# Salesforce Order Management Apex Inputs

Salesforce Order Management includes these Apex input classes.

- **[ConnectApi.AdjustItemInputRepresentation](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_connectapi_input_adjust_item.htm)**

A price adjustment to an OrderItemSummary. It only supports       discounts, not increases.
- **[ConnectApi.AdjustOrderItemSummaryInputRepresentation](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_connectapi_input_adjust_order_item_summary.htm)**

A list of price adjustments to OrderItemSummaries that make up a       price adjustment to an order.
- **[ConnectApi.ChangeInputRepresentation](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_connectapi_input_change.htm)**

A list of changes to OrderItemSummaries that make up an order       change, such as a cancel or return.
- **[ConnectApi.ChangeItemInputRepresentation](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_connectapi_input_change_item.htm)**

Change to an OrderItemSummary, such as a return or cancel. You       specify whether to prorate the associated shipping charge based on the price change. The       OrderItemSummary can’t be a shipping charge.
- **[ConnectApi.CreateCreditMemoInputRepresentation](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_connectapi_input_create_credit_memo.htm)**

A list of change orders used to create a credit     memo.
- **[ConnectApi.CreateOrderPaymentSummaryInputRepresentation](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_connectapi_input_create_order_payment_summary.htm)**

An OrderSummary for which to create an OrderPaymentSummary, with the       payment authorization or payments to include in it.
- **[ConnectApi.EnsureFundsAsyncInputRepresentation](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_connectapi_input_ensure_funds_async.htm)**

ID of an invoice to ensure funds for and apply them     to.
- **[ConnectApi.EnsureRefundsAsyncInputRepresentation](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_connectapi_input_ensure_refunds_async.htm)**

ID of a credit memo to ensure refunds for, an amount of excess funds       to refund, or both. At least one is required.
- **[ConnectApi.FulfillmentGroupInputRepresentation](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_connectapi_input_fulfillment_group.htm)**

A list of OrderItemSummaries to be fulfilled together, and the       fulfillment location that will handle them. The fulfillment type is one of the values defined       for the Type field on the FulfillmentOrder object, such as “Warehouse” or “Retail Store.” The       specified type is assigned to the FulfillmentOrder for this fulfillment     group.
- **[ConnectApi.FulfillmentOrderInputRepresentation](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_connectapi_input_fulfillment_order.htm)**

An OrderDeliveryGroupSummary that defines a delivery method and       recipient, and a list of fulfillment groups to assign to FulfillmentOrders. Each fulfillment       group is a set of OrderItemSummaries that match the OrderDeliveryGroupSummary and share the       same fulfillment location. The method creates a FulfillmentOrder for each fulfillment group       and a FulfillmentOrderLineItem for each OrderItemSummary.
- **[ConnectApi.FulfillmentOrderInvoiceInputRepresentation](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_connectapi_input_fulfillment_order_invoice.htm)**

Instantiate and include this object with no properties when creating       an invoice.
- **[ConnectApi.FulfillmentOrderLineItemInputRepresentation](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_connectapi_input_fulfillment_order_line_item.htm)**

A FulfillmentOrderLineItem and quantity to cancel. You can cancel       less than the full quantity, in which case you reallocate the canceled quantity to a different       FulfillmentOrder.
- **[ConnectApi.FulfillmentOrderLineItemsToCancelInputRepresentation](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_connectapi_input_fulfillment_order_line_items_to_cancel.htm)**

A list of FulfillmentOrderLineItems and quantities to     cancel.
- **[ConnectApi.OrderItemSummaryInputRepresentation](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_connectapi_input_order_item_summary.htm)**

An OrderItemSummary and quantity.
- **[ConnectApi.OrderSummaryInputRepresentation](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_connectapi_input_order_summary.htm)**

An order from which to create an OrderSummary, and whether it is       managed in Salesforce Order Management. Optionally, you can specify an OrderNumber or       Status.