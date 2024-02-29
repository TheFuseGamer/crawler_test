# OrderItemAdjustmentLineSummary

    Represents the current properties and state of price adjustments on an
      OrderItemSummary. Corresponds to one or more order item adjustment line item objects,
      consisting of an original object and any change objects applicable to it. This object is
    available in API version 48.0 and later.

## Supported Calls

         <samp class="codeph nolang">create()</samp>, <samp class="codeph nolang">delete()</samp>, <samp class="codeph nolang">describeLayout()</samp>, <samp class="codeph nolang">describeSObjects()</samp>, <samp class="codeph nolang">getDeleted()</samp>, <samp class="codeph nolang">getUpdated()</samp>, <samp class="codeph nolang">query()</samp>,           <samp class="codeph nolang">retrieve()</samp>, <samp class="codeph nolang">undelete()</samp>,           <samp class="codeph nolang">update()</samp>,           <samp class="codeph nolang">upsert()</samp>       

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

                        - Amount, not including tax, of the OrderItemAdjustmentLineSummary.<br>

                        - If the OrderLifeCycleType field on the associated
                      OrderSummary is set to UNMANAGED, then users with the Edit Unmanaged Order
                      Summaries or B2B Commerce Integrator user permission can modify this
                      field. |
| CurrencyIsoCode | - Type<br>

                        - picklist<br>

                    - Properties<br>

                        - Defaulted on create, Filter, Group, Restricted picklist, Sort<br>

                    - Description<br>

                        - ISO code for the currency of the OrderItemSummary to which the adjustment
                      applies. The default value is USD.<br>

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

                        - Description of the OrderItemAdjustmentLineSummary.<br>

                        - This field can be edited. |
| Name | - Type<br>

                        - string<br>

                    - Properties<br>

                        - Create, Filter, Group, idLookup, Sort, Update<br>

                    - Description<br>

                        - Name of the OrderItemAdjustmentLineSummary. |
| OrderAdjustmentGroup​SummaryId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Filter, Group, Nillable, Sort<br>

                    - Description<br>

                        - If this object belongs to an OrderAdjustmentGroupSummary, this value is the
                      ID of that OrderAdjustmentGroupSummary. |
| OrderItemSummaryId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Filter, Group, Sort<br>

                    - Description<br>

                        - ID of the OrderItemSummary to which the OrderItemAdjustmentLineSummary
                      applies. |
| OrderSummaryId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Filter, Group, Sort<br>

                    - Description<br>

                        - ID of the OrderSummary associated with the OrderItemSummary to which this
                      OrderItemAdjustmentLineSummary applies. |
| OriginalOrderItem​AdjustmentLineItemId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Filter, Group, Nillable, Sort<br>

                    - Description<br>

                        - ID of the original OrderItemAdjustmentLine associated with this summary
                      object. Nillable=true only if the associated order summary is unmanaged. For
                      managed order summaries, nillable=false. |
| TotalAmtWithTax | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total amount of the adjustment, inclusive of tax. This amount is equal to
                      Amount + TotalTaxAmount.<br>

                        - This field is available in API version 49.0 and later. |
| TotalTaxAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Tax on the Amount. |

#### See Also

- [OrderItemSummary](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_orderitemsummary.htm "Represents the current properties and state of a product or charge on an OrderSummary. Corresponds to one or more order item objects, consisting of an original object and any change objects applicable to it. This object is available in API version 48.0 and later.")
- [OrderItemTaxLineItemSummary](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_orderitemtaxlineitemsummary.htm "Represents the current tax on an OrderItemSummary or OrderItemAdjustmentLineSummary. Corresponds to one or more order item tax line items, consisting of an original object and any change objects applicable to it. This object is available in API version 48.0 and later.")