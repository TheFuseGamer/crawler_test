# ConnectApi.FulfillmentOrderLineItemInputRepresentation

A FulfillmentOrderLineItem and quantity to cancel. You can cancel
      less than the full quantity, in which case you reallocate the canceled quantity to a different
      FulfillmentOrder.

| Property | Type | Description | Required or Optional | Available Version |
| --- | --- | --- | --- | --- |
| <samp class="codeph apex_code">fulfillmentOrder​LineItemId</samp> | String | ID of the
                FulfillmentOrderLineItem. | Required | 48.0 |
| <samp class="codeph apex_code">quantity</samp> | Double | Quantity to cancel. | Required | 48.0 |

#### See Also

- [ConnectApi.FulfillmentOrderLineItemsToCancelInputRepresentation](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_connectapi_input_fulfillment_order_line_items_to_cancel.htm "A list of FulfillmentOrderLineItems and quantities to cancel.")
- [cancelFulfillmentOrderLineItems(fulfillmentOrderId, cancelFulfillmentOrderLineItemsInput)](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_ConnectAPI_FulfillmentOrder_static_methods.htm#apex_ConnectAPI_FulfillmentOrder_cancelFulfillmentOrderLineItems_1 "Cancel FulfillmentOrderLineItems from a FulfillmentOrder. This action doesn’t cancel the associated OrderItemSummaries, so reallocate the canceled quantities to a new FulfillmentOrder.")