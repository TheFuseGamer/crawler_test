# Salesforce Order Management Resources

Manage orders and the order fulfillment process. Available in Salesforce Order
      Management orgs.

Available resources are:

| Resource | Description |
| --- | --- |
| [<samp class="codeph nolang">/commerce/fulfillment/fulfillment-orders</samp>](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_fulfillment_orders.htm "Create one or more FulfillmentOrders and FulfillmentOrderLineItems for an OrderDeliveryGroupSummary, which defines a delivery method and recipient for an OrderSummary. You specify the OrderItemSummaries to allocate, which can be fulfilled from different locations. Specifying multiple fulfillment groups creates one FulfillmentOrder for each location. For each OrderItemSummary, a FulfillmentOrderLineItem is created and assigned to the corresponding FulfillmentOrder.") | Create one or more FulfillmentOrders and FulfillmentOrderLineItems
      for an OrderDeliveryGroupSummary, which defines a delivery method and recipient for an
      OrderSummary. You specify the OrderItemSummaries to allocate, which can be fulfilled from
      different locations. Specifying multiple fulfillment groups creates one FulfillmentOrder for
      each location. For each OrderItemSummary, a FulfillmentOrderLineItem is created and assigned
      to the corresponding FulfillmentOrder. |
| [<samp class="codeph nolang">/commerce/fulfillment/fulfillment-orders/​<var class="keyword varname">fulfillmentOrderId</var>/actions/cancel-item</samp>](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_fulfillment_orders_cancel_items.htm "Cancel FulfillmentOrderLineItems from a FulfillmentOrder. This action doesn’t cancel the associated OrderItemSummaries, so reallocate the canceled quantities to a new FulfillmentOrder.") | Cancel FulfillmentOrderLineItems from a FulfillmentOrder. This
      action doesn’t cancel the associated OrderItemSummaries, so reallocate the canceled quantities
      to a new FulfillmentOrder. |
| [<samp class="codeph nolang">/commerce/fulfillment/fulfillment-orders/​<var class="keyword varname">fulfillmentOrderId</var>/actions/create-invoice</samp>](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_fulfillment_orders_create_invoice.htm "Create an invoice for a FulfillmentOrder that doesn’t have one.") | Create an invoice for a FulfillmentOrder that doesn’t have
    one. |
| <samp class="codeph nolang">/commerce/fulfillment/actions/create-multiple</samp> | Create multiple FulfillmentOrders in a single
    request. |
| [<samp class="codeph nolang">/commerce/order-management/order-payment-summaries</samp>](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_order_payment_summaries.htm "Create an OrderPaymentSummary for an OrderSummary. Specify a payment authorization or payments that share the same payment method. In an org with the multicurrency feature enabled, the OrderPaymentSummary inherits the CurrencyIsoCode value from the OrderSummary.") | Create an OrderPaymentSummary for an OrderSummary. Specify a payment
      authorization or payments that share the same payment method. In an org with the multicurrency
      feature enabled, the OrderPaymentSummary inherits the CurrencyIsoCode value from the
      OrderSummary. |
| [<samp class="codeph nolang">/commerce/order-management/order-summaries</samp>](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_order_summaries.htm "Create an OrderSummary based on an order. That order is considered the original order for the OrderSummary. Subsequent change orders that apply to the OrderSummary are also represented as orders. You can specify whether the order is managed in Salesforce Order Management or by an external system. Most Salesforce Order Management APIs can run only on orders that it manages.") | Create an OrderSummary based on an order. That order is considered
      the original order for the OrderSummary. Subsequent change orders that apply to the
      OrderSummary are also represented as orders. You can specify whether the order is managed in
      Salesforce Order Management or by an external system. Most Salesforce Order Management APIs
      can run only on orders that it manages. |
| [<samp class="codeph nolang">/commerce/order-management/order-summaries/​<var class="keyword varname">orderSummaryId</var>/actions/create-credit-memo</samp>](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_order_summaries_create_credit_memo.htm "Create a credit memo to represent the refund for one or more change orders associated with an OrderSummary.") | Create a credit memo to represent the refund for one or more change
      orders associated with an OrderSummary. |
| [<samp class="codeph nolang">/commerce/order-management/order-summaries​<var class="keyword varname">orderSummaryId</var>/async-actions/​ensure-funds-async</samp>](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_order_summaries_ensure_funds_async.htm "Ensure funds for an invoice and apply them to it. If needed, capture authorized funds by sending a request to a payment provider. This method inserts a background operation into an asynchronous job queue and returns the ID of that operation so you can track its status. Payment gateway responses appear in the payment gateway log and do not affect the background operation status.") | Ensure funds for an invoice and apply them to it. If needed, capture
      authorized funds by sending a request to a payment provider. This method inserts a background
      operation into an asynchronous job queue and returns the ID of that operation so you can track
      its status. Payment gateway responses appear in the payment gateway log and do not affect the
      background operation status. |
| [<samp class="codeph nolang">/commerce/order-management/order-summaries/​<var class="keyword varname">orderSummaryId</var>/async-actions/​ensure-refunds-async</samp>](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_order_summaries_ensure_refunds_async.htm "Ensure refunds for a credit memo or excess funds by sending a request to a payment provider. This method inserts a background operation into an asynchronous job queue and returns the ID of that operation so you can track its status. Payment gateway responses appear in the payment gateway log and do not affect the background operation status.") | Ensure refunds for a credit memo or excess funds by sending a request to a payment
      provider. This method inserts a background operation into an asynchronous job queue and
      returns the ID of that operation so you can track its status. Payment gateway responses appear
      in the payment gateway log and do not affect the background operation status. |
| [<samp class="codeph nolang">/commerce/order-management/order-summaries/​<var class="keyword varname">orderSummaryId</var>/actions/preview-cancel</samp>](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_order_summaries_preview_cancel.htm "Retrieve the expected change order values for canceling one or more OrderItemSummaries from an OrderSummary, without actually executing the cancel.") | Retrieve the expected change order values for canceling one or more
      OrderItemSummaries from an OrderSummary, without actually executing the
    cancel. |
| [<samp class="codeph nolang">/commerce/order-management/order-summaries/​<var class="keyword varname">orderSummaryId</var>/actions/preview-return</samp>](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_order_summaries_preview_return.htm "Retrieve the expected change order values for returning one or more OrderItemSummaries from an OrderSummary, without actually executing the return.") | Retrieve the expected change order values for returning one or more
      OrderItemSummaries from an OrderSummary, without actually executing the
    return. |
| [<samp class="codeph nolang">/commerce/order-management/order-summaries/​<var class="keyword varname">orderSummaryId</var>/actions/submit-cancel</samp>](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_order_summaries_submit_cancel.htm "Cancel one or more OrderItemSummaries from an OrderSummary, and create a corresponding change order.") | Cancel one or more OrderItemSummaries from an OrderSummary, and
      create a corresponding change order. |
| [<samp class="codeph nolang">/commerce/order-management/order-summaries/​<var class="keyword varname">orderSummaryId</var>/actions/submit-return</samp>](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_order_summaries_submit_return.htm "Return one or more OrderItemSummaries from an OrderSummary, and create a corresponding change order.") | Return one or more OrderItemSummaries from an OrderSummary, and
      create a corresponding change order. |
| <samp class="codeph nolang">/commerce/order-management/routing/actions/find-routes-with-fewest-splits</samp> | Returns combinations of inventory locations that can fulfill an
      order within a specified limit of shipment splits. |
| <samp class="codeph nolang">/commerce/order-management/routing/actions/rank-byaverage-distance</samp> | Calculates the average distance from sets of inventory locations to
      an order recipient, and ranks them. Use this method to compare the average shipping distances
      for different sets of locations that can fulfill an order. |

- **[Fulfillment Orders](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_fulfillment_orders.htm)**

Create one or more FulfillmentOrders and FulfillmentOrderLineItems       for an OrderDeliveryGroupSummary, which defines a delivery method and recipient for an       OrderSummary. You specify the OrderItemSummaries to allocate, which can be fulfilled from       different locations. Specifying multiple fulfillment groups creates one FulfillmentOrder for       each location. For each OrderItemSummary, a FulfillmentOrderLineItem is created and assigned       to the corresponding FulfillmentOrder.
- **[Fulfillment Orders, Cancel Item](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_fulfillment_orders_cancel_items.htm)**

Cancel FulfillmentOrderLineItems from a FulfillmentOrder. This       action doesn’t cancel the associated OrderItemSummaries, so reallocate the canceled quantities       to a new FulfillmentOrder.
- **[Fulfillment Orders, Create Invoice](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_fulfillment_orders_create_invoice.htm)**

Create an invoice for a FulfillmentOrder that doesn’t have     one.
- **[Order Payment Summaries](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_order_payment_summaries.htm)**

Create an OrderPaymentSummary for an OrderSummary. Specify a payment       authorization or payments that share the same payment method. In an org with the multicurrency       feature enabled, the OrderPaymentSummary inherits the CurrencyIsoCode value from the       OrderSummary.
- **[Order Summaries](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_order_summaries.htm)**

Create an OrderSummary based on an order. That order is considered       the original order for the OrderSummary. Subsequent change orders that apply to the       OrderSummary are also represented as orders. You can specify whether the order is managed in       Salesforce Order Management or by an external system. Most Salesforce Order Management APIs       can run only on orders that it manages.
- **[Order Summaries, Create Credit Memo](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_order_summaries_create_credit_memo.htm)**

Create a credit memo to represent the refund for one or more change       orders associated with an OrderSummary.
- **[Order Summaries, Ensure Funds Async](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_order_summaries_ensure_funds_async.htm)**

Ensure funds for an invoice and apply them to it. If needed, capture       authorized funds by sending a request to a payment provider. This method inserts a background       operation into an asynchronous job queue and returns the ID of that operation so you can track       its status. Payment gateway responses appear in the payment gateway log and do not affect the       background operation status.
- **[Order Summaries, Ensure Refunds Async](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_order_summaries_ensure_refunds_async.htm)**

Ensure refunds for a credit memo or excess funds by sending a request to a payment       provider. This method inserts a background operation into an asynchronous job queue and       returns the ID of that operation so you can track its status. Payment gateway responses appear       in the payment gateway log and do not affect the background operation status.
- **[Order Summaries, Preview Adjust](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_order_summaries_preview_adjust.htm)**

Retrieve the expected results of adjusting the price of one or more       OrderItemSummaries from an OrderSummary, without actually executing the adjustment. The       response data contains the financial changes that would result from submitting the proposed       adjustment.
- **[Order Summaries, Preview Cancel](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_order_summaries_preview_cancel.htm)**

Retrieve the expected change order values for canceling one or more       OrderItemSummaries from an OrderSummary, without actually executing the     cancel.
- **[Order Summaries, Preview Return](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_order_summaries_preview_return.htm)**

Retrieve the expected change order values for returning one or more       OrderItemSummaries from an OrderSummary, without actually executing the     return.
- **[Order Summaries, Submit Adjust](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_order_summaries_submit_adjust.htm)**

Adjust the price of one or more OrderItemSummaries from an       OrderSummary, and create one or two corresponding change orders.
- **[Order Summaries, Submit Cancel](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_order_summaries_submit_cancel.htm)**

Cancel one or more OrderItemSummaries from an OrderSummary, and       create a corresponding change order.
- **[Order Summaries, Submit Return](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_order_summaries_submit_return.htm)**

Return one or more OrderItemSummaries from an OrderSummary, and       create a corresponding change order.