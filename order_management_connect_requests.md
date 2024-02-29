# Salesforce Order Management Requests

Salesforce Order Management includes these Chatter Connect API requests.

- **[Adjust Item Input](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_requests_adjust_item_input.htm)**

A price adjustment to an OrderItemSummary. It only supports       discounts, not increases.
- **[Adjust Order Item Summary Input](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_requests_adjust_order_item_summary_input.htm)**

A list of price adjustments to OrderItemSummaries that make up a       price adjustment to an order.
- **[Change Input](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_requests_change_input.htm)**

A list of changes to OrderItemSummaries that make up an order       change, such as a cancel or return.
- **[Change Item Input](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_requests_change_item_input.htm)**

Change to an OrderItemSummary, such as a return or cancel. You       specify whether to prorate the associated shipping charge based on the price change. The       OrderItemSummary can’t be a shipping charge.
- **[Create Credit Memo Input](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_requests_create_credit_memo_input.htm)**

A list of change orders used to create a credit     memo.
- **[Create Order Payment Summary Input](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_requests_create_order_payment_summary_input.htm)**

An OrderSummary for which to create an OrderPaymentSummary, with the       payment authorization or payments to include in it.
- **[Ensure Funds Async Input](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_requests_ensure_funds_async_input.htm)**

ID of an invoice to ensure funds for and apply them     to.
- **[Ensure Refunds Async Input](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_requests_ensure_refunds_async_input.htm)**

ID of a credit memo to ensure refunds for, an amount of excess funds       to refund, or both. At least one is required.
- **[Fulfillment Group Input](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_requests_fulfillment_group_input.htm)**

A list of OrderItemSummaries to be fulfilled together, and the       fulfillment location that will handle them. The fulfillment type is one of the values defined       for the Type field on the FulfillmentOrder object, such as “Warehouse” or “Retail Store.” The       specified type is assigned to the FulfillmentOrder for this fulfillment     group.
- **[Fulfillment Order Input](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_requests_fulfillment_order_input.htm)**

An OrderDeliveryGroupSummary that defines a delivery method and       recipient, and a list of fulfillment groups to assign to FulfillmentOrders. Each fulfillment       group is a set of OrderItemSummaries that match the OrderDeliveryGroupSummary and share the       same fulfillment location. The method creates a FulfillmentOrder for each fulfillment group       and a FulfillmentOrderLineItem for each OrderItemSummary.
- **[Fulfillment Order Invoice Input](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_requests_fulfillment_order_invoice_input.htm)**

Use an empty request body for this     input.
- **[Fulfillment Order Line Item Input](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_requests_fulfillment_order_line_item_input.htm)**

A FulfillmentOrderLineItem and quantity to cancel. You can cancel       less than the full quantity, in which case you reallocate the canceled quantity to a different       FulfillmentOrder.
- **[Fulfillment Order Line Items To Cancel Input](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_requests_fulfillment_order_line_items_to_cancel_input.htm)**

A list of FulfillmentOrderLineItems and quantities to     cancel.
- **[Order Item Summary Input](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_requests_order_item_summary_input.htm)**

An OrderItemSummary and quantity.
- **[Order Summary Input](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_requests_order_summary_input.htm)**

An order from which to create an OrderSummary, and whether it is       managed in Salesforce Order Management. Optionally, you can specify an OrderNumber or       Status.