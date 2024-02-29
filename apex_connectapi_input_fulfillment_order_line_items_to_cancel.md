# ConnectApi.FulfillmentOrderLineItemsToCancelInputRepresentation

A list of FulfillmentOrderLineItems and quantities to
    cancel.

| Property | Type | Description | Required or Optional | Available Version |
| --- | --- | --- | --- | --- |
| <samp class="codeph apex_code">fulfillment​OrderLine​ItemsToCancel</samp> | List&lt;<samp class="codeph apex_code"><a class="xref" href="atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_connectapi_input_fulfillment_order_line_item.htm" title="A FulfillmentOrderLineItem and quantity to cancel. You can cancel less than the full quantity, in which case you reallocate the canceled quantity to a different FulfillmentOrder.">ConnectApi.​FulfillmentOrder​LineItemInput​Representation</a></samp>&gt; | List of FulfillmentOrderLineItems
                  and quantities. | Required | 48.0 |

#### See Also

- [cancelFulfillmentOrderLineItems(fulfillmentOrderId, cancelFulfillmentOrderLineItemsInput)](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_ConnectAPI_FulfillmentOrder_static_methods.htm#apex_ConnectAPI_FulfillmentOrder_cancelFulfillmentOrderLineItems_1 "Cancel FulfillmentOrderLineItems from a FulfillmentOrder. This action doesn’t cancel the associated OrderItemSummaries, so reallocate the canceled quantities to a new FulfillmentOrder.")