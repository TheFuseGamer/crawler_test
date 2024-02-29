# Fulfillment Orders, Cancel Item

Cancel FulfillmentOrderLineItems from a FulfillmentOrder. This
      action doesn’t cancel the associated OrderItemSummaries, so reallocate the canceled quantities
      to a new FulfillmentOrder.

          - Resource

              - ```
/commerce/fulfillment/fulfillment-orders/fulfillmentOrderId/actions/cancel-item
```

          - Available version

              - 48.0

          - Requires Chatter

              - No

          - HTTP methods

              - POST

          - Request body for POST

              - [Fulfillment Order Line Items To Cancel Input](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_requests_fulfillment_order_line_items_to_cancel_input.htm "A list of FulfillmentOrderLineItems and quantities to cancel.")

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

          - Response body for POST

              - - When the HTTP status code indicates success, the response body is a [Fulfillment Order Cancel Line Items Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_fulfillment_order_cancel_line_items_output.htm "Wraps the base output."). The response
                body can still indicate processing errors.
- When the HTTP status code is in the 400 (client error) or 500 (server error)
                range, the response body is an [Error with Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_error_with_output.htm "Contains extra information about errors. In rare cases, an error message isn't enough to describe the reason for a failure. For example, when a conflicting precondition exists, the error result can include the information about the cause of the conflict."). The <samp class="codeph nolang">output</samp> property is a [Fulfillment Order Cancel Line Items Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_fulfillment_order_cancel_line_items_output.htm "Wraps the base output."), and the value
                of the <samp class="codeph nolang">enhancedErrorType</samp> property can be
                ignored.