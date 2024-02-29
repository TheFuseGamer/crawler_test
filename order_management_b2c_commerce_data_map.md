# Salesforce B2C Commerce Storefront Order Data Map

These tables illustrate how data in a Salesforce B2C Commerce order packet maps to
  records in Salesforce Order Management. If you’re implementing your own storefront integration,
  this map can help you understand the order data requirements.

## Integration Notes

General:

- B2C Commerce sends orders in New or Open status to Salesforce Order Management. To delay
     sending an order, for example, to perform a fraud check, keep it in Created status.
- B2C Commerce sends order data to Salesforce Order Management according to a set frequency
     and when the packet of pending orders reaches a certain size. The process is similar to the one
     used for Commerce Cloud Order Management. In addition, the integration contacts B2C Commerce
     every 5 minutes to request any pending order data.
- When the order/billing-address/company-name value in the order data is
     not null, Order Management always uses a standard account and contact to represent the
     shopper.

International Considerations

- If the order/taxation value for an order is <kbd class="ph userinput">net</kbd>,
     then the integration creates an OrderItemTaxLineItem record for each OrderItem and
     OrderItemAdjustmentLineItem record.
- If Salesforce state and country picklists aren’t enabled:
    - The state-code values in order data must match a standard 2-character
       ISO state or province code. The integration copies them to State fields on Salesforce
       records.
    - The country-code values in order data must match a standard
       2-character ISO country code. The integration copies them to Country fields on Salesforce
       records.
- If Salesforce state and country picklists are enabled:
    - The state-code values in order data must match the state code of an
       entry in the Salesforce state picklist. The integration copies them to StateCode fields on
       Salesforce records. The corresponding State fields are set to the matching integration values
       from the picklist.
    - The country-code values in order data must match the country code of
       an entry in the Salesforce country picklist. The integration copies them to CountryCode
       fields on Salesforce records. The corresponding Country fields are set to the matching
       integration values from the picklist.

Payments

- Order data includes a paired payment instrument and payment transaction for each payment
     associated with the order.
- If an order/payments/payment/transaction-type value in the order data
     starts with <kbd class="ph userinput">auth</kbd>, then the integration creates a PaymentAuthorization
     record for that transaction. If the value is <kbd class="ph userinput">sale</kbd> or
      <kbd class="ph userinput">capture</kbd>, then it creates a Payment record. These checks are not
     case-sensitive.
- For a credit or debit card payment type, the
      payments/payment/credit-card/card-type value in the order data must match
     a value in the CardType picklist on the CardPaymentMethod object.
- To handle a payment method that doesn’t match a CardPaymentMethod CardType or DigitalWallet
     Type, create a custom payment method as described later in this section.
- The integration recognizes certain custom attributes on
      order/payments/paymentand copies them to standard fields on the
     PaymentGatewayLog record in Salesforce. To take advantage of this feature, create and populate
     custom attributes with the following exact names on the Order Payment Transaction object in B2C Commerce:
    - authCode (value copied to PaymentGatewayLog.GatewayAuthCode)
    - avsResultCode (value copied to PaymentGatewayLog.GatewayAvsCode)
    - approvalStatus (value copied to
       PaymentGatewayLog.GatewayResultCode)

Promotions

- The integration creates an OrderAdjustmentGroup record for each
      price-adjustments/price-adjustment/promotion-id included in the order
     data. For each OrderAdjustmentGroup, it creates an OrderItemAdjustmentLineItem record for each
     OrderItem in the order that the promotion applies to.
- If the order/taxation value for an order is <kbd class="ph userinput">net</kbd>,
     then the integration creates an OrderItemTaxLineItem record for each
     OrderItemAdjustmentLineItem record.

For information on the Salesforce state and country picklists, see [Let Users Select State and Country from
     Picklists](https://help.salesforce.com/articleView?id=admin_state_country_picklists_overview.htm&amp;language=en_US "HTML (New Window)") in <cite class="cite">Salesforce Help</cite>.

## Set Up Payment Gateways

Configure a payment gateway adapter for each merchant account. If you use multiple currencies     or payment methods through a single payment processor, you can optionally set up multiple     payment gateways for that processor. By default, the Order Management integration with     Salesforce B2C Commerce only supports credit card and digital wallet payment types, but you can     create your own customizations.

You can use Apex and the Connect REST API to set up payment gateways. See [commercepayments namespace](https://developer.salesforce.com/docs/atlas.en-us.230.0.apexcode.meta/apexcode/apex_namespace_commercepayments.htm "HTML (New Window)") and      [Use Cases for the commercepayments
     Namespace](https://developer.salesforce.com/docs/atlas.en-us.230.0.apexcode.meta/apexcode/apex_commercepayments_use_cases.htm "HTML (New Window)") in the <cite class="cite">Apex Developer Guide</cite>, and [Commerce Payments Resources](https://developer.salesforce.com/docs/atlas.en-us.230.0.chatterapi.meta/chatterapi/connect_resources_payments.htm "HTML (New Window)") in the      <cite class="cite">Connect REST API Developer Guide</cite>.

## Payment Method Processing

The B2C Commerce integration processes each storefront payment method in the order data as     follows:

1. Does the payment method ID in the order data match the following non-case-sensitive regular
     expression? If so, then create a DigitalWallet record in
     Salesforce.

    ```
    paypal|visa_checkout|pay_by_check|.*(apple|google|android|amazon|ali).*(pay)*
    ```
2. Does the payment method ID in the order data match the Gateway Provider Payment Method Type
     of a GtwyProvPaymentMethodType record in Salesforce? If so, then create a record in Salesforce
     according to the GtwyProvPaymentMethodType’s Payment Method Type.
3. Does the card type in the order data match an entry in the Card Type picklist on the
     CardPaymentMethod object in Salesforce? If so, then create a CardPaymentMethod record in
      Salesforce.

![Note](/docs/resources/img/en-us/230.0?doc_id=images%2Ficon_note.png&folder=order_management_developer_guide)

#### Note

You can’t customize the Card Type picklist.
4. Return an error message that the payment method isn’t supported.

To support a different payment type, set up a custom payment method as described in the next     section.

## Create Custom Payment Methods

If you use a storefront payment method that meets both of the following criteria, configure a     custom payment method for it.

- The default regular expression doesn’t identify it as a DigitalWallet method.
- It doesn’t match any of the standard card types for a CardPaymentMethod.

To configure a custom payment method as an AlternativePaymentMethod, first create a RecordType     for the AlternativePaymentMethod object. Give the record type a name that represents the payment     method. For information on creating record types, see [Create Record Types](https://help.salesforce.com/articleView?id=creating_record_types.htm&amp;language=en_US "HTML (New Window)") in <cite class="cite">Salesforce
     Help</cite>.

Define a custom payment method by creating a GtwyProvPaymentMethodType (Gateway Provider     Payment Method Type) record. The gateway provider payment method type associates the custom     payment method with a payment gateway and defines it as an AlternativePaymentMethod,     CardPaymentMethod, or DigitalWallet.

![Note](/docs/resources/img/en-us/230.0?doc_id=images%2Ficon_note.png&folder=order_management_developer_guide)

#### Note

You can’t create or access a **GtwyProvPaymentMethodType record** in the Salesforce UI.     To create one, insert a record using Workbench. The API name of the object is     GtwyProvPaymentMethodType, at the URL <samp class="codeph nolang">/services/data/v51.0/sobjects/GtwyProvPaymentMethodType</samp>.

Set the GtwyProvPaymentMethodType fields as described here.

     - Comments

         - Optional description.

     - Developer Name

         - The unique API name of the record.

     - Master Label

         - A human-readable name for the record.

     - Gateway Provider Payment Method Type

         - The name of the payment method in the storefront. This value must exactly match the payment
      method ID used in B2C Commerce.

     - Payment Gateway Provider Id

         - Reference to the Payment Gateway Provider record associated with the payment processor for
      the payment method.

     - Payment Method Type

         - <kbd class="ph userinput">AlternativePaymentMethod</kbd>
      <kbd class="ph userinput">CardPaymentMethod</kbd>, or <kbd class="ph userinput">DigitalWallet</kbd>. To use
      AlternativePaymentMethod, first create a corresponding RecordType record.

     - Record Type Id

         - If using an AlternativePaymentMethod, this value is a reference to the RecordType
      record.

Here’s an example of a gateway provider payment method definition:

```
{
  "DeveloperName" : "BankTransfer"
  "MasterLabel" : "Bank Transfer",
  "GtwyProviderPaymentMethodType" : "directBanking",
  "PaymentGatewayProviderId" : "0cJaa0000000001E67",
  "PaymentMethodType" : "AlternativePaymentMethod",
  “RecordTypeId” : "012aa000000008A34F"
}
```

## Integrate Custom B2C Commerce Storefront Data

The integration can pass custom data on certain B2C Commerce objects to Order Management. To     set up the transfer, add custom attributes to objects in B2C Commerce, and add matching custom     fields to the corresponding objects in Order Management. As long as the names and data types     match, the integration includes those values when it creates Order Management records. If you     also create a matching field on the corresponding summary object, Order Management includes the     custom data when it creates a summary record.

If order data includes a custom attribute value, but the corresponding Salesforce object has     no matching custom field, the integration ignores that attribute. If a custom field exists in     Salesforce, and order data doesn’t include a matching custom attribute value, the integration     ignores it.

![Important](/docs/resources/img/en-us/230.0?doc_id=images%2Ficon_note_important.png&folder=order_management_developer_guide)

#### Important

If a custom field in Salesforce is required, and it corresponds to a     custom storefront attribute, then order data must include a value for that attribute. Without     that value, the integration can’t create the corresponding Salesforce record. In that case, the     integration fails with an error.

![Note](/docs/resources/img/en-us/230.0?doc_id=images%2Ficon_note.png&folder=order_management_developer_guide)

#### Note

At the API level, custom field names in Salesforce always end in     <kbd class="ph userinput">__c</kbd>. Don’t include it in the names of the matching attributes on your     storefront objects. However, if you include a custom namespace in a custom field name, also     include it in the name of the matching storefront object attribute. For example, if the API name     of your custom field in Salesforce is <kbd class="ph userinput">mynamespace_FieldName__c</kbd>, name your     matching storefront object attribute <kbd class="ph userinput">mynamespace_FieldName</kbd>.

You can use matching custom attributes and fields on these sets of objects:

| B2C Commerce | Salesforce Order Management |
| --- | --- |
| Gift Certificate Line Item and Product Line Item (not Shipping Line Item) | OrderItem and OrderItemSummary |
| Order | Order and OrderSummary |
| Order Payment Instrument and Order Payment Transaction | CardPaymentMethod, DigitalWallet, Payment, PaymentAuthorization, and
        PaymentGatewayLog |

The integration supports the following data types for matching custom attributes and     fields:

- Boolean
- Currency
- Datetime (Date is not supported)
- Double
- Multipicklist
- Phone
- Picklist
- Reference
- String
- TextArea
- URL

The Order Management B2C Service permission set provides the integration with access to     Salesforce records. When you add a custom field to a Salesforce object, update that permission     set by adding read and edit access to the new field. You also must add edit access to the     permission set that provides access for your Order Management users.

1. From Setup, in the Quick Find box, enter <kbd class="ph userinput">Permission Sets</kbd>, and then
     select **Permission Sets**.
2. Select **Order Management B2C Service**.
3. In the Apps section, click **Object Settings**.
4. Select the object that has the custom field.
5. Click **Edit**.
6. In the Field Permissions section, select the **Edit Access** checkbox for
     the custom field.
7. Click **Save**.
8. Return to the list of permission sets by selecting **Permission Sets** in
     the Setup navigation menu.
9. Select the permission set that controls access for your Order Management users. Normally,
     it’s called **OM Console**.
10. In the Apps section, click **Object Settings**.
11. Select the object that has the custom field.
12. Click **Edit**.
13. In the Field Permissions section, select the **Edit Access** checkbox for
     the custom field.
14. Click **Save**.

## Account Object (Standard or PersonAccount)

Order Management always uses standard accounts to represent shoppers that have company names.     If an order includes an order/billing-address/company-name value, and no     matching account record exists, then the integration creates a standard account, regardless of     the Person Accounts for Shoppers setting.

Changing the Person Accounts for Shoppers org setting doesn’t affect existing shopper data.
    However, it changes the way that the B2C Commerce integration stores new shopper data and
    whether it recognizes existing shopper data.
- While Order Management is configured to use standard accounts: the integration recognizes
      existing shoppers that are stored as person accounts. It associates their new orders with
      their existing person accounts. If an existing shopper has records of both types, it
      associates new orders with their standard account and contact.
- While Order Management is configured to use person accounts: the integration doesn’t
      recognize existing shoppers that are stored as standard accounts and contacts. If one of those
      shoppers places an order, the integration creates a person account record for them and
      associates the new order with it. Order Management treats the accounts as separate shoppers.
      If an existing shopper has records of both types, the integration associates new orders with
      their person account.

| B2C Commerce XSD Value | Salesforce Object Field | Notes |
| --- | --- | --- |
| order/billing-address/company-name or order/billing-address/first-name and
        order/billing-address/last-name | Name | If order/billing-address/company-namehas a
        value in the order data packet, then it’s copied to this value. If it has no value in the
        order data, this value is set as follows:<ul class="ul bulletList">
         <li class="li">If this record is a person account, this value is not set.</li>

         <li class="li">If this record is not a person account, this value is set to
           <var class="keyword varname">order/billing-address/first-name</var> + "<kbd class="ph userinput"> </kbd>" +
           <var class="keyword varname">order/billing-address/last-name</var>.</li>

        </ul> |
| order/billing-address/first-name and order/billing-address/second-name | FirstName | This value is only set for person accounts. It is set to
         <var class="keyword varname">order/billing-address/first-name</var> + "<kbd class="ph userinput"> </kbd>" +
         <var class="keyword varname">order/billing-address/second-name</var>. |
| order/billing-address/last-name | LastName | This value is only set for person accounts. |
| order/customer/customer-email | PersonEmail | This value is only set for person accounts. |
| order/billing-address/title | PersonTitle | This value is only set for person accounts. |
| order/billing-address/address1, order/billing-address/address2, and
        order/billing-address/address3 | BillingStreet | This value is only set for person accounts. It’s set to
         <var class="keyword varname">order/billing-address/address1</var> + "<kbd class="ph userinput"> </kbd>" +
         <var class="keyword varname">order/billing-address/address2</var> + "<kbd class="ph userinput"> </kbd>" +
         <var class="keyword varname">order/billing-address/address3</var>. |
| order/billing-address/city | BillingCity | This value is only set for person accounts. |
| order/billing-address/postal-code | BillingPostalCode | This value is only set for person accounts. |
| order/billing-address/state-code | BillingState | This value is only set for person accounts. Usage depends on whether state and country
        picklists are enabled in Salesforce.<ul class="ul bulletList">
         <li class="li">Picklists not enabled- This value is set to
           <var class="keyword varname">order/billing-address/state-code</var>. It must be a standard 2-character
          ISO state or province code.</li>

         <li class="li">Picklists enabled- This value is set to the picklist integration value corresponding to
          the state code that matches <var class="keyword varname">order/billing-address/state-code</var>.</li>

        </ul> |
| order/billing-address/state-code | BillingStateCode | This value is only set for person accounts, and only when state and country picklists
        are enabled on your org. <var class="keyword varname">order/billing-address/state-code</var> must match the
        state code of an entry in the Salesforce state picklist. |
| order/billing-address/country-code | BillingCountry | This value is only set for person accounts. Usage depends on whether state and country
        picklists are enabled in Salesforce.<ul class="ul bulletList">
         <li class="li">Picklists not enabled- This value is set to
           <var class="keyword varname">order/billing-address/country-code</var>. It must be a standard 2-character
          ISO country code.</li>

         <li class="li">Picklists enabled- This value is set to the picklist integration value corresponding to
          the country code that matches <var class="keyword varname">order/billing-address/country-code</var>.</li>

        </ul> |
| order/billing-address/country-code | BillingCountryCode | This value is only set for person accounts, and only when state and country picklists
        are enabled on your org. <var class="keyword varname">order/billing-address/country-code</var> must match
        the country code of an entry in the Salesforce country picklist. |
| order/billing-address/phone | Phone | This value is set for both person accounts and regular accounts. |

## AlternativePaymentMethod Object

The integration checks the payment\_method value of each payment     instrument in an order. If it matches the Gateway Provider Payment Method Type of a     GtwyProvPaymentMethodType record, then the integration creates a record according to the     GtwyProvPaymentMethodType’s Payment Method Type value. If the Payment Method Type is     AlternativePaymentMethod, then the integration creates an AlternativePaymentMethod record using     the associated RecordType.

![Note](/docs/resources/img/en-us/230.0?doc_id=images%2Ficon_note.png&folder=order_management_developer_guide)

#### Note

To use AlternativePaymentMethod, first create a RecordType and GtwyProvPaymentMethodType     for your custom payment type as described in the Create Custom Payment Methods section.

| B2C Commerce XSD Value | Salesforce Object Field | Notes |
| --- | --- | --- |
| N/A | RecordTypeId | This value is set to the ID of the RecordType record assigned to the
        GtwyProvPaymentMethodType. |
| order/payments/payment/credit-card/card-token | GatewayToken |  |
| order/customer/customer-email | Email |  |
| N/A | Status | This picklist value is always set to <kbd class="ph userinput">Active</kbd>. |
| order/billing-address/company-name | CompanyName |  |
| order/billing-address/address1, order/billing-address/address2, and
        order/billing-address/address3 | PaymentMethodStreet | This value is set to <var class="keyword varname">order/billing-address/address1</var> +
         "<kbd class="ph userinput"> </kbd>" + <var class="keyword varname">order/billing-address/address2</var> +
         "<kbd class="ph userinput"> </kbd>" + <var class="keyword varname">order/billing-address/address3</var>. |
| order/billing-address/city | PaymentMethodCity |  |
| order/billing-address/state-code | PaymentMethodState | Usage depends on whether state and country picklists are enabled in Salesforce.<ul class="ul bulletList">
         <li class="li">Picklists not enabled- This value is set to
           <var class="keyword varname">order/billing-address/state-code</var>. It must be a standard 2-character
          ISO state or province code.</li>

         <li class="li">Picklists enabled- This value is set to the picklist integration value corresponding to
          the state code that matches <var class="keyword varname">order/billing-address/state-code</var>.</li>

        </ul> |
| order/billing-address/state-code | PaymentMethodStateCode | This value is only set when state and country picklists are enabled on your org.
         <var class="keyword varname">order/billing-address/state-code</var> must match the state code of an entry
        in the Salesforce state picklist. |
| order/billing-address/postal-code | PaymentMethodPostalCode |  |
| order/billing-address/country-code | PaymentMethodCountry | Usage depends on whether state and country picklists are enabled in Salesforce.<ul class="ul bulletList">
         <li class="li">Picklists not enabled- This value is set to
           <var class="keyword varname">order/billing-address/country-code</var>. It must be a standard 2-character
          ISO country code.</li>

         <li class="li">Picklists enabled- This value is set to the picklist integration value corresponding to
          the country code that matches <var class="keyword varname">order/billing-address/country-code</var>.</li>

        </ul> |
| order/billing-address/country-code | PaymentMethodCountryCode | This value is only set when state and country picklists are enabled on your org.
         <var class="keyword varname">order/billing-address/country-code</var> must match the country code of an
        entry in the Salesforce country picklist. |
| order/billing-address/phone | Phone |  |
| orderremoteHost | IpAddress |  |
| N/A | AccountId | This value is set to the ID of the Account or Person Account record associated with
        the shopper. |
| N/A | PaymentGatewayId | This value is set to the ID of the PaymentGateway record associated with the
        PaymentGatewayProvider record assigned to the GtwyProvPaymentMethodType. |
| N/A | ProcessingMode | This value is always set to <kbd class="ph userinput">External</kbd>. It specifies that an
        external payment provider handles payment transactions. |
| order/payments/payment/<var class="keyword varname">custom_attribute</var> or a custom attribute on
        the payment type | <var class="keyword varname">Custom_Attribute</var> | If the Salesforce AlternativePaymentMethod object has a custom field matching a custom
        attribute on the storefront payment type or order payment transaction object, the value is
        copied to the AlternativePaymentMethod record. If a custom field is non-nillable, then order
        data must include a value for the corresponding custom attribute. If the value is missing,
        the integration fails. |

## CardPaymentMethod Object

The integration checks the payment\_method value of each payment     instrument in an order against the following regex. If it matches, then the integration creates     a DigitalWallet record for the instrument. If it doesn’t match, then the integration checks the      payment/credit-card/card-type value against the CardType picklist on the     CardPaymentMethod object. If the picklist contains a match, then the integration creates a     CardPaymentMethod record for the instrument. Otherwise, to support the payment method, you must     set up a custom payment method for it.

```
paypal|visa_checkout|pay_by_check|.*(apple|google|android|amazon|ali).*(pay)*
```

![Note](/docs/resources/img/en-us/230.0?doc_id=images%2Ficon_note.png&folder=order_management_developer_guide)

#### Note

The regex is not case-sensitive.

| B2C Commerce XSD Value | Salesforce Object Field | Notes |
| --- | --- | --- |
| order/payments/payment/credit-card/card-type | CardType | The value must match a card type in the CardType picklist on the CardPaymentMethod
        object. To handle a different card type, create a custom payment method as described in the
         <cite class="cite">Order Management Implementation Guide</cite>. |
| order/payments/payment/credit-card/card-number | InputCardNumber |  |
| order/payments/payment/credit-card/card-holder | CardHolderName |  |
| order/payments/payment/credit-card/expiration-year | ExpiryYear |  |
| order/payments/payment/credit-card/expiration-month | ExpiryMonth |  |
| [order payment method] | CardCategory | This value can be <kbd class="ph userinput">CreditCard</kbd> or
         <kbd class="ph userinput">DebitCard</kbd>. The default value is
        <kbd class="ph userinput">CreditCard</kbd>. |
| N/A | Status | This picklist value is always set to <kbd class="ph userinput">Active</kbd>. |
| order/payments/payment/credit-card/card-token | GatewayToken |  |
| order/billing-address/address1, order/billing-address/address2, and
        order/billing-address/address3 | PaymentMethodStreet | This value is set to <var class="keyword varname">order/billing-address/address1</var> +
         "<kbd class="ph userinput"> </kbd>" + <var class="keyword varname">order/billing-address/address2</var> +
         "<kbd class="ph userinput"> </kbd>" + <var class="keyword varname">order/billing-address/address3</var>. |
| order/billing-address/city | PaymentMethodCity |  |
| order/billing-address/state-code | PaymentMethodState | Usage depends on whether state and country picklists are enabled in Salesforce.<ul class="ul bulletList">
         <li class="li">Picklists not enabled- This value is set to
           <var class="keyword varname">order/billing-address/state-code</var>. It must be a standard 2-character
          ISO state or province code.</li>

         <li class="li">Picklists enabled- This value is set to the picklist integration value corresponding to
          the state code that matches <var class="keyword varname">order/billing-address/state-code</var>.</li>

        </ul> |
| order/billing-address/state-code | PaymentMethodStateCode | This value is only set when state and country picklists are enabled on your org.
         <var class="keyword varname">order/billing-address/state-code</var> must match the state code of an entry
        in the Salesforce state picklist. |
| order/billing-address/postal-code | PaymentMethodPostalCode |  |
| order/billing-address/country-code | PaymentMethodCountry | Usage depends on whether state and country picklists are enabled in Salesforce.<ul class="ul bulletList">
         <li class="li">Picklists not enabled- This value is set to
           <var class="keyword varname">order/billing-address/country-code</var>. It must be a standard 2-character
          ISO country code.</li>

         <li class="li">Picklists enabled- This value is set to the picklist integration value corresponding to
          the country code that matches <var class="keyword varname">order/billing-address/country-code</var>.</li>

        </ul> |
| order/billing-address/country-code | PaymentMethodCountryCode | This value is only set when state and country picklists are enabled on your org.
         <var class="keyword varname">order/billing-address/country-code</var> must match the country code of an
        entry in the Salesforce country picklist. |
| N/A | AccountId | This value is set to the ID of the Account or Person Account record associated with
        the CardPaymentMethod. |
| N/A | PaymentGatewayId | This value is set to the ID of the PaymentGateway record whose ExternalReference value
        matches the processor ID value of the order payment instrument. |
| N/A | ProcessingMode | This value is always set to <kbd class="ph userinput">External</kbd>. It specifies that an
        external payment provider handles payment transactions. |
| order/payments/payment/<var class="keyword varname">custom_attribute</var> or a custom attribute on
        the payment type | <var class="keyword varname">Custom_Attribute</var> | If the Salesforce CardPaymentMethod object has a custom field matching a custom
        attribute on the storefront payment type or order payment transaction object, the value is
        copied to the CardPaymentMethod record. If a custom field is non-nillable, then order data
        must include a value for the corresponding custom attribute. If the value is missing, the
        integration fails. |

## Contact Object

When using person accounts, access shopper contact data using person account records, not
    contact records. When using standard accounts and contacts, the
     BillToContactIdfield on these objects points to the associated contact record:
- Credit Memo
- Fulfillment Order
- Invoice
- Order
- Order Summary

| B2C Commerce XSD Value | Salesforce Object Field | Notes |
| --- | --- | --- |
| N/A | AccountId | This value is set to the ID of the Account record that represents the shopper. |
| order/customer/customer-email | Email |  |
| order/billing-address/first-name | FirstName |  |
| order/billing-address/last-name | LastName |  |
| order/billing-address/phone | Phone |  |

## DigitalWallet Object

The integration checks the payment\_method value of each payment     instrument in an order. If it matches the following regex, then the integration creates a     DigitalWallet record for the instrument. If it doesn’t match, then the integration tries to     create an AlternativePaymentMethod or a CardPaymentMethod record for the instrument.

```
paypal|visa_checkout|pay_by_check|.(apple|google|android|amazon|ali).(pay)*
```

![Note](/docs/resources/img/en-us/230.0?doc_id=images%2Ficon_note.png&folder=order_management_developer_guide)

#### Note

The regex is not case-sensitive.

| B2C Commerce XSD Value | Salesforce Object Field | Notes |
| --- | --- | --- |
| N/A | Status | This picklist value is always set to <kbd class="ph userinput">Active</kbd>. |
| [order payment method] | Type |  |
| order/payments/payment/credit-card/card-token | GatewayToken |  |
| order/billing-address/address1, order/billing-address/address2, and
        order/billing-address/address3 | PaymentMethodStreet | This value is set to <var class="keyword varname">order/billing-address/address1</var> +
         "<kbd class="ph userinput"> </kbd>" + <var class="keyword varname">order/billing-address/address2</var> +
         "<kbd class="ph userinput"> </kbd>" + <var class="keyword varname">order/billing-address/address3</var>. |
| order/billing-address/city | PaymentMethodCity |  |
| order/billing-address/state-code | PaymentMethodState | Usage depends on whether state and country picklists are enabled in Salesforce.<ul class="ul bulletList">
         <li class="li">Picklists not enabled- This value is set to
           <var class="keyword varname">order/billing-address/state-code</var>. It must be a standard 2-character
          ISO state or province code.</li>

         <li class="li">Picklists enabled- This value is set to the picklist integration value corresponding to
          the state code that matches <var class="keyword varname">order/billing-address/state-code</var>.</li>

        </ul> |
| order/billing-address/state-code | PaymentMethodStateCode | This value is only set when state and country picklists are enabled on your org.
         <var class="keyword varname">order/billing-address/state-code</var> must match the state code of an entry
        in the Salesforce state picklist. |
| order/billing-address/postal-code | PaymentMethodPostalCode |  |
| order/billing-address/country-code | PaymentMethodCountry | Usage depends on whether state and country picklists are enabled in Salesforce.<ul class="ul bulletList">
         <li class="li">Picklists not enabled- This value is set to
           <var class="keyword varname">order/billing-address/country-code</var>. It must be a standard 2-character
          ISO country code.</li>

         <li class="li">Picklists enabled- This value is set to the picklist integration value corresponding to
          the country code that matches <var class="keyword varname">order/billing-address/country-code</var>.</li>

        </ul> |
| order/billing-address/country-code | PaymentMethodCountryCode | This value is only set when state and country picklists are enabled on your org.
         <var class="keyword varname">order/billing-address/country-code</var> must match the country code of an
        entry in the Salesforce country picklist. |
| N/A | AccountId | This value is set to the ID of the Account or Person Account record associated with
        the DigitalWallet. |
| N/A | PaymentGatewayId | This value is set to the ID of the PaymentGateway record whose ExternalReference value
        matches the processor ID value of the order payment instrument. |
|  | ProcessingMode | This value is always set to <kbd class="ph userinput">External</kbd>. It specifies that an
        external payment provider handles payment transactions. |
| order/payments/payment/<var class="keyword varname">custom_attribute</var> or a custom attribute on
        the payment type | <var class="keyword varname">Custom_Attribute</var> | If the Salesforce DigitalWallet object has a custom field matching a custom attribute
        on the storefront payment type or order payment transaction object, the value is copied to
        the DigitalWallet record. If a custom field is non-nillable, then order data must include a
        value for the corresponding custom attribute. If the value is missing, the integration
        fails. |

## Order Object

| B2C Commerce XSD Value | Salesforce Object Field | Notes |
| --- | --- | --- |
| N/A | Pricebook2Id | This value is set to the ID of the Pricebook2 record for the standard price
        book. |
| order/customer/customer-name | Name |  |
| N/A | Status | When the Order record is created, this value is set to <kbd class="ph userinput">Draft</kbd>.
        The last step in the Composite API call that creates the records related to the order sets
        this value to <kbd class="ph userinput">Active</kbd>. |
| N/A | EffectiveDate | This value is set to the current datetime when the record is created. |
| order/order-no | OrderReferenceNumber |  |
| order/billing-address/address1, order/billing-address/address2, and
        order/billing-address/address3 | BillingStreet | This value is set to <var class="keyword varname">order/billing-address/address1</var> +
         "<kbd class="ph userinput"> </kbd>" + <var class="keyword varname">order/billing-address/address2</var> +
         "<kbd class="ph userinput"> </kbd>" + <var class="keyword varname">order/billing-address/address3</var>. |
| order/billing-address/city | BillingCity |  |
| order/billing-address/state-code | BillingState | Usage depends on whether state and country picklists are enabled in Salesforce.<ul class="ul bulletList">
         <li class="li">Picklists not enabled- This value is set to
           <var class="keyword varname">order/billing-address/state-code</var>. It must be a standard 2-character
          ISO state or province code.</li>

         <li class="li">Picklists enabled- This value is set to the picklist integration value corresponding to
          the state code that matches <var class="keyword varname">order/billing-address/state-code</var>.</li>

        </ul> |
| order/billing-address/state-code | BillingStateCode | This value is only set when state and country picklists are enabled on your org.
         <var class="keyword varname">order/billing-address/state-code</var> must match the state code of an entry
        in the Salesforce state picklist. |
| order/billing-address/postal-code | BillingPostalCode |  |
| order/billing-address/country-code | BillingCountry | Usage depends on whether state and country picklists are enabled in Salesforce.<ul class="ul bulletList">
         <li class="li">Picklists not enabled- This value is set to
           <var class="keyword varname">order/billing-address/country-code</var>. It must be a standard 2-character
          ISO country code.</li>

         <li class="li">Picklists enabled- This value is set to the picklist integration value corresponding to
          the country code that matches <var class="keyword varname">order/billing-address/country-code</var>.</li>

        </ul> |
| order/billing-address/country-code | BillingCountryCode | This value is only set when state and country picklists are enabled on your org.
         <var class="keyword varname">order/billing-address/country-code</var> must match the country code of an
        entry in the Salesforce country picklist. |
| order/billing-address/phone | BillingPhoneNumber |  |
| order/order-date | OrderedDate |  |
| order/customer/customer-email | BillingEmailAddress |  |
| N/A | BillToContactId | This value is set to the ID of the Contact record that represents the shopper. When
        using person accounts, this value is not set. In that case, access shopper contact
        information via the Account instead of the Contact. |
| N/A | AccountId | This value is set to the ID of the Account or Person Account record that represents
        the shopper. |
| N/A | SalesChannelId | This value is set to the ID of the SalesChannel record whose Name field matches the
         order.domain\_id in the order data packet. |
| order/taxation | TaxLocaleType | This value is set to <kbd class="ph userinput">Net</kbd> or <kbd class="ph userinput">Gross</kbd> based
        on the value of order/taxation. If using Net taxation, this value is set to
         <kbd class="ph userinput">Net</kbd> and the integration creates OrderItemTaxLineItem records for the
        order. If using Gross taxation, this value is set to <kbd class="ph userinput">Gross</kbd> and the
        integration doesn’t create OrderItemTaxLineItem records for the order. If the value isn’t
        set, then the default value is <kbd class="ph userinput">Net</kbd>. |
| order/currency | CurrencyIsoCode | This value is only set if the Salesforce org has Multicurrency enabled. |
| order/<var class="keyword varname">custom_attribute</var> | <var class="keyword varname">Custom_Attribute</var> | If the Salesforce Order object has a custom field matching a custom attribute on the
        storefront Order object, the value is copied to the Order record. If the Salesforce
        OrderSummary object also has a matching custom field, it’s copied to both records. If a
        custom field is non-nillable, then order data must include a value for the corresponding
        custom attribute. If the value is missing, the integration fails. |

## OrderAdjustmentGroup Object

The integration creates one OrderAdjustmentGroup record for each promotion that applies to an     order. For an order-level promotion, it assigns the OrderAdjustmentGroup to one     OrderItemAdjustmentLineItem record for each OrderItem record in the order. For an item-level     promotion, it assigns the OrderAdjustmentGroup to one OrderItemAdjustmentLineItem record for     each OrderItem record in the Order that the promotion applies to.

![Note](/docs/resources/img/en-us/230.0?doc_id=images%2Ficon_note.png&folder=order_management_developer_guide)

#### Note

Shipping adjustments that aren’t part of an order-level promotion are treated as item-level     promotions. An example of an order-level promotion is “20% off and free shipping.”

| B2C Commerce XSD Value | Salesforce Object Field | Notes |
| --- | --- | --- |
| See notes | Name | This value is generated based on the type of the promotion:<ul class="ul bulletList">
         <li class="li">Order-level- <var class="keyword varname">price-adjustments/price-adjustment/promotion-id</var>
</li>

         <li class="li">Item-level- <var class="keyword varname">order/product-lineitems/product-lineitem/product-id</var> +
           "<kbd class="ph userinput"> - </kbd>" +
           <var class="keyword varname">price-adjustments/price-adjustment/promotion-id</var>
</li>

        </ul> |
| price-adjustments/price-adjustment/promotion-id | Description |  |
| N/A | Type | This picklist value is always set to <kbd class="ph userinput">Header</kbd>. |
| N/A | OrderId | This value is set to the ID of the associated original Order record. |

## OrderDeliveryGroup Object

The integration creates an OrderDeliveryGroup record for each shipment (also called a     LineItemGroup in B2C Commerce) in the order data.

For order changes such as returns and cancellations that include prorated delivery amounts,     the proration considers the OrderDeliveryGroups containing OrderItems that are part of the     change. For example, consider an order that has three OrderDeliveryGroups, each with multiple     OrderItems. A return of two OrderItems, each from a different OrderDeliveryGroup, uses the total     delivery charges associated with those two OrderDeliveryGroups. It prorates that amount across     the OrderItems in those OrderDeliveryGroups by OrderItem price. The shipping refund equals the     prorated delivery amounts for the two returned OrderItems. The return doesn’t consider any     delivery charges associated with the third OrderDeliveryGroup.

| B2C Commerce XSD Value | Salesforce Object Field | Notes |
| --- | --- | --- |
| order/customer/customer-email | EmailAddress |  |
| order/shipments/shipment/shipping-address/city | DeliverToCity |  |
| order/shipments/shipment/shipping-address/country-code | DeliverToCountry | Usage depends on whether state and country picklists are enabled in Salesforce.<ul class="ul bulletList">
         <li class="li">Picklists not enabled- This value is set to
           <var class="keyword varname">order/shipments/shipment/shipping-address/country-code</var>. It must be a
          standard 2-character ISO country code.</li>

         <li class="li">Picklists enabled- This value is set to the picklist integration value corresponding to
          the country code that matches
           <var class="keyword varname">order/shipments/shipment/shipping-address/country-code</var>.</li>

        </ul> |
| order/shipments/shipment/shipping-address/country-code | DeliverToCountryCode | This value is only set when state and country picklists are enabled on your org.
         <var class="keyword varname">order/shipments/shipment/shipping-address/country-code</var> must match the
        country code of an entry in the Salesforce country picklist. |
| order/shipments/shipment/shipping-address/title,
        order/shipments/shipment/shipping-address/first-name,
        order/shipments/shipment/shipping-address/last-name, and
        order/shipments/shipment/shipping-address/suffix | DeliveryGroupToName | This value is set to
         <var class="keyword varname">order/shipments/shipment/shipping-address/title</var> +
         "<kbd class="ph userinput"> </kbd>" +
         <var class="keyword varname">order/shipments/shipment/shipping-address/first-name</var> +
         "<kbd class="ph userinput"> </kbd>" +
         <var class="keyword varname">order/shipments/shipment/shipping-address/last-name</var> +
         "<kbd class="ph userinput"> </kbd>" +
         <var class="keyword varname">order/shipments/shipment/shipping-address/suffix</var>. |
| order/shipments/shipment/shipping-address/postal-code | DeliverToPostalCode |  |
| order/shipments/shipment/shipping-address/state-code | DeliverToState | Usage depends on whether state and country picklists are enabled in Salesforce.<ul class="ul bulletList">
         <li class="li">Picklists not enabled- This value is set to
           <var class="keyword varname">order/shipments/shipment/shipping-address/state-code</var>. It must be a
          standard 2-character ISO state or province code.</li>

         <li class="li">Picklists enabled- This value is set to the picklist integration value corresponding to
          the state code that matches
           <var class="keyword varname">order/shipments/shipment/shipping-address/state-code</var>.</li>

        </ul> |
| order/shipments/shipment/shipping-address/state-code | DeliverToStateCode | This value is only set when state and country picklists are enabled on your org.
         <var class="keyword varname">order/shipments/shipment/shipping-address/state-code</var> must match the
        state code of an entry in the Salesforce country picklist. |
| order/shipments/shipment/shipping-address/address1,
        order/shipments/shipment/shipping-address/address2, and
        order/shipments/shipment/shipping-address/address3 | DeliverToStreet | This value is set to
         <var class="keyword varname">order/shipments/shipment/shipping-address/address1</var> +
         "<kbd class="ph userinput"> </kbd>" +
         <var class="keyword varname">order/shipments/shipment/shipping-address/address2</var> +
         "<kbd class="ph userinput"> </kbd>" +
         <var class="keyword varname">order/shipments/shipment/shipping-address/address3</var>. |
| order/shipments/shipment/shipping-address/phone | PhoneNumber |  |
| order/shipments/shipment/gift | IsGift | This value is only populated if
         order/shipments/shipment/gift=<kbd class="ph userinput">true</kbd>. |
| order/shipments/shipment/gift-message | GiftMessage | This value is only populated if
         order/shipments/shipment/gift=<kbd class="ph userinput">true</kbd>. |
| order/shipments/shipment/shipping-method | OrderDeliveryMethodId | This value is set to the ID of the OrderDeliveryMethod record whose
         ReferenceNumber field matches the
         order/shipments/shipment/shipping-method value in the order
        data. |
| N/A | OrderId | This value is set to the ID of the associated original Order record. |

## OrderItem Object

If an order has a TaxLocaleType of Net, then the integration also creates an     OrderItemTaxLineItem record for each OrderItem record.

| B2C Commerce XSD Value | Salesforce Object Field | Notes |
| --- | --- | --- |
| order/product-lineitems/product-lineitem/lineitem-text | Description | If the record represents a shipping charge, this value is set to
         <kbd class="ph userinput">Shipping</kbd>. Otherwise, it’s set to
         <var class="keyword varname">order/product-lineitems/product-lineitem/lineitem-text</var>. |
| N/A | Type | If the record represents a shipping charge, this picklist value is set to
         <kbd class="ph userinput">Delivery Charge</kbd>. Otherwise, it’s set to <kbd class="ph userinput">Order
         Product</kbd>. |
| order/product-lineitems/product-lineitem/quantity | Quantity |  |
| order/product-lineitems/product-lineitem/net-price | TotalLineAmount |  |
| order/product-lineitems/product-lineitem/position | LineNumber | Records that represent charges are assigned a value starting at
         <kbd class="ph userinput">1000</kbd> so they appear after all order products in lists. |
| order/product-lineitems/product-lineitem/base-price | UnitPrice |  |
| order/product-lineitems/product-lineitem/base-price | ListPrice | This value is only set if the Optional Price Books feature is enabled. It’s needed
        when the OrderItem has no associated PriceBookEntry. |
| N/A | OrderId | This value is set to the ID of the associated original Order record. |
| N/A | OrderDeliveryGroupId | This value is set to the ID of the associated OrderDeliveryGroup record. |
| N/A | PricebookEntryId | This value is set to the ID of the associated PriceBookEntry record. If the Optional
        Price Books feature is enabled, this value isn’t
        set. |
| N/A | Product2Id | This value is set to the ID of the associated Product2 record. |
| order/product-lineitems/product-lineitem/<var class="keyword varname">custom_attribute</var> | <var class="keyword varname">Custom_Attribute</var> | If the Salesforce OrderItem object has a custom field matching a custom attribute on
        the storefront Gift Certificate Line Item, Product Line Item, or Shipping Line Item object,
        the value is copied to the OrderItem record. If the Salesforce OrderItemSummary object also
        has a matching custom field, it’s copied to both records. If a custom field is non-nillable,
        then order data must include a value for the corresponding custom attribute. If the value is
        missing, the integration fails. |

## OrderItemAdjustmentLineItem Object

An OrderItemAdjustmentLineItem record represents the application of a promotion to an     OrderItem record. Thus, an OrderItem record has one associated OrderItemAdjustmentLineItem     record for each promotion that applies to it.

If an order has a TaxLocaleType of Net, then the integration also creates an     OrderItemTaxLineItem record for each OrderItemAdjustmentLineItem record.

| B2C Commerce XSD Value | Salesforce Object Field | Notes |
| --- | --- | --- |
| price-adjustments/price-adjustment/promotion-id | Name |  |
| price-adjustments/price-adjustment/net-price | Amount |  |
| price-adjustments/price-adjustment/tax | TotalTaxAmount |  |
| price-adjustments/price-adjustment/promotion-id | PromotionId |  |
| N/A | Type | This value is set to either <kbd class="ph userinput">Product</kbd> or
         <kbd class="ph userinput">Shipping</kbd>, based on the Type of the OrderItem
        record that the adjustment applies to. |
| N/A | OrderItemId | This value is set to the ID of the OrderItem record that the adjustment applies
        to. |
| N/A | OrderAdjustmentGroupId | This value is set to the ID of the parent OrderAdjustmentGroup record. |

## OrderItemTaxLineItem Object

If an order has a TaxLocaleType of Net, then the integration creates an OrderItemTaxLineItem     record for each OrderItem and OrderItemAdjustmentLineItem record in the order. If an order has a     TaxLocaleType of Gross, then the integration doesn’t create any OrderItemTaxLineItem records for     it.

| B2C Commerce XSD Value | Salesforce Object Field | Notes |
| --- | --- | --- |
| See notes | Name | This value is generated based on the Type of the associated
        OrderItem or OrderItemAdjustmentLineItem record and, if applicable, the
         StockKeepingUnitof the associated Product2:<ul class="ul bulletList">
         <li class="li">OrderItem:<ul class="ul bulletList">
           <li class="li">Order Product- <var class="keyword varname">StockKeepingUnit</var> + "<kbd class="ph userinput"> -
            Tax</kbd>"</li>

           <li class="li">Delivery Charge- <kbd class="ph userinput">"Delivery Charge - Tax"</kbd>
</li>

          </ul>
</li>

         <li class="li">OrderItemAdjustmentLineItem:<ul class="ul bulletList">
           <li class="li">Product- <var class="keyword varname">StockKeepingUnit</var> + "<kbd class="ph userinput"> - Adjustment
             Tax</kbd>"</li>

           <li class="li">Shipping- "<kbd class="ph userinput">Delivery Charge - Adjustment Tax</kbd>"</li>

          </ul>
</li>

        </ul> |
| N/A | Type | This picklist value is always set to <kbd class="ph userinput">Estimated</kbd>. |
| order/product-lineitems/product-lineitem/tax | Amount |  |
| order/product-lineitems/product-lineitem/tax-rate | Rate |  |
| order/order-date | TaxEffectiveDate |  |
| N/A | OrderItemId | If the tax applies to an OrderItem record, this value is set to the ID of that order
        item. If it applies to an OrderItemAdjustmentLineItem record, this value is set to the ID of
        the order item that the adjustment applies to. |
| N/A | OrderItemAdjustmentLineItemId | This value is only set for tax that applies to an OrderItemAdjustmentLineItem
        record. |

## Payment Object

If an order/payments/payment/transaction-type value in the order data is      <kbd class="ph userinput">sale</kbd> or <kbd class="ph userinput">capture</kbd>, then the integration creates a     Payment record for that transaction. If the value starts with <kbd class="ph userinput">auth</kbd>, then     it creates a PaymentAuthorization record. These checks are not case-sensitive .

| B2C Commerce XSD Value | Salesforce Object Field | Notes |
| --- | --- | --- |
| N/A | PaymentGatewayId | This value is set to the ID of the PaymentGateway record whose ExternalReference value
        matches the processor ID value of the order payment instrument associated with the order
        payment transaction. |
| N/A | PaymentGatewayLogId | This value is set to the ID of the PaymentGatewayLog record associated with the
        payment. |
| order/payments/payment/amount | Amount |  |
| N/A | ProcessingMode | This picklist value is always set to <kbd class="ph userinput">External</kbd>. |
| N/A | Status | This picklist value is always set to <kbd class="ph userinput">Processed</kbd>. |
| order/payments/payment/transaction-id | GatewayRefNumber | This value is not required in the order data. The default value is
         <kbd class="ph userinput">null</kbd>. |
| order/customer/customer-email | Email |  |
| order/order-date | Date |  |
| order/payments/payment/transaction-type | Type |  |
| order/billing-address/phone | Phone |  |
|  | PaymentGroupId | This value is set to the ID of the PaymentGroup record associated with the
        payment. |
|  | AccountId | This value is set to the ID of the Account or Person Account record associated with
        the shopper. |
|  | PaymentMethodId | This value is set to the ID of the CardPaymentMethod or DigitalWallet record
        associated with the payment. |
| order/currency | CurrencyIsoCode | This value is only set if the Salesforce org has Multicurrency enabled. |
| order/payments/payment/<var class="keyword varname">custom_attribute</var> or a custom attribute on
        the payment type | <var class="keyword varname">Custom_Attribute</var> | If the Salesforce Payment object has a custom field matching a custom attribute on the
        storefront payment type or order payment transaction object, the value is copied to the
        Payment record. If a custom field is non-nillable, then order data must include a value for
        the corresponding custom attribute. If the value is missing, the integration fails. |

## PaymentAuthorization Object

If an order/payments/payment/transaction-type value in the order data     starts with <kbd class="ph userinput">auth</kbd>, then the integration creates a PaymentAuthorization     record for that transaction. If the value is <kbd class="ph userinput">sale</kbd> or      <kbd class="ph userinput">capture</kbd>, then it creates a Payment record. These checks are not     case-sensitive .

| B2C Commerce XSD Value | Salesforce Object Field | Notes |
| --- | --- | --- |
| N/A | PaymentGatewayId | This value is set to the ID of the PaymentGateway record whose ExternalReference value
        matches the processor ID value of the order payment instrument associated with the order
        payment transaction. |
| N/A | PaymentGatewayLogId | This value is set to the ID of the PaymentGatewayLog record associated with the
        payment authorization. |
| order/payments/payment/amount | Amount |  |
| N/A | ProcessingMode | This picklist value is always set to <kbd class="ph userinput">External</kbd>. |
| N/A | Status | This picklist value is always set to <kbd class="ph userinput">Processed</kbd>. |
| order/payments/payment/transaction-id | GatewayRefNumber | This value is not required in the order data. The default value is
         <kbd class="ph userinput">null</kbd>. |
| (custom attribute) order/payments/payment/authCode | GatewayAuthCode | The default Payment Transaction object in B2C Commerce doesn’t include an
         authCode attribute. To use it, add it as a custom attribute and
        populate it before sending the order data. If you name it authCode, the
        integration automatically copies it to the GatewayAuthCode field. |
| N/A | PaymentGroupId | This value is set to the ID of the PaymentGroup record associated with the payment
        authorization. |
| N/A | AccountId | This value is set to the ID of the Account or Person Account record associated with
        the shopper. |
| N/A | PaymentMethodId | This value is set to the ID of the CardPaymentMethod or DigitalWallet record
        associated with the payment authorization. |
| order/currency | CurrencyIsoCode | This value is only set if the Salesforce org has Multicurrency enabled. |
| order/payments/payment/<var class="keyword varname">custom_attribute</var> or a custom attribute on
        the payment type | <var class="keyword varname">Custom_Attribute</var> | If the Salesforce PaymentAuthorization object has a custom field matching a custom
        attribute on the storefront payment type or order payment transaction object, the value is
        copied to the PaymentAuthorization record. If a custom field is non-nillable, then order
        data must include a value for the corresponding custom attribute. If the value is missing,
        the integration fails. |

## PaymentGatewayLog Object

| B2C Commerce XSD Value | Salesforce Object Field | Notes |
| --- | --- | --- |
| N/A | PaymentGatewayId | This value is set to the ID of the PaymentGateway record whose ExternalReference value
        matches the processor ID value of the order payment instrument associated with the order
        payment transaction. |
| N/A | InteractionStatus | This picklist value is always set to <kbd class="ph userinput">Success</kbd>. |
| order/payments/payment/transaction-type | InteractionType | The default value is <kbd class="ph userinput">Authorization</kbd>. |
| (custom attribute) order/payments/payment/authCode | GatewayAuthCode | The default Payment Transaction object in B2C Commerce doesn’t include an
         authCode attribute. To use it, add it as a custom attribute and
        populate it before sending the order data. If you name it authCode, the
        integration automatically copies it to the GatewayAuthCode field. |
| (custom attribute) order/payments/payment/avsResultCode | GatewayAvsCode | The default Payment Transaction object in B2C Commerce doesn’t include an
         avsResultCode attribute. To use it, add it as a custom attribute and
        populate it before sending the order data. If you name it
        avsResultCode, the integration automatically copies it to the
        GatewayAvsCode field. |
| (custom attribute) order/payments/payment/approvalStatus | GatewayResultCode | The default Payment Transaction object in B2C Commerce doesn’t include an
         approvalStatus field. To use it, add it as a custom attribute and
        populate it before sending the order data. If you name it
         approvalStatus, the integration automatically copies it to the
        GatewayResultCode field. |
| order/payments/payment/<var class="keyword varname">custom_attribute</var> or a custom attribute on
        the payment type | <var class="keyword varname">Custom_Attribute</var> | If the Salesforce PaymentGatewayLog object has a custom field matching a custom
        attribute on the storefront payment type or order payment transaction object, the value is
        copied to the PaymentGatewayLog record. However, the integration copies certain Order
        Payment Transaction custom attributes to standard PaymentGatewayLog fields, as described in
        this table. If a custom field is non-nillable, then order data must include a value for the
        corresponding custom attribute. If the value is missing, the integration fails. |

## PaymentGroup Object

| B2C Commerce XSD Value | Salesforce Object Field | Notes |
| --- | --- | --- |
| N/A | SourceObjectId | This value is set to the ID of the original Order record that the payments in the
        group apply to. |
| order/currency | CurrencyIsoCode | This value is only set if the Salesforce org has Multicurrency enabled. |

## PricebookEntry Object

Salesforce Order Management doesn’t use the PricebookEntry object. It creates a PriceBookEntry     record for each Product2 because the OrderItem object requires a      PricebookEntryId value.

![Note](/docs/resources/img/en-us/230.0?doc_id=images%2Ficon_note.png&folder=order_management_developer_guide)

#### Note

If you turn on the [Optional Price Books feature](https://help.salesforce.com/articleView?id=customize_order_enable_without_pricebooks.htm&amp;language=en_US "HTML (New Window)"), then     Order Management doesn’t create price book entries for product records that it creates from     order data. If you turn off the feature, then you must add price book entries     manually.

| B2C Commerce XSD Value | Salesforce Object Field | Notes |
| --- | --- | --- |
| N/A | Pricebook2Id | This value is set to the ID of the Pricebook2 record for the standard price
        book. |
| N/A | Product2Id | This value is set to the ID of the associated Product2 record. |
| order/product-lineitems/product-lineitem/base-price | UnitPrice | This value is only set when the PriceBookEntry record is created. It isn’t updated
        when an OrderItem associated with the same Product2 is created. |
| order/currency | CurrencyIsoCode | This value is only set if the Salesforce org has Multicurrency enabled. |

## Product2 Object

| B2C Commerce XSD Value | Salesforce Object Field | Notes |
| --- | --- | --- |
| order/product-lineitem/lineitem-text | Description |  |
| order/product-lineitem/product-name | Name |  |
| order/product-lineitem/product-id | StockKeepingUnit | If the product is an electronic gift certificate, this value is set to
         <kbd class="ph userinput">eGiftCertificate</kbd>. |
| order/product-lineitem/product-id | ProductCode | If the product is an electronic gift certificate, this value is set to
         <kbd class="ph userinput">eGiftCertificate</kbd>. |
| N/A | IsActive | The default value is <kbd class="ph userinput">true</kbd>. |

## SalesChannel Object

| B2C Commerce XSD Value | Salesforce Object Field | Notes |
| --- | --- | --- |
| order.domain\_id | Description |  |
| order.domain\_id | SalesChannelName |  |