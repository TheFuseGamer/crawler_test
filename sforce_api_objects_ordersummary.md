# OrderSummary

    Represents the current properties and state of an order. Corresponds to one or
      more order objects, consisting of an original object and any change objects applicable to
      it. This object is available in API version 48.0 and later.

## Supported Calls

<samp class="codeph nolang">create()</samp>,           <samp class="codeph nolang">delete()</samp>,           <samp class="codeph nolang">describeLayout()</samp>, <samp class="codeph nolang">describeSObjects()</samp>, <samp class="codeph nolang">getDeleted()</samp>, <samp class="codeph nolang">getUpdated()</samp>, <samp class="codeph nolang">query()</samp>,           <samp class="codeph nolang">retrieve()</samp>, <samp class="codeph nolang">search()</samp>,           <samp class="codeph nolang">undelete()</samp>, <samp class="codeph nolang">update()</samp>, <samp class="codeph nolang">upsert()</samp>

## Special Access Rules

This object is only available in Salesforce Order Management orgs or if the B2B Commerce on         Lightning Experience license is enabled.

## Fields

| Field | Details |
| --- | --- |
| AccountId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Filter, Group, Nillable, Sort<br>

                    - Description<br>

                        - ID of the account or person account associated with the OrderSummary. It
                      represents the shopper in the storefront.<br>

                        - If the OrderLifeCycleType field on the associated
                      OrderSummary is set to UNMANAGED, then users with the Edit Unmanaged Order
                      Summaries or B2B Commerce Integrator user permission can modify this
                      field. |
| ActiveProcessExceptionCount | - Type<br>

                        - int<br>

                    - Properties<br>

                        - Filter, Group, Nillable, Sort<br>

                    - Description<br>

                        - Total number of active process exceptions on the OrderSummary.<br>

                        - This field is available in API version 50.0 and later. |
| BillingAddress | - Type<br>

                        - address<br>

                    - Properties<br>

                        - Filter, Nillable<br>

                    - Description<br>

                        - Billing address associated with the OrderSummary.<br>

                        - If the OrderLifeCycleType field on the associated
                      OrderSummary is set to UNMANAGED, then users with the Edit Unmanaged Order
                      Summaries or B2B Commerce Integrator user permission can modify this
                      field. |
| BillingCity | - Type<br>

                        - string<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort, Update<br>

                    - Description<br>

                        - Billing address city. |
| BillingCountry | - Type<br>

                        - string<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort, Update<br>

                    - Description<br>

                        - Billing address country. |
| BillingEmailAddress | - Type<br>

                        - email<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort, Update<br>

                    - Description<br>

                        - Email address on the billing address. |
| BillingGeocodeAccuracy | - Type<br>

                        - picklist<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Restricted picklist, Sort, Update<br>

                    - Description<br>

                        - The accuracy of the geocode for the billing address.<br>

                        - Possible values are: <ul class="ul bulletList">
                        <li class="li"><samp class="codeph nolang">Address</samp></li>

                        <li class="li"><samp class="codeph nolang">Block</samp></li>

                        <li class="li"><samp class="codeph nolang">City</samp></li>

                        <li class="li"><samp class="codeph nolang">County</samp></li>

                        <li class="li"><samp class="codeph nolang">ExtendedZip</samp></li>

                        <li class="li"><samp class="codeph nolang">NearAddress</samp></li>

                        <li class="li"><samp class="codeph nolang">Neighborhood</samp></li>

                        <li class="li"><samp class="codeph nolang">State</samp></li>

                        <li class="li"><samp class="codeph nolang">Street</samp></li>

                        <li class="li"><samp class="codeph nolang">Unknown</samp></li>

                        <li class="li"><samp class="codeph nolang">Zip</samp></li>

                      </ul> |
| BillingLatitude | - Type<br>

                        - double<br>

                    - Properties<br>

                        - Create, Filter, Nillable, Sort, Update<br>

                    - Description<br>

                        - Used with BillingLongitude to specify the precise geolocation of the billing
                      address. Acceptable values are numbers between –90 and 90 with up to 15
                      decimal places. |
| BillingLongitude | - Type<br>

                        - double<br>

                    - Properties<br>

                        - Create, Filter, Nillable, Sort, Update<br>

                    - Description<br>

                        - Used with BillingLatitude to specify the precise geolocation of the billing
                      address. Acceptable values are numbers between –90 and 90 with up to 15
                      decimal places. |
| BillingPhoneNumber | - Type<br>

                        - phone<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort, Update<br>

                    - Description<br>

                        - Phone number of the billing address. |
| BillingPostalCode | - Type<br>

                        - string<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort, Update<br>

                    - Description<br>

                        - Billing address postal code. |
| BillingState | - Type<br>

                        - string<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort, Update<br>

                    - Description<br>

                        - Billing address state. |
| BillingStreet | - Type<br>

                        - textarea<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort, Update<br>

                    - Description<br>

                        - Billing address street. |
| BillToContactId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort<br>

                    - Description<br>

                        - ID of the Contact associated with the OrderSummary. It represents the
                      shopper in the storefront when not using person accounts.<br>

                        - If the OrderLifeCycleType field is set to UNMANAGED,
                      then users with the Edit Unmanaged Order Summaries or B2B Commerce Integrator
                      user permission can modify this field.<br>

                        - This field is available in API version 49.0 and later. |
| ChangeOrderId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Filter, Group, Nillable, Sort<br>

                    - Description<br>

                        - Reserved for future use. |
| CurrencyIsoCode | - Type<br>

                        - picklist<br>

                    - Properties<br>

                        - Create, Defaulted on create, Filter, Group, Nillable, Restricted picklist,
                      Sort, Update<br>

                    - Description<br>

                        - Available only for orgs with the multicurrency feature enabled. Contains the
                      ISO code for the currency of the original Order associated with the
                      OrderSummary. The default value is USD.<br>

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
| Description | - Type<br>

                        - textarea<br>

                    - Properties<br>

                        - Create, Nillable, Update<br>

                    - Description<br>

                        - Description of the OrderSummary.<br>

                        - This field can be edited. |
| GrandTotalAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total amount, including adjustments and tax, of the OrderSummary. |
| IsSuspended | - Type<br>

                        - boolean<br>

                    - Properties<br>

                        - Create, Defaulted on create, Filter, Group, Sort, Update<br>

                    - Description<br>

                        - Indicates whether the OrderSummary is suspended. The default value is
                      false.<br>

                        - This field is available in API version 50.0 and later. |
| LastReferencedDate | - Type<br>

                        - dateTime<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - The timestamp for when the current user last viewed a record related to
                      this record. |
| LastViewedDate | - Type<br>

                        - dateTime<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - The timestamp for when the current user last viewed this record. A null
                      value can mean that this record has only been referenced (LastReferencedDate)
                      and not viewed. |
| OrderedDate | - Type<br>

                        - dateTime<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Date of the original order associated with this OrderSummary.<br>

                        - If the OrderLifeCycleType field on the associated
                      OrderSummary is set to UNMANAGED, then users with the Edit Unmanaged Order
                      Summaries or B2B Commerce Integrator user permission can modify this
                      field. |
| OrderLifeCycleType | - Type<br>

                        - picklist<br>

                    - Properties<br>

                        - Filter, Group, Restricted picklist, Sort<br>

                    - Description<br>

                        - Specifies whether the OrderSummary is managed by Salesforce Order Management
                      (MANAGED) or by an external system (UNMANAGED). An unmanaged OrderSummary is
                      stored in Salesforce for reference purposes.<ul class="ul bulletList">
                        <li class="li">Some Order Management APIs reject input records that are associated with
                          unmanaged OrderSummaries.</li>

                        <li class="li">Order Management does not update financial bucket fields on some records
                          that are associated with unmanaged OrderSummaries.</li>

                        <li class="li">A user with the EditUnmanagedOrderSummaries or B2BCommerceIntegrator
                          permission can edit certain fields on objects related to unmanaged
                          OrderSummaries that are normally only accessible via APIs.</li>

                      </ul><br>

                        - Possible values are: <ul class="ul bulletList">
                        <li class="li">
<samp class="codeph nolang">MANAGED</samp>—Managed</li>

                        <li class="li">
<samp class="codeph nolang">UNMANAGED</samp>—Unmanaged</li>

                      </ul><br>

                        - This field is available in API version 49.0 and later. |
| OrderNumber | - Type<br>

                        - string<br>

                    - Properties<br>

                        - Create, Filter, Group, idLookup, Sort, Update<br>

                    - Description<br>

                        - Name of the OrderSummary. |
| OriginalOrderId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Filter, Group, Sort<br>

                    - Description<br>

                        - ID of the original order associated with this OrderSummary. |
| OwnerId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Create, Defaulted on create, Filter, Group, Sort, Update<br>

                    - Description<br>

                        - The ID of the user who currently owns this OrderSummary. Default value is
                      the user logged in to the API to perform the create. |
| PoNumber | - Type<br>

                        - string<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort, Update<br>

                    - Description<br>

                        - Purchase order number associated with this OrderSummary.<br>

                        - If the OrderLifeCycleType field on the associated
                      OrderSummary is set to UNMANAGED, then users with the Edit Unmanaged Order
                      Summaries or B2B Commerce Integrator user permission can modify this
                      field. |
| RoutingAttempts | - Type<br>

                        - int<br>

                    - Properties<br>

                        - Create, Defaulted on create, Filter, Group, Nillable, Sort, Update<br>

                    - Description<br>

                        - The number of attempts that have been made to route the order summary to
                      inventory locations.<br>

                        - This field is available in API version 51.0 and later. |
| SalesChannelId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Filter, Group, Nillable, Sort<br>

                    - Description<br>

                        - ID of the SalesChannel associated with this OrderSummary.<br>

                        - If the OrderLifeCycleType field on the associated
                      OrderSummary is set to UNMANAGED, then users with the Edit Unmanaged Order
                      Summaries or B2B Commerce Integrator user permission can modify this
                      field. |
| SalesStoreId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Filter, Group, Nillable, Sort<br>

                    - Description<br>

                        - ID of the RetailStore or WebStore associated with this OrderSummary.<br>

                        - If the OrderLifeCycleType field on the associated
                      OrderSummary is set to UNMANAGED, then users with the Edit Unmanaged Order
                      Summaries or B2B Commerce Integrator user permission can modify this
                      field.<br>

                        - This field is only available in Salesforce B2B Commerce orgs. |
| Status | - Type<br>

                        - picklist<br>

                    - Properties<br>

                        - Create, Defaulted on create, Filter, Group, Nillable, Sort, Update<br>

                    - Description<br>

                        - Status of the order summary. Unlike the Status and Status Category fields on
                      the order and FulfillmentOrder objects, this field is optional.<br>

                        - We recommend that you use the same values in this picklist that you use in
                      the Status picklist for the order object. |
| TaxLocaleType | - Type<br>

                        - picklist<br>

                    - Properties<br>

                        - Filter, Group, Nillable, Restricted picklist, Sort<br>

                    - Description<br>

                        - The system used to handle tax on the original Order associated with the
                      OrderSummary. Gross usually applies to taxes like value-added tax (VAT), and
                      Net usually applies to taxes like sales tax.<br>

                        - Possible values are: <ul class="ul bulletList">
                        <li class="li">
<samp class="codeph nolang">Gross</samp> (displays most prices and
                          taxes as combined values)</li>

                        <li class="li">
<samp class="codeph nolang">Net</samp> (displays most prices and taxes
                          as separate values)</li>

                      </ul><br>

                        - If the OrderLifeCycleType field on the associated
                      OrderSummary is set to UNMANAGED, then users with the Edit Unmanaged Order
                      Summaries or B2B Commerce Integrator user permission can modify this
                      field.<br>

                        - This field is available in API version 49.0 and later. |
| TotalAdjDelivery​AmtWithTax | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total amount of all OrderItemSummaries of type code Charge belonging to this
                      OrderSummary, inclusive of adjustments and tax. This amount is equal to
                      TotalAdjustedDeliveryAmount + TotalAdjustedDeliveryTaxAmount.<br>

                        - This field is available in API version 49.0 and later. |
| TotalAdjDistAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total of distributed adjustments applied to OrderItemSummaries belonging to
                      this OrderSummary. This amount is equal to TotalProductAdjDistAmount plus
                      TotalDeliveryAdjDistAmount. |
| TotalAdjDistAmountWithTax | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total of distributed adjustments applied to OrderItemSummaries belonging to
                      this OrderSummary, inclusive of tax. This amount is equal to
                      TotalAdjDistAmount plus TotalAdjDistTaxAmount.<br>

                        - This field is available in API version 49.0 and later. |
| TotalAdjDistTaxAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Tax on the TotalAdjDistAmount. |
| TotalAdjProduct​AmtWithTax | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total amount of all OrderItemSummaries of type code Product belonging to
                      this OrderSummary, inclusive of adjustments and tax. This amount is equal to
                      TotalAdjustedProductAmount plus TotalAdjustedProductTaxAmount.<br>

                        - This field is available in API version 49.0 and later. |
| TotalAdjusted​DeliveryAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total, including adjustments but not tax, of all OrderItemSummaries of type
                      code Charge belonging to this OrderSummary. |
| TotalAdjusted​DeliveryTaxAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Tax on the TotalAdjustedDeliveryAmount. |
| TotalAdjustedProduct​Amount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total, including adjustments but not tax, of all OrderItemSummaries of type
                      code Product belonging to this OrderSummary. |
| TotalAdjustedProduct​TaxAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Tax on the TotalAdjustedProductAmount. |
| TotalAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total, including adjustments but not tax, of all OrderItemSummaries
                      belonging to this OrderSummary. Equal to TotalAdjustedProductAmount plus
                      TotalAdjustedDeliveryAmount. |
| TotalDeliveryAdj​DistAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total of all order-level price adjustments applied to OrderItemSummaries of
                      type code Charge belonging to this OrderSummary. This value includes
                      OrderItemAdjustmentLineSummaries that belong to OrderAdjustmentGroupSummaries
                      of type Header. |
| TotalDeliveryAdj​DistAmtWithTax | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total of all order-level price adjustments applied to OrderItemSummaries of
                      type code Charge belonging to this OrderSummary, inclusive of tax. This value
                      includes OrderItemAdjustmentLineSummaries that belong to
                      OrderAdjustmentGroupSummaries of type Header. It is equal to
                      TotalDeliveryAdjDistAmount + TotalDeliveryAdjDistTaxAmount.<br>

                        - This field is available in API version 49.0 and later. |
| TotalDeliveryAdj​DistTaxAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Tax on the TotalDeliveryAdjDistAmount. |
| TotalProductAdj​DistAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total of all order-level price adjustments applied to OrderItemSummaries of
                      type code Product belonging to this OrderSummary. This value includes
                      OrderItemAdjustmentLineSummaries that belong to OrderAdjustmentGroupSummaries
                      of type Header. |
| TotalProductAdj​DistAmtWithTax | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total of all order-level price adjustments applied to OrderItemSummaries of
                      type code Product belonging to this OrderSummary, inclusive of tax. This value
                      includes OrderItemAdjustmentLineSummaries that belong to
                      OrderAdjustmentGroupSummaries of type Header. It is equal to
                      TotalProductAdjDistAmount + TotalProductAdjDistTaxAmount.<br>

                        - This field is available in API version 49.0 and later. |
| TotalProductAdj​DistTaxAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Tax on the TotalProductAdjDistAmount. |
| TotalTaxAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total tax on all OrderItemSummaries belonging to this OrderSummary. Equal to
                      TotalAdjustedDeliveryTaxAmount plus TotalAdjustedProductTaxAmount. |

## Associated Objects

This object has the following associated objects. Unless noted, they are available in the         same API version as this object.

          - OrderSummaryFeed

              - Feed tracking is available for the object.

          - OrderSummaryOwnerSharingRule

              - Sharing rules are available for the object.

          - OrderSummaryShare

              - Sharing is available for the object.

#### See Also

- [FulfillmentOrder](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_fulfillmentorder.htm "Represents a group of products and delivery charges on a single order that share the same fulfillment location, delivery method, and recipient. The FulfillmentOrderLineItems belonging to a FulfillmentOrder are associated with OrderItemSummary objects belonging to a single OrderSummary. This object is available in API version 48.0 and later.")
- [OrderItemSummary](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_orderitemsummary.htm "Represents the current properties and state of a product or charge on an OrderSummary. Corresponds to one or more order item objects, consisting of an original object and any change objects applicable to it. This object is available in API version 48.0 and later.")
- [OrderPaymentSummary](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_orderpaymentsummary.htm "Represents the current properties and state of payments using a single payment method that are applied to one OrderSummary. This object is available in API version 48.0 and later.")
- [SalesChannel](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_saleschannel.htm "Represents the origin of an order. For example, a web storefront, physical store, marketplace, or mobile app. Usually you will set up a SalesChannel for each Site in your B2C Commerce implementation. This object is available in API version 48.0 and later.")