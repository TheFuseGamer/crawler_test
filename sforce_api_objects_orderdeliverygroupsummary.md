# OrderDeliveryGroupSummary

    Represents the current properties and state of a group of OrderItemSummaries,
      belonging to one OrderSummary, to be fulfilled using the same delivery method and delivered to
      the same address. A single shipment can include them all, but that is not guaranteed.
      Corresponds to one or more order delivery group objects, consisting of an original object and
      any change objects applicable to it. This object is available in API version 48.0 and
    later.

## Supported Calls

<samp class="codeph nolang">create()</samp>,           <samp class="codeph nolang">delete()</samp>,           <samp class="codeph nolang">describeLayout()</samp>, <samp class="codeph nolang">describeSObjects()</samp>, <samp class="codeph nolang">getDeleted()</samp>, <samp class="codeph nolang">getUpdated()</samp>, <samp class="codeph nolang">query()</samp>,           <samp class="codeph nolang">retrieve()</samp>, <samp class="codeph nolang">undelete()</samp>,           <samp class="codeph nolang">update()</samp>,           <samp class="codeph nolang">upsert()</samp>       

## Special Access Rules

This object is only available in Salesforce Order Management orgs or if the B2B Commerce on         Lightning Experience license is enabled.

## Fields

| Field | Details |
| --- | --- |
| CurrencyIsoCode | - Type<br>

                        - picklist<br>

                    - Properties<br>

                        - Defaulted on create, Filter, Group, Restricted picklist, Sort<br>

                    - Description<br>

                        - ISO code for the currency of the OrderSummary associated with the
                      OrderDeliveryGroupSummary. The default value is USD.<br>

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
| DeliverToAddress | - Type<br>

                        - address<br>

                    - Properties<br>

                        - Filter, Nillable<br>

                    - Description<br>

                        - Address of the recipient.<br>

                        - If the OrderLifeCycleType field on the associated
                      OrderSummary is set to UNMANAGED, then users with the Edit Unmanaged Order
                      Summaries or B2B Commerce Integrator user permission can modify this
                      field. |
| DeliverToCity | - Type<br>

                        - string<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort, Update<br>

                    - Description<br>

                        - Recipient address city. |
| DeliverToCountry | - Type<br>

                        - string<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort, Update<br>

                    - Description<br>

                        - Recipient address country. |
| DeliverTo​GeocodeAccuracy | - Type<br>

                        - picklist<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Restricted picklist, Sort, Update<br>

                    - Description<br>

                        - Accuracy of the geocode for the recipient address.<br>

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
| DeliverToLatitude | - Type<br>

                        - double<br>

                    - Properties<br>

                        - Create, Filter, Nillable, Sort, Update<br>

                    - Description<br>

                        - Used with FulfilledToLongitude to specify the precise geolocation of the
                      recipient address. Acceptable values are numbers between –90 and 90 with up to
                      15 decimal places. |
| DeliverToLongitude | - Type<br>

                        - double<br>

                    - Properties<br>

                        - Create, Filter, Nillable, Sort, Update<br>

                    - Description<br>

                        - Used with FulfilledToLatitude to specify the precise geolocation of the
                      recipient address. Acceptable values are numbers between –90 and 90 with up to
                      15 decimal places. |
| DeliverToName | - Type<br>

                        - string<br>

                    - Properties<br>

                        - Create, Filter, Group, Sort, Update<br>

                    - Description<br>

                        - Name on the recipient address.<br>

                        - If the OrderLifeCycleType field on the associated
                      OrderSummary is set to UNMANAGED, then users with the Edit Unmanaged Order
                      Summaries or B2B Commerce Integrator user permission can modify this
                      field. |
| DeliverToPostalCode | - Type<br>

                        - string<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort, Update<br>

                    - Description<br>

                        - Recipient address postal code. |
| DeliverToState | - Type<br>

                        - string<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort, Update<br>

                    - Description<br>

                        - Recipient address state. |
| DeliverToStreet | - Type<br>

                        - textarea<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort, Update<br>

                    - Description<br>

                        - Recipient address street. |
| DeliveryInstructions | - Type<br>

                        - textarea<br>

                    - Properties<br>

                        - Create, Nillable, Update<br>

                    - Description<br>

                        - Special instructions for the delivery.<br>

                        - If the OrderLifeCycleType field on the associated
                      OrderSummary is set to UNMANAGED, then users with the Edit Unmanaged Order
                      Summaries or B2B Commerce Integrator user permission can modify this
                      field. |
| Description | - Type<br>

                        - textarea<br>

                    - Properties<br>

                        - Create, Nillable, Update<br>

                    - Description<br>

                        - Description of the OrderDeliveryGroupSummary.<br>

                        - This field can be edited. |
| DesiredDeliveryDate | - Type<br>

                        - dateTime<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Desired date for delivery. This field is informational, available for
                      customizations.<br>

                        - If the OrderLifeCycleType field on the associated
                      OrderSummary is set to UNMANAGED, then users with the Edit Unmanaged Order
                      Summaries or B2B Commerce Integrator user permission can modify this
                      field. |
| EmailAddress | - Type<br>

                        - email<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort, Update<br>

                    - Description<br>

                        - Email address of the recipient.<br>

                        - If the OrderLifeCycleType field on the associated
                      OrderSummary is set to UNMANAGED, then users with the Edit Unmanaged Order
                      Summaries or B2B Commerce Integrator user permission can modify this
                      field. |
| GiftMessage | - Type<br>

                        - textarea<br>

                    - Properties<br>

                        - Create, Nillable, Update<br>

                    - Description<br>

                        - Gift message to include.<br>

                        - If the OrderLifeCycleType field on the associated
                      OrderSummary is set to UNMANAGED, then users with the Edit Unmanaged Order
                      Summaries or B2B Commerce Integrator user permission can modify this
                      field. |
| GrandTotalAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total, including adjustments and tax, of the delivery charges associated
                      with the OrderDeliveryGroupSummary. This value only includes
                      OrderItemSummaries of type code Charge. |
| IsGift | - Type<br>

                        - boolean<br>

                    - Properties<br>

                        - Defaulted on create, Filter, Group, Sort<br>

                    - Description<br>

                        - Indicates whether the OrderDeliveryGroupSummary represents a gift.<br>

                        - If the OrderLifeCycleType field on the associated
                      OrderSummary is set to UNMANAGED, then users with the Edit Unmanaged Order
                      Summaries or B2B Commerce Integrator user permission can modify this
                      field. |
| OrderDeliveryGroup​SummaryNumber | - Type<br>

                        - string<br>

                    - Properties<br>

                        - Autonumber, Defaulted on create, Filter, idLookup, Sort<br>

                    - Description<br>

                        - ID of the OrderDeliveryGroupSummary. |
| OrderDeliveryMethodId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Filter, Group, Sort<br>

                    - Description<br>

                        - ID of the order delivery method specified for the
                      OrderDeliveryGroupSummary.<br>

                        - If the OrderLifeCycleType field on the associated
                      OrderSummary is set to UNMANAGED, then users with the Edit Unmanaged Order
                      Summaries or B2B Commerce Integrator user permission can modify this
                      field. |
| OrderSummaryId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Filter, Group, Sort<br>

                    - Description<br>

                        - ID of the OrderSummary associated with the OrderDeliveryGroupSummary. |
| OriginalOrderDelivery​GroupId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Filter, Group, Nillable, Sort<br>

                    - Description<br>

                        - ID of the original order delivery group associated with this summary object.
                      Nillable=true only if the associated order summary is unmanaged. For managed
                      order summaries, nillable=false. |
| PhoneNumber | - Type<br>

                        - phone<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort, Update<br>

                    - Description<br>

                        - Phone number of the recipient.<br>

                        - If the OrderLifeCycleType field on the associated
                      OrderSummary is set to UNMANAGED, then users with the Edit Unmanaged Order
                      Summaries or B2B Commerce Integrator user permission can modify this
                      field. |
| PromisedDeliveryDate | - Type<br>

                        - dateTime<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Promised date for delivery. This field is informational, available for
                      customizations.<br>

                        - If the OrderLifeCycleType field on the associated
                      OrderSummary is set to UNMANAGED, then users with the Edit Unmanaged Order
                      Summaries or B2B Commerce Integrator user permission can modify this
                      field. |
| TotalAdjustmentAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total price adjustments applied to delivery charges associated with the
                      OrderDeliveryGroupSummary. This value only includes adjustments to
                      OrderItemSummaries of type code Charge. |
| TotalAdjustment​AmtWithTax | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total amount of the price adjustments applied to the delivery charges
                      associated with the OrderDeliveryGroupSummary, inclusive of tax. This amount
                      is equal to TotalAdjustmentAmount + TotalAdjustmentTaxAmount.<br>

                        - This field is available in API version 49.0 and later. |
| TotalAdjustment​TaxAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Tax on the TotalAdjustmentAmount. |
| TotalAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total, including adjustments but not tax, of the delivery charges associated
                      with the OrderDeliveryGroupSummary. This value only includes adjustments to
                      OrderItemSummaries of type code Charge. |
| TotalLineAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total, not including adjustments or tax, of the delivery charges associated
                      with the OrderDeliveryGroupSummary. |
| TotalLineAmt​WithTax | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total of the delivery charges associated with the OrderDeliveryGroupSummary,
                      inclusive of tax. This amount is equal to TotalLineAmount +
                      TotalLineTaxAmount.<br>

                        - This field is available in API version 49.0 and later. |
| TotalLineTaxAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Tax on the TotalLineAmount. |
| TotalTaxAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Tax on the TotalAmount. |

#### See Also

- [OrderItemSummary](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_orderitemsummary.htm "Represents the current properties and state of a product or charge on an OrderSummary. Corresponds to one or more order item objects, consisting of an original object and any change objects applicable to it. This object is available in API version 48.0 and later.")