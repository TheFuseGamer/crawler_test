# ConnectApi.FulfillmentGroupInputRepresentation

A list of OrderItemSummaries to be fulfilled together, and the
      fulfillment location that will handle them. The fulfillment type is one of the values defined
      for the Type field on the FulfillmentOrder object, such as “Warehouse” or “Retail Store.” The
      specified type is assigned to the FulfillmentOrder for this fulfillment
    group.

| Property | Type | Description | Required or Optional | Available Version |
| --- | --- | --- | --- | --- |
| <samp class="codeph apex_code">fulfilledFrom​LocationId</samp> | String | ID of the fulfillment location. | Required | 48.0 |
| <samp class="codeph apex_code">fulfillmentType</samp> | String | Fulfillment type. One of the Type field values defined
                  for FulfillmentOrders. | Required | 48.0 |
| <samp class="codeph apex_code">orderItem​Summaries</samp> | List&lt;<samp class="codeph apex_code"><a class="xref" href="atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_connectapi_input_order_item_summary.htm" title="An OrderItemSummary and quantity.">ConnectApi.​OrderItem​SummaryInput​Representation</a></samp>&gt; | List of OrderItemSummaries. | Required | 48.0 |

#### See Also

- [ConnectApi.FulfillmentOrderInputRepresentation](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_connectapi_input_fulfillment_order.htm "An OrderDeliveryGroupSummary that defines a delivery method and recipient, and a list of fulfillment groups to assign to FulfillmentOrders. Each fulfillment group is a set of OrderItemSummaries that match the OrderDeliveryGroupSummary and share the same fulfillment location. The method creates a FulfillmentOrder for each fulfillment group and a FulfillmentOrderLineItem for each OrderItemSummary.")
- [createFulfillmentOrders(fulfillmentOrderInput)](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_ConnectAPI_FulfillmentOrder_static_methods.htm#apex_ConnectAPI_FulfillmentOrder_createFulfillmentOrders_1 "Create one or more FulfillmentOrders and FulfillmentOrderLineItems for an OrderDeliveryGroupSummary, which defines a delivery method and recipient for an OrderSummary. You specify the OrderItemSummaries to allocate, which can be fulfilled from different locations. Specifying multiple fulfillment groups creates one FulfillmentOrder for each location. For each OrderItemSummary, a FulfillmentOrderLineItem is created and assigned to the corresponding FulfillmentOrder.")