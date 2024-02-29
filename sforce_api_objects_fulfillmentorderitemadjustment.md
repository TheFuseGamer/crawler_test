# FulfillmentOrderItemAdjustment

    Represents a price adjustment on a FulfillmentOrderLineItem. Corresponds to an
      OrderItemAdjustmentLineSummary associated with the corresponding OrderItemSummary. This
    object is available in API version 48.0 and later.

This object is used for calculations and doesn’t have a default record page.

## Supported Calls

       <samp class="codeph nolang">create()</samp>,        <samp class="codeph nolang">delete()</samp>,          <samp class="codeph nolang">describeLayout()</samp>,          <samp class="codeph nolang">describeSObjects()</samp>,          <samp class="codeph nolang">getDeleted()</samp>,          <samp class="codeph nolang">getUpdated()</samp>,          <samp class="codeph nolang">query()</samp>,          <samp class="codeph nolang">retrieve()</samp>,          <samp class="codeph nolang">update()</samp>,          <samp class="codeph nolang">upsert()</samp>           

## Special Access Rules

This object is only available in Salesforce Order Management orgs.

## Fields

| Field | Details |
| --- | --- |
| Amount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Create, Filter, Sort<br>

                    - Description<br>

                        - Amount, not including tax, of the adjustment. |
| CampaignName | - Type<br>

                        - string<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort, Update<br>

                    - Description<br>

                        - Campaign associated with the adjustment. |
| CouponName | - Type<br>

                        - string<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort, Update<br>

                    - Description<br>

                        - Coupon associated with the adjustment. |
| CurrencyIsoCode | - Type<br>

                        - picklist<br>

                    - Properties<br>

                        - Defaulted on create, Filter, Group, Restricted picklist, Sort<br>

                    - Description<br>

                        - ISO code for the currency of the FulfillmentOrderLineItem to which the
                      adjustment applies. The default value is USD.<br>

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

                        - Text description of the adjustment. |
| FulfillmentOrderId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Create, Filter, Group, Sort<br>

                    - Description<br>

                        - ID of the FulfillmentOrder associated with the FulfillmentOrderLineItem to
                      which the adjustment applies. |
| FulfillmentOrderItem​AdjustmentNumber | - Type<br>

                        - string<br>

                    - Properties<br>

                        - Autonumber, Defaulted on create, Filter, idLookup, Sort<br>

                    - Description<br>

                        - ID of the FulfillmentOrderLineItemAdjustment. |
| FulfillmentOrder​LineItemId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Create, Filter, Group, Sort<br>

                    - Description<br>

                        - ID of the FulfillmentOrderLineItem to which this adjustment applies. |
| OrderItemAdjust​LineSummaryId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort<br>

                    - Description<br>

                        - ID of the OrderItemAdjustmentLineSummary associated with the
                      adjustment. |
| PromotionName | - Type<br>

                        - string<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort, Update<br>

                    - Description<br>

                        - Promotion associated with the adjustment. |
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

- [FulfillmentOrder](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_fulfillmentorder.htm "Represents a group of products and delivery charges on a single order that share the same fulfillment location, delivery method, and recipient. The FulfillmentOrderLineItems belonging to a FulfillmentOrder are associated with OrderItemSummary objects belonging to a single OrderSummary. This object is available in API version 48.0 and later.")
- [FulfillmentOrderItemTax](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_fulfillmentorderitemtax.htm "Represents the tax on a FulfillmentOrderLineItem or FulfillmentOrderItemAdjustment. Corresponds to an OrderItemTaxLineItemSummary. This object is available in API version 48.0 and later.")
- [FulfillmentOrderLineItem](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_fulfillmentorderlineitem.htm "Represents a product or delivery charge belonging to a FulfillmentOrder. Corresponds to an OrderItemSummary. This object is available in API version 48.0 and later.")
- [OrderItemAdjustmentLineSummary](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_orderitemadjustmentlinesummary.htm "Represents the current properties and state of price adjustments on an OrderItemSummary. Corresponds to one or more order item adjustment line item objects, consisting of an original object and any change objects applicable to it. This object is available in API version 48.0 and later.")