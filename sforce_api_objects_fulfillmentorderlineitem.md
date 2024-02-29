# FulfillmentOrderLineItem

    Represents a product or delivery charge belonging to a FulfillmentOrder.
      Corresponds to an OrderItemSummary. This object is available in API version 48.0 and
    later.

## Supported Calls

       <samp class="codeph nolang">create()</samp>,          <samp class="codeph nolang">delete()</samp>,          <samp class="codeph nolang">describeLayout()</samp>,          <samp class="codeph nolang">describeSObjects()</samp>,          <samp class="codeph nolang">getDeleted()</samp>,          <samp class="codeph nolang">getUpdated()</samp>,          <samp class="codeph nolang">query()</samp>,          <samp class="codeph nolang">retrieve()</samp>,          <samp class="codeph nolang">update()</samp>,          <samp class="codeph nolang">upsert()</samp>           

## Special Access Rules

This object is only available in Salesforce Order Management orgs.

## Fields

| Field | Details |
| --- | --- |
| CurrencyIsoCode | - Type<br>

                        - picklist<br>

                    - Properties<br>

                        - Defaulted on create, Filter, Group, Restricted picklist, Sort<br>

                    - Description<br>

                        - ISO code for the currency of the FulfillmentOrder associated with the
                      FulfillmentOrderLineItem. The default value is USD.<br>

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

                        - string<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort, Update<br>

                    - Description<br>

                        - Description of the FulfillmentOrderLineItem. |
| EndDate | - Type<br>

                        - dateTime<br>

                    - Properties<br>

                        - Create, Filter, Nillable, Sort<br>

                    - Description<br>

                        - End date of the FulfillmentOrderLineItem. |
| FulfillmentOrderId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Create, Filter, Group, Sort<br>

                    - Description<br>

                        - ID of the FulfillmentOrder associated with the
                      FulfillmentOrderLineItem. |
| FulfillmentOrder​LineItemNumber | - Type<br>

                        - string<br>

                    - Properties<br>

                        - Autonumber, Defaulted on create, Filter, idLookup, Sort<br>

                    - Description<br>

                        - ID of the FulfillmentOrderLineItem. |
| GrossUnitPrice | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Create, Filter, Nillable, Sort<br>

                    - Description<br>

                        - Unit price, including tax, of the FulfillmentOrderLineItem. This value is
                      equal to TotalPrice + TotalTaxAmount.<br>

                        - This field is available in API version 49.0 and later. |
| OrderItemId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort<br>

                    - Description<br>

                        - ID of the original OrderItem for the OrderItemSummary associated with the
                      FulfillmentOrderLineItem. |
| OrderItemSummaryId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort<br>

                    - Description<br>

                        - ID of the OrderItemSummary associated with the
                      FulfillmentOrderLineItem. |
| OriginalQuantity | - Type<br>

                        - double<br>

                    - Properties<br>

                        - Create, Filter, Sort<br>

                    - Description<br>

                        - Original quantity of the FulfillmentOrderLineItem. |
| Product2Id | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort<br>

                    - Description<br>

                        - ID of the product represented by the FulfillmentOrderLineItem. |
| Quantity | - Type<br>

                        - double<br>

                    - Properties<br>

                        - Create, Filter, Sort, Update<br>

                    - Description<br>

                        - Current quantity of the FulfillmentOrderLineItem. Equal to the original
                      quantity minus any canceled quantity. |
| QuantityUnitOfMeasure | - Type<br>

                        - string<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort<br>

                    - Description<br>

                        - Unit of measure of the quantity, for example: unit, gallon, ton, or
                      case. |
| ServiceDate | - Type<br>

                        - dateTime<br>

                    - Properties<br>

                        - Create, Filter, Nillable, Sort<br>

                    - Description<br>

                        - Service or start date of the FulfillmentOrderLineItem. |
| TotalAdjustmentAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total of any price adjustments applied to the FulfillmentOrderLineItem. |
| TotalAdjustment​AmountWithTax | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total amount of the price adjustments applied to the
                      FulfillmentOrderLineItem, inclusive of tax. This amount is equal to
                      TotalAdjustmentAmount + TotalAdjustmentTaxAmount.<br>

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

                        - Total, including adjustments and tax, of the FulfillmentOrderLineItem. |
| TotalLineAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Create, Defaulted on create, Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total, not including adjustments or tax, of the
                      FulfillmentOrderLineItem. |
| TotalLineAmount​WithTax | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total price of the FulfillmentOrderLineItem, inclusive of tax. This amount
                      is equal to TotalLineAmount + TotalLineTaxAmount.<br>

                        - This field is available in API version 49.0 and later. |
| TotalLineTaxAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Tax on the TotalLineAmount. |
| TotalPrice | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total, including adjustments but not tax, of the FulfillmentOrderLineItem.
                      Equal to UnitPrice times Quantity. |
| TotalTaxAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Tax on the TotalPrice. |
| Type | - Type<br>

                        - picklist<br>

                    - Properties<br>

                        - Create, Filter, Group, Restricted picklist, Sort<br>

                    - Description<br>

                        - Type of the FulfillmentOrderLineItem. Matches the type of the associated
                      OrderItemSummary. Delivery Charge indicates that the FulfillmentOrderLineItem
                      represents a delivery charge. Order Product indicates that it represents any
                      other type of product, service, or charge. Each type corresponds to one type
                      code, shown here in parentheses.<br>

                        - Possible values are: <ul class="ul bulletList">
                        <li class="li"><samp class="codeph nolang">Delivery Charge</samp></li>

                        <li class="li"><samp class="codeph nolang">Order Product</samp></li>

                      </ul> |
| TypeCode | - Type<br>

                        - picklist<br>

                    - Properties<br>

                        - Create, Filter, Group, Restricted picklist, Sort<br>

                    - Description<br>

                        - Type code of the FulfillmentOrderLineItem. Matches the type code of the
                      associated OrderItemSummary. Processing depends on this value. Charge
                      indicates that the FulfillmentOrderLineItem represents a delivery charge.
                      Product indicates that it represents any other type of product, service, or
                      charge. Each type category corresponds to one or more types.<br>

                        - Possible values are: <ul class="ul bulletList">
                        <li class="li"><samp class="codeph nolang">Charge</samp></li>

                        <li class="li"><samp class="codeph nolang">Product</samp></li>

                      </ul> |
| UnitPrice | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Create, Defaulted on create, Filter, Nillable, Sort<br>

                    - Description<br>

                        - Unit price of the FulfillmentOrderLineItem. |

#### See Also

- [FulfillmentOrder](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_fulfillmentorder.htm "Represents a group of products and delivery charges on a single order that share the same fulfillment location, delivery method, and recipient. The FulfillmentOrderLineItems belonging to a FulfillmentOrder are associated with OrderItemSummary objects belonging to a single OrderSummary. This object is available in API version 48.0 and later.")
- [FulfillmentOrderItemAdjustment](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_fulfillmentorderitemadjustment.htm "Represents a price adjustment on a FulfillmentOrderLineItem. Corresponds to an OrderItemAdjustmentLineSummary associated with the corresponding OrderItemSummary. This object is available in API version 48.0 and later.")
- [FulfillmentOrderItemTax](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_fulfillmentorderitemtax.htm "Represents the tax on a FulfillmentOrderLineItem or FulfillmentOrderItemAdjustment. Corresponds to an OrderItemTaxLineItemSummary. This object is available in API version 48.0 and later.")
- [OrderItemSummary](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_orderitemsummary.htm "Represents the current properties and state of a product or charge on an OrderSummary. Corresponds to one or more order item objects, consisting of an original object and any change objects applicable to it. This object is available in API version 48.0 and later.")