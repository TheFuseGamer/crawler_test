# OrderAdjustmentGroupSummary

    Represents the current properties and state of a group of related price
      adjustments. Associated with a set of OrderItemAdjustmentLineSummaries that apply to
      OrderItemSummaries belonging to one OrderSummary. Corresponds to one or more order adjustment
      group objects, consisting of an original object and any change objects applicable to it.
    This object is available in API version 48.0 and later.

An OrderAdjustmentGroupSummary can represent an adjustment to an entire order as a group of         adjustments to each of its products. For example, representing “10% off the order” as a set         of 10% off adjustments to each product on the order. It can also represent an adjustment         that applies to a subset of the products on an order. For example, representing “buy one,         get one 50% off” as a 25% off adjustment to each of two products.

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
                      adjustments in the group. The default value is USD.<br>

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

                        - Description of the OrderAdjustmentGroupSummary.<br>

                        - This field can be edited. |
| GrandTotalAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total, including tax, of the associated
                      OrderItemAdjustmentLineSummaries. |
| Name | - Type<br>

                        - string<br>

                    - Properties<br>

                        - Create, Filter, Group, idLookup, Sort, Update<br>

                    - Description<br>

                        - Name of the OrderAdjustmentGroupSummary. |
| OrderSummaryId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Filter, Group, Sort<br>

                    - Description<br>

                        - ID of the OrderSummary associated with the OrderAdjustmentGroupSummary. |
| OriginalOrderAdjGroupId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Filter, Group, Nillable, Sort<br>

                    - Description<br>

                        - ID of the original OrderAdjustmentGroup associated with this summary object.
                      Nillable=true only if the associated order summary is unmanaged. For managed
                      order summaries, nillable=false. |
| TotalAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total, not including tax, of the associated
                      OrderItemAdjustmentIineSummaries. |
| TotalTaxAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Tax on the TotalAmount. |
| Type | - Type<br>

                        - picklist<br>

                    - Properties<br>

                        - Filter, Group, Restricted picklist, Sort<br>

                    - Description<br>

                        - Type of the OrderAdjustmentGroupSummary. Header represents an order-level
                      adjustment with an OrderItemAdjustmentLineSummary for each OrderItemSummary on
                      the OrderSummary. SplitLine represents any other related set of
                      OrderItemAdjustmentLineSummaries.<br>

                        - Possible values are: <ul class="ul bulletList">
                        <li class="li"><samp class="codeph nolang">Header</samp></li>

                        <li class="li"><samp class="codeph nolang">SplitLine</samp></li>

                      </ul><br>

                        - If the OrderLifeCycleType field on the associated
                      OrderSummary is set to UNMANAGED, then users with the Edit Unmanaged Order
                      Summaries or B2B Commerce Integrator user permission can modify this
                      field. |

#### See Also

- [OrderItemAdjustmentLineSummary](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_orderitemadjustmentlinesummary.htm "Represents the current properties and state of price adjustments on an OrderItemSummary. Corresponds to one or more order item adjustment line item objects, consisting of an original object and any change objects applicable to it. This object is available in API version 48.0 and later.")