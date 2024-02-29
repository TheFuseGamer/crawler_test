# Fulfillment Order Line Item Input

A FulfillmentOrderLineItem and quantity to cancel. You can cancel
      less than the full quantity, in which case you reallocate the canceled quantity to a different
      FulfillmentOrder.

          - Root XML tag

              - <samp class="codeph nolang">&lt;fulfillmentOrderLineItem&gt;</samp>

          - JSON example

              - ```
{   
  "fulfillmentOrderLineItemId" : "0a4xx00000000W0001",
  "quantity":1
}
```

          - Properties

              - | Name | Type | Description | Required or Optional | Available Version |
| --- | --- | --- | --- | --- |
| <samp class="codeph nolang">fulfillmentOrder​LineItemId</samp> | String | ID of the
                FulfillmentOrderLineItem. | Required | 48.0 |
| <samp class="codeph nolang">quantity</samp> | Double | Quantity to cancel. | Required | 48.0 |

#### See Also

- [Fulfillment Orders, Cancel Item](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_fulfillment_orders_cancel_items.htm "Cancel FulfillmentOrderLineItems from a FulfillmentOrder. This action doesn’t cancel the associated OrderItemSummaries, so reallocate the canceled quantities to a new FulfillmentOrder.")
- [Fulfillment Order Line Items To Cancel Input](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_requests_fulfillment_order_line_items_to_cancel_input.htm "A list of FulfillmentOrderLineItems and quantities to cancel.")