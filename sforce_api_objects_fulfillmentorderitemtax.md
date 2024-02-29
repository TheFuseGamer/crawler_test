# FulfillmentOrderItemTax

    Represents the tax on a FulfillmentOrderLineItem or
      FulfillmentOrderItemAdjustment. Corresponds to an OrderItemTaxLineItemSummary. This
    object is available in API version 48.0 and later.

This object is used for calculations and doesn’t have a default record page.

## Supported Calls

       <samp class="codeph nolang">create()</samp>,          <samp class="codeph nolang">delete()</samp>,          <samp class="codeph nolang">describeLayout()</samp>,          <samp class="codeph nolang">describeSObjects()</samp>,          <samp class="codeph nolang">getDeleted()</samp>,          <samp class="codeph nolang">getUpdated()</samp>,          <samp class="codeph nolang">query()</samp>,          <samp class="codeph nolang">retrieve()</samp>,          <samp class="codeph nolang">update()</samp>,          <samp class="codeph nolang">upsert()</samp>           

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

                        - Amount of tax represented by the FulfillmentOrderItemTax. |
| CurrencyIsoCode | - Type<br>

                        - picklist<br>

                    - Properties<br>

                        - Defaulted on create, Filter, Group, Restricted picklist, Sort<br>

                    - Description<br>

                        - ISO code for the currency of the FulfillmentOrderLineItem to which the tax
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

                        - Description of the FulfillmentOrderItemTax. |
| FulfillmentOrderId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Create, Filter, Group, Sort<br>

                    - Description<br>

                        - ID of the associated FulfillmentOrder. |
| FulfillmentOrder​ItemAdjustId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort<br>

                    - Description<br>

                        - If this object represents tax on an adjustment, this value is the ID of the
                      FulfillmentOrderItemAdjustment to which the tax applies. If this value is
                      null, the adjustment applies to a FulfillmentOrderLineItem. |
| FulfillmentOrderItem​TaxNumber | - Type<br>

                        - string<br>

                    - Properties<br>

                        - Autonumber, Defaulted on create, Filter, idLookup, Sort<br>

                    - Description<br>

                        - ID of the FulfillmentOrderItemTax. |
| FulfillmentOrder​LineItemId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Create, Filter, Group, Sort<br>

                    - Description<br>

                        - If this object represents tax on a FulfillmentOrderLineItem, this value is
                      the ID of that FulfillmentOrderLineItem. If this object represents tax on an
                      adjustment, this value is the ID of the FulfillmentOrderLineItem to which the
                      adjustment applies. |
| OrderItemTaxLineItem​SummaryId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort<br>

                    - Description<br>

                        - ID of the OrderItemTaxLineItemSummary associated with the OrderItemSummary
                      that corresponds to the FulfillmentOrderLineItem to which the tax
                      applies. |
| Rate | - Type<br>

                        - percent<br>

                    - Properties<br>

                        - Create, Filter, Nillable, Sort, Update<br>

                    - Description<br>

                        - Tax rate used to calculate the Amount. |
| TaxEffectiveDate | - Type<br>

                        - date<br>

                    - Properties<br>

                        - Create, Filter, Group, Sort, Update<br>

                    - Description<br>

                        - Date on which the Amount was calculated. Important due to tax rate changes
                      over time. |
| Type | - Type<br>

                        - picklist<br>

                    - Properties<br>

                        - Create, Filter, Group, Restricted picklist, Sort, Update<br>

                    - Description<br>

                        - Indicates whether the Amount is actual or estimated.<br>

                        - Possible values are: <ul class="ul bulletList">
                        <li class="li"><samp class="codeph nolang">Actual</samp></li>

                        <li class="li"><samp class="codeph nolang">Estimated</samp></li>

                      </ul> |

#### See Also

- [FulfillmentOrder](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_fulfillmentorder.htm "Represents a group of products and delivery charges on a single order that share the same fulfillment location, delivery method, and recipient. The FulfillmentOrderLineItems belonging to a FulfillmentOrder are associated with OrderItemSummary objects belonging to a single OrderSummary. This object is available in API version 48.0 and later.")
- [FulfillmentOrderItemAdjustment](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_fulfillmentorderitemadjustment.htm "Represents a price adjustment on a FulfillmentOrderLineItem. Corresponds to an OrderItemAdjustmentLineSummary associated with the corresponding OrderItemSummary. This object is available in API version 48.0 and later.")
- [FulfillmentOrderLineItem](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_fulfillmentorderlineitem.htm "Represents a product or delivery charge belonging to a FulfillmentOrder. Corresponds to an OrderItemSummary. This object is available in API version 48.0 and later.")
- [OrderItemTaxLineItemSummary](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_orderitemtaxlineitemsummary.htm "Represents the current tax on an OrderItemSummary or OrderItemAdjustmentLineSummary. Corresponds to one or more order item tax line items, consisting of an original object and any change objects applicable to it. This object is available in API version 48.0 and later.")