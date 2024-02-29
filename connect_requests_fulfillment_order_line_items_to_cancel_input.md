# Fulfillment Order Line Items To Cancel Input

A list of FulfillmentOrderLineItems and quantities to
    cancel.

          - Root XML tag

              - <samp class="codeph nolang">&lt;fulfillmentOrderLineItemsToCancelInput&gt;</samp>

          - JSON example

              - ```
{
"fulfillmentOrderLineItemsToCancel" : [
  {   
    "fulfillmentOrderLineItemId" : "0a4xx00000000W0001",
    "quantity":1
  },
  {   
    "fulfillmentOrderLineItemId" : "0a4xx00000000W0002",
    "quantity":2
  }
]
}	
```

          - Properties

              - | Name | Type | Description | Required or Optional | Available Version |
| --- | --- | --- | --- | --- |
| <samp class="codeph nolang">fulfillmentOrder​LineItems​ToCancel</samp> | [Fulfillment Order Line Item Input](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_requests_fulfillment_order_line_item_input.htm "A FulfillmentOrderLineItem and quantity to cancel. You can cancel less than the full quantity, in which case you reallocate the canceled quantity to a different FulfillmentOrder.")[] | List of FulfillmentOrderLineItems
                  and quantities. | Required | 48.0 |

#### See Also

- [Fulfillment Orders, Cancel Item](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_fulfillment_orders_cancel_items.htm "Cancel FulfillmentOrderLineItems from a FulfillmentOrder. This action doesn’t cancel the associated OrderItemSummaries, so reallocate the canceled quantities to a new FulfillmentOrder.")