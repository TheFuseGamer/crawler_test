# OrderItemSummary

    Represents the current properties and state of a product or charge on an
      OrderSummary. Corresponds to one or more order item objects, consisting of an original object
      and any change objects applicable to it. This object is available in API version 48.0 and
    later.

## Supported Calls

<samp class="codeph nolang">create()</samp>,           <samp class="codeph nolang">delete()</samp>,           <samp class="codeph nolang">describeLayout()</samp>, <samp class="codeph nolang">describeSObjects()</samp>, <samp class="codeph nolang">getDeleted()</samp>, <samp class="codeph nolang">getUpdated()</samp>, <samp class="codeph nolang">query()</samp>,           <samp class="codeph nolang">retrieve()</samp>, <samp class="codeph nolang">undelete()</samp>,           <samp class="codeph nolang">update()</samp>,           <samp class="codeph nolang">upsert()</samp>       

## Special Access Rules

This object is only available in Salesforce Order Management orgs or if the B2B Commerce on         Lightning Experience license is enabled.

## Fields

| Field | Details |
| --- | --- |
| AdjustedLineAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total, including adjustments but not tax, of the OrderItemSummary. |
| AdjustedLineAmt​WithTax | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total price of the OrderItemSummary, inclusive of adjustments and tax. This
                      amount is equal to AdjustedLineAmount + TotalAdjustedLineTaxAmount.<br>

                        - This field is available in API version 49.0 and later. |
| CurrencyIsoCode | - Type<br>

                        - picklist<br>

                    - Properties<br>

                        - Defaulted on create, Filter, Group, Restricted picklist, Sort<br>

                    - Description<br>

                        - ISO code for the currency of the OrderSummary associated with the
                      OrderItemSummary. The default value is USD.<br>

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

                        - Description of the OrderItemSummary.<br>

                        - This field can be edited. |
| EndDate | - Type<br>

                        - date<br>

                    - Properties<br>

                        - Filter, Group, Nillable, Sort<br>

                    - Description<br>

                        - End date of the OrderItemSummary.<br>

                        - If the OrderLifeCycleType field on the associated
                      OrderSummary is set to UNMANAGED, then users with the Edit Unmanaged Order
                      Summaries or B2B Commerce Integrator user permission can modify this
                      field. |
| GrossUnitPrice | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Unit price, including tax, of the OrderItemSummary. This value is equal to
                      UnitPrice + the amount of tax on the UnitPrice.<br>

                        - If the OrderLifeCycleType field on the associated
                      OrderSummary is set to UNMANAGED, then users with the Edit Unmanaged Order
                      Summaries or B2B Commerce Integrator user permission can modify this
                      field.<br>

                        - This field is available in API version 49.0 and later. |
| LineNumber | - Type<br>

                        - int<br>

                    - Properties<br>

                        - Filter, Group, Nillable, Sort<br>

                    - Description<br>

                        - The order line number assigned to this OrderItemSummary. For example, if
                      this object is the third in the displayed list of OrderItemSummaries belonging
                      to the OrderSummary, this value is 3.<br>

                        - If the OrderLifeCycleType field on the associated
                      OrderSummary is set to UNMANAGED, then users with the Edit Unmanaged Order
                      Summaries or B2B Commerce Integrator user permission can modify this
                      field. |
| ListPrice | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - List price of the product represented by this OrderItemSummary.<br>

                        - If the OrderLifeCycleType field on the associated
                      OrderSummary is set to UNMANAGED, then users with the Edit Unmanaged Order
                      Summaries or B2B Commerce Integrator user permission can modify this
                      field. |
| Name | - Type<br>

                        - string<br>

                    - Properties<br>

                        - Create, Filter, Group, idLookup, Sort, Update<br>

                    - Description<br>

                        - Name of the OrderItemSummary. |
| OrderDeliveryGroup​SummaryId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Filter, Group, Sort<br>

                    - Description<br>

                        - ID of the OrderDeliveryGroupSummary to which this object belongs. |
| OrderSummaryId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Filter, Group, Sort<br>

                    - Description<br>

                        - ID of the OrderSummary to which this object belongs. |
| OriginalOrderItemId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Filter, Group, Nillable, Sort<br>

                    - Description<br>

                        - ID of the original order item associated with this summary object.
                      Nillable=true only if the associated order summary is unmanaged. For managed
                      order summaries, nillable=false. |
| Product2Id | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Filter, Group, Sort<br>

                    - Description<br>

                        - ID of the product represented by this OrderItemSummary. |
| ProductCode | - Type<br>

                        - string<br>

                    - Properties<br>

                        - Filter, Group, Nillable, Sort<br>

                    - Description<br>

                        - Product code of the product represented by this OrderItemSummary. |
| Quantity | - Type<br>

                        - double<br>

                    - Properties<br>

                        - Filter, Sort<br>

                    - Description<br>

                        - Current total quantity of products represented by this order item summary.
                      Equal to QuantityOrdered minus (QuantityCanceled and QuantityReturned).<br>

                        - If the OrderLifeCycleType field on the associated
                      OrderSummary is set to UNMANAGED, then users with the Edit Unmanaged Order
                      Summaries or B2B Commerce Integrator user permission can modify this
                      field. |
| QuantityAllocated | - Type<br>

                        - double<br>

                    - Properties<br>

                        - Filter, Sort<br>

                    - Description<br>

                        - Allocated quantity on this order item summary. This quantity is associated
                      with one or more FulfillmentOrderLineItems.<br>

                        - If the OrderLifeCycleType field on the associated
                      OrderSummary is set to UNMANAGED, then users with the Edit Unmanaged Order
                      Summaries or B2B Commerce Integrator user permission can modify this
                      field. |
| QuantityAvailable​ToCancel | - Type<br>

                        - double<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Quantity that can still be canceled on this OrderItemSummary. Equal to
                      QuantityOrdered minus (QuantityCanceled and QuantityAllocated). This value
                      duplicates QuantityAvailableToFulfill. |
| QuantityAvailable​ToFulfill | - Type<br>

                        - double<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Quantity available to be fulfilled on this OrderItemSummary. Equal to
                      QuantityOrdered minus (QuantityCanceled and QuantityAllocated). This value
                      duplicates QuantityAvailableToCancel. |
| QuantityAvailable​ToReturn | - Type<br>

                        - double<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Quantity available to be returned on this OrderItemSummary. Equal to
                      QuantityFulfilled minus QuantityReturnInitiated. |
| QuantityCanceled | - Type<br>

                        - double<br>

                    - Properties<br>

                        - Filter, Sort<br>

                    - Description<br>

                        - Canceled quantity on this OrderItemSummary.<br>

                        - If the OrderLifeCycleType field on the associated
                      OrderSummary is set to UNMANAGED, then users with the Edit Unmanaged Order
                      Summaries or B2B Commerce Integrator user permission can modify this
                      field. |
| QuantityFulfilled | - Type<br>

                        - double<br>

                    - Properties<br>

                        - Filter, Sort<br>

                    - Description<br>

                        - Fulfilled quantity on this OrderItemSummary. This quantity can no longer be
                      canceled.<br>

                        - If the OrderLifeCycleType field on the associated
                      OrderSummary is set to UNMANAGED, then users with the Edit Unmanaged Order
                      Summaries or B2B Commerce Integrator user permission can modify this
                      field. |
| QuantityNetOrdered | - Type<br>

                        - double<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Quantity available to be allocated on this OrderItemSummary. Equal to
                      QuantityOrdered minus QuantityCanceled. |
| QuantityOrdered | - Type<br>

                        - double<br>

                    - Properties<br>

                        - Filter, Sort<br>

                    - Description<br>

                        - Ordered quantity on this OrderItemSummary. It includes the originally
                      ordered quantity plus any quantity added to the order later.<br>

                        - If the OrderLifeCycleType field on the associated
                      OrderSummary is set to UNMANAGED, then users with the Edit Unmanaged Order
                      Summaries or B2B Commerce Integrator user permission can modify this
                      field. |
| QuantityReturned | - Type<br>

                        - double<br>

                    - Properties<br>

                        - Filter, Sort<br>

                    - Description<br>

                        - Returned quantity on this OrderItemSummary.<br>

                        - If the OrderLifeCycleType field on the associated
                      OrderSummary is set to UNMANAGED, then users with the Edit Unmanaged Order
                      Summaries or B2B Commerce Integrator user permission can modify this
                      field. |
| QuantityReturnInitiated | - Type<br>

                        - double<br>

                    - Properties<br>

                        - Filter, Sort<br>

                    - Description<br>

                        - Quantity returned or pending return on this OrderItemSummary.<br>

                        - If the OrderLifeCycleType field on the associated
                      OrderSummary is set to UNMANAGED, then users with the Edit Unmanaged Order
                      Summaries or B2B Commerce Integrator user permission can modify this
                      field. |
| ReservedAtLocationId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort, Update<br>

                    - Description<br>

                        - Reserved for future use. |
| ServiceDate | - Type<br>

                        - date<br>

                    - Properties<br>

                        - Filter, Group, Nillable, Sort<br>

                    - Description<br>

                        - Service or start date of the OrderItemSummary.<br>

                        - If the OrderLifeCycleType field on the associated
                      OrderSummary is set to UNMANAGED, then users with the Edit Unmanaged Order
                      Summaries or B2B Commerce Integrator user permission can modify this
                      field. |
| Status | - Type<br>

                        - picklist<br>

                    - Properties<br>

                        - Defaulted on create, Filter, Group, Restricted picklist, Sort<br>

                    - Description<br>

                        - Status of the OrderItemSummary. The default value is ORDERED.<br>

                        - Possible values are: <ul class="ul bulletList">
                        <li class="li">
<samp class="codeph nolang">ALLOCATED</samp>—Allocated</li>

                        <li class="li">
<samp class="codeph nolang">CANCELED</samp>—Canceled</li>

                        <li class="li">
<samp class="codeph nolang">FULFILLED</samp>—Fulfilled</li>

                        <li class="li">
<samp class="codeph nolang">ORDERED</samp>—Ordered</li>

                        <li class="li">
<samp class="codeph nolang">PAID</samp>—Paid</li>

                        <li class="li">
<samp class="codeph nolang">PARTIALLYALLOCATED</samp>—Partially
                          Allocated</li>

                        <li class="li">
<samp class="codeph nolang">PARTIALLYFULFILLED</samp>—Partially
                          Fulfilled</li>

                        <li class="li">
<samp class="codeph nolang">RESHIPPED</samp>—Reshipped</li>

                        <li class="li">
<samp class="codeph nolang">RETURNED</samp>—Returned</li>

                      </ul> |
| StockKeepingUnit | - Type<br>

                        - string<br>

                    - Properties<br>

                        - Filter, Group, Nillable, Sort<br>

                    - Description<br>

                        - The stock keeping unit (SKU) of the Product2 associated with the
                      OrderItemSummary..<br>

                        - This field is available in API version 49.0 and later. |
| TotalAdjusted​LineTaxAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Tax on the AdjustedLineAmount. |
| TotalAdjustmentAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total of all price adjustments applied to this OrderItemSummary. |
| TotalAdjustment​AmtWithTax | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total amount of all price adjustments applied to this OrderItemSummary,
                      inclusive of tax. This amount is equal to TotalAdjustmentAmount +
                      TotalAdjustmentTaxAmount.<br>

                        - This field is available in API version 49.0 and later. |
| TotalAdjustmentDistAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total of all order-level price adjustments applied to this OrderItemSummary.
                      This value includes OrderItemAdjustmentLineSummaries that belong to
                      OrderAdjustmentGroupSummaries of type Header. |
| TotalAdjustmentDist​AmtWithTax | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total amount of the order-level price adjustments applied to this
                      OrderItemSummary, inclusive of tax. This amount is equal to
                      TotalAdjustmentDistAmount + TotalAdjustmentDistTaxAmount.<br>

                        - This field is available in API version 49.0 and later. |
| TotalAdjustmentDist​TaxAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Tax on the TotalAdjustmentDistAmount. |
| TotalAdjustmentTaxAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Tax on the TotalAdjustmentAmount. |
| TotalAmtWithTax | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total price of the OrderItemSummary, inclusive of tax. This amount is equal
                      to TotalPrice + TotalTaxAmount.<br>

                        - This field is available in API version 49.0 and later. |
| TotalLineAdjustmentAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total of all non-order-level price adjustments applied to this
                      OrderItemSummary. This value includes OrderItemAdjustmentLineSummaries that
                      don’t belong to an OrderAdjustmentGroupSummary, or that belong to an
                      OrderAdjustmentGroupSummary of type SplitLine. |
| TotalLineAdjustment​AmtWithTax | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total of all non-order-level price adjustments applied to this
                      OrderItemSummary, inclusive of tax. This amount is equal to
                      TotalLineAdjustmentAmount + TotalLineAdjustmentTaxAmount.<br>

                        - This field is available in API version 49.0 and later. |
| TotalLineAdjustment​TaxAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Tax on the TotalLineAdjustmentAmount. |
| TotalLineAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total, not including adjustments or tax, of the OrderItemSummary.<br>

                        - If the OrderLifeCycleType field on the associated
                      OrderSummary is set to UNMANAGED, then users with the Edit Unmanaged Order
                      Summaries or B2B Commerce Integrator user permission can modify this
                      field. |
| TotalLineAmount​WithTax | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total unadjusted amount of the OrderItemSummary, inclusive of tax. This
                      amount is equal to TotalLineAmount + TotalLineTaxAmount.<br>

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

                        - Total, including adjustments but not tax, of the OrderItemSummary. |
| TotalTaxAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Tax on the TotalPrice. |
| Type | - Type<br>

                        - picklist<br>

                    - Properties<br>

                        - Filter, Group, Nillable, Restricted picklist, Sort<br>

                    - Description<br>

                        - Type of the OrderItemSummary. Delivery Charge indicates that the
                      OrderItemSummary represents a delivery charge. Order Product indicates that it
                      represents any other type of product, service, or charge. Each type
                      corresponds to one type code, shown here in parentheses.<br>

                        - Possible values are: <ul class="ul bulletList">
                        <li class="li"><samp class="codeph nolang">Delivery Charge (Charge)</samp></li>

                        <li class="li"><samp class="codeph nolang">Order Product (Product)</samp></li>

                      </ul><br>

                        - If the OrderLifeCycleType field on the associated
                      OrderSummary is set to UNMANAGED, then users with the Edit Unmanaged Order
                      Summaries or B2B Commerce Integrator user permission can modify this
                      field. |
| TypeCode | - Type<br>

                        - picklist<br>

                    - Properties<br>

                        - Filter, Group, Nillable, Restricted picklist, Sort<br>

                    - Description<br>

                        - Type code of the OrderItemSummary. Charge indicates that the
                      OrderItemSummary represents a delivery charge. Product indicates that it
                      represents any other type of product, service, or charge.<br>

                        - Possible values are: <ul class="ul bulletList">
                        <li class="li"><samp class="codeph nolang">Charge</samp></li>

                        <li class="li"><samp class="codeph nolang">Product</samp></li>

                      </ul><br>

                        - If the OrderLifeCycleType field on the associated
                      OrderSummary is set to UNMANAGED, then users with the Edit Unmanaged Order
                      Summaries or B2B Commerce Integrator user permission can modify this
                      field. |
| UnitPrice | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Unit price of the product represented by the OrderItemSummary.<br>

                        - If the OrderLifeCycleType field on the associated
                      OrderSummary is set to UNMANAGED, then users with the Edit Unmanaged Order
                      Summaries or B2B Commerce Integrator user permission can modify this
                      field. |

#### See Also

- [FulfillmentOrderLineItem](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_fulfillmentorderlineitem.htm "Represents a product or delivery charge belonging to a FulfillmentOrder. Corresponds to an OrderItemSummary. This object is available in API version 48.0 and later.")
- [OrderItemAdjustmentLineSummary](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_orderitemadjustmentlinesummary.htm "Represents the current properties and state of price adjustments on an OrderItemSummary. Corresponds to one or more order item adjustment line item objects, consisting of an original object and any change objects applicable to it. This object is available in API version 48.0 and later.")
- [OrderItemTaxLineItemSummary](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_orderitemtaxlineitemsummary.htm "Represents the current tax on an OrderItemSummary or OrderItemAdjustmentLineSummary. Corresponds to one or more order item tax line items, consisting of an original object and any change objects applicable to it. This object is available in API version 48.0 and later.")
- [OrderSummary](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_ordersummary.htm "Represents the current properties and state of an order. Corresponds to one or more order objects, consisting of an original object and any change objects applicable to it. This object is available in API version 48.0 and later.")