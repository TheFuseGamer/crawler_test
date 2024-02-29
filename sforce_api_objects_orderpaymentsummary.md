# OrderPaymentSummary

    Represents the current properties and state of payments using a single payment
      method that are applied to one OrderSummary. This object is available in API version 48.0
    and later.

Unlike most summary objects, an OrderPaymentSummary is not related to a similarly named         order payment object. Instead, it combines values from multiple payment objects that use the         same payment method and apply to the same OrderSummary.

## Supported Calls

<samp class="codeph nolang">create()</samp>,           <samp class="codeph nolang">delete()</samp>,           <samp class="codeph nolang">describeLayout()</samp>, <samp class="codeph nolang">describeSObjects()</samp>, <samp class="codeph nolang">getDeleted()</samp>, <samp class="codeph nolang">getUpdated()</samp>, <samp class="codeph nolang">query()</samp>,           <samp class="codeph nolang">retrieve()</samp>, <samp class="codeph nolang">search()</samp>,           <samp class="codeph nolang">undelete()</samp>, <samp class="codeph nolang">update()</samp>,           <samp class="codeph nolang">upsert()</samp>       

## Special Access Rules

This object is only available in Salesforce Order Management orgs or if the B2B Commerce on         Lightning Experience license is enabled.

## Fields

| Field | Details |
| --- | --- |
| AuthorizationAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Amount of the OrderPaymentSummary that has been authorized. |
| AuthorizationReversal​Amount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Amount of the AuthorizationAmount that has been reversed. |
| AvailableToCaptureAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Amount of the OrderPaymentSummary that is available to be captured. Equal to
                      AuthorizationAmount minus (CapturedAmount and PendingCaptureAmount and
                      PendingReverseAuthAmount). |
| AvailableToRefundAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Amount of the OrderPaymentSummary that is available to be refunded. Equal to
                      CapturedAmount minus (RefundedAmount and PendingCaptureAmount and
                      PendingRefundAmount). |
| BalanceAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total balance of all payments associated with this summary object. |
| CapturedAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Amount of the OrderPaymentSummary that has been captured. |
| CurrencyIsoCode | - Type<br>

                        - picklist<br>

                    - Properties<br>

                        - Create, Defaulted on create, Filter, Group, Nillable, Restricted picklist,
                      Sort, Update<br>

                    - Description<br>

                        - Available only for orgs with the multicurrency feature enabled. Contains the
                      ISO code for the currency of the OrderSummary associated with the
                      OrderPaymentSummary. Order Management APIs and actions that create an
                      OrderPaymentSummary for an OrderSummary set this value. The default value is
                      USD.<br>

                        - Possible values are: <ul class="ul bulletList">
                        <li class="li">
<samp class="codeph nolang">DKK</samp>—Danish Krone</li>

                        <li class="li">
<samp class="codeph nolang">EUR</samp>—Euro</li>

                        <li class="li">
<samp class="codeph nolang">GBP</samp>—British Pound</li>

                        <li class="li">
<samp class="codeph nolang">USD</samp>—U.S. Dollar</li>

                      </ul><br>

                        - This field is available in API version 49.0 and later. |
| FullName | - Type<br>

                        - string<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort, Update<br>

                    - Description<br>

                        - The full name of the payment method user. |
| LastPaymentGateway​LogId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Filter, Group, Nillable, Sort<br>

                    - Description<br>

                        - ID of the most recent payment gateway log associated with the
                      OrderPaymentSummary. |
| LastPaymentGateway​Message | - Type<br>

                        - string<br>

                    - Properties<br>

                        - Create, Filter, Nillable, Sort, Update<br>

                    - Description<br>

                        - The most recent message received from the payment gateway associated with
                      the OrderPaymentSummary. |
| LastReferencedDate | - Type<br>

                        - dateTime<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Timestamp for when the current user last viewed a record related to this
                      record.<br>

                        - This field is available in API version 49.0 and later. |
| LastViewedDate | - Type<br>

                        - dateTime<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Timestamp for when the current user last viewed this record. A null value
                      can mean that this record has only been referenced (LastReferencedDate) and
                      not viewed.<br>

                        - This field is available in API version 49.0 and later. |
| Method | - Type<br>

                        - string<br>

                    - Properties<br>

                        - Create, Filter, Group, idLookup, Sort, Update<br>

                    - Description<br>

                        - Name of the OrderPaymentSummary. |
| OrderSummaryId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Filter, Group, Sort<br>

                    - Description<br>

                        - ID of the OrderSummary associated with the OrderPaymentSummary. |
| OwnerId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Create, Defaulted on create, Filter, Group, Sort, Update<br>

                    - Description<br>

                        - The ID of the user who currently owns this OrderPaymentSummary. Default
                      value is the user logged in to the API to perform the create. |
| PaymentMethodId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Filter, Group, Nillable, Sort<br>

                    - Description<br>

                        - ID of the payment method associated with this OrderPaymentSummary. |
| PendingAuthorization​Amount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Amount of the OrderPaymentSummary that is pending authorization. |
| PendingCaptureAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Amount of the OrderPaymentSummary that is pending capture. |
| PendingRefundAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Amount of the OrderPaymentSummary that is pending refund. |
| PendingReverseAuth​Amount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Amount of the AuthorizationAmount that is pending reversal. |
| RefundedAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Amount of the OrderPaymentSummary that has been refunded. |
| Type | - Type<br>

                        - string<br>

                    - Properties<br>

                        - Filter, Group, Sort<br>

                    - Description<br>

                        - The payment method type associated with the OrderPaymentSummary. For
                      example, <samp class="codeph nolang">visa</samp>, <samp class="codeph nolang">mastercard</samp>, <samp class="codeph nolang">check</samp>, or <samp class="codeph nolang">giftcard</samp>. |

#### See Also

- [OrderSummary](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_ordersummary.htm "Represents the current properties and state of an order. Corresponds to one or more order objects, consisting of an original object and any change objects applicable to it. This object is available in API version 48.0 and later.")