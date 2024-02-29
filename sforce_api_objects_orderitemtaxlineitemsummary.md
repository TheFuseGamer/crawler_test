# OrderItemTaxLineItemSummary

    Represents the current tax on an OrderItemSummary or
      OrderItemAdjustmentLineSummary. Corresponds to one or more order item tax line items,
      consisting of an original object and any change objects applicable to it. This object is
    available in API version 48.0 and later.

## Supported Calls

         <samp class="codeph nolang">delete()</samp>, <samp class="codeph nolang">describeLayout()</samp>, <samp class="codeph nolang">describeSObjects()</samp>, <samp class="codeph nolang">getDeleted()</samp>, <samp class="codeph nolang">getUpdated()</samp>, <samp class="codeph nolang">query()</samp>,           <samp class="codeph nolang">retrieve()</samp>, <samp class="codeph nolang">undelete()</samp>,             <samp class="codeph nolang">update()</samp>       

## Special Access Rules

This object is only available in Salesforce Order Management orgs or if the B2B Commerce on         Lightning Experience license is enabled.

## Fields

| Field | Details |
| --- | --- |
| Amount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Sort<br>

                    - Description<br>

                        - Amount of tax represented by the OrderItemTaxLineItemSummary.<br>

                        - If the OrderLifeCycleType field on the associated
                      OrderSummary is set to UNMANAGED, then users with the Edit Unmanaged Order
                      Summaries or B2B Commerce Integrator user permission can modify this
                      field. |
| CurrencyIsoCode | - Type<br>

                        - picklist<br>

                    - Properties<br>

                        - Defaulted on create, Filter, Group, Restricted picklist, Sort<br>

                    - Description<br>

                        - ISO code for the currency of the OrderSummary associated with the
                      OrderItemTaxLineItemSummary. The default value is USD.<br>

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

                        - Nillable, Update<br>

                    - Description<br>

                        - Description of the OrderItemTaxLineItemSummary.<br>

                        - This field can be edited. |
| Name | - Type<br>

                        - string<br>

                    - Properties<br>

                        - Filter, Group, idLookup, Sort, Update<br>

                    - Description<br>

                        - Name of the OrderItemTaxLineItemSummary. |
| OrderItemAdjustmentLine​SummaryId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Filter, Group, Nillable, Sort<br>

                    - Description<br>

                        - If this object represents tax on an adjustment, this value is the ID of the
                      OrderItemAdjustmentLineSummary to which the tax applies. If this value is
                      null, the adjustment applies to an OrderItemSummary. |
| OrderItemSummaryId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Filter, Group, Sort<br>

                    - Description<br>

                        - If this object represents tax on an OrderItemSummary, this value is the ID
                      of that OrderItemSummary. If this object represents tax on an adjustment, this
                      value is the ID of the OrderItemSummary to which the adjustment applies. |
| OrderSummaryId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Filter, Group, Sort<br>

                    - Description<br>

                        - ID of the OrderSummary that the associated OrderItemSummary or
                      OrderItemAdjustmentLineSummary belongs to. |
| OriginalOrderItemTax​LineItemId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Filter, Group, Nillable, Sort<br>

                    - Description<br>

                        - ID of the original order item tax line item associated with this summary
                      object. Nillable=true only if the associated order summary is unmanaged. For
                      managed order summaries, nillable=false. |
| Rate | - Type<br>

                        - percent<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Tax rate used to calculate the Amount.<br>

                        - If the OrderLifeCycleType field on the associated
                      OrderSummary is set to UNMANAGED, then users with the Edit Unmanaged Order
                      Summaries or B2B Commerce Integrator user permission can modify this
                      field. |
| TaxEffectiveDate | - Type<br>

                        - date<br>

                    - Properties<br>

                        - Filter, Group, Sort<br>

                    - Description<br>

                        - Date on which the Amount was calculated. Important due to tax rate changes
                      over time.<br>

                        - If the OrderLifeCycleType field on the associated
                      OrderSummary is set to UNMANAGED, then users with the Edit Unmanaged Order
                      Summaries or B2B Commerce Integrator user permission can modify this
                      field. |
| Type | - Type<br>

                        - picklist<br>

                    - Properties<br>

                        - Filter, Group, Restricted picklist, Sort<br>

                    - Description<br>

                        - Indicates whether the Amount is actual or estimated.<br>

                        - Possible values are: <ul class="ul bulletList">
                        <li class="li"><samp class="codeph nolang">Actual</samp></li>

                        <li class="li"><samp class="codeph nolang">Estimated</samp></li>

                      </ul><br>

                        - If the OrderLifeCycleType field on the associated
                      OrderSummary is set to UNMANAGED, then users with the Edit Unmanaged Order
                      Summaries or B2B Commerce Integrator user permission can modify this
                      field. |

#### See Also

- [FulfillmentOrderItemTax](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_fulfillmentorderitemtax.htm "Represents the tax on a FulfillmentOrderLineItem or FulfillmentOrderItemAdjustment. Corresponds to an OrderItemTaxLineItemSummary. This object is available in API version 48.0 and later.")
- [OrderItemAdjustmentLineSummary](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_orderitemadjustmentlinesummary.htm "Represents the current properties and state of price adjustments on an OrderItemSummary. Corresponds to one or more order item adjustment line item objects, consisting of an original object and any change objects applicable to it. This object is available in API version 48.0 and later.")
- [OrderItemSummary](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_orderitemsummary.htm "Represents the current properties and state of a product or charge on an OrderSummary. Corresponds to one or more order item objects, consisting of an original object and any change objects applicable to it. This object is available in API version 48.0 and later.")