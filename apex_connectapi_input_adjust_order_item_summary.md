# ConnectApi.AdjustOrderItemSummaryInputRepresentation

A list of price adjustments to OrderItemSummaries that make up a
      price adjustment to an order.

| Property | Type | Description | Required or Optional | Available Version |
| --- | --- | --- | --- | --- |
| <samp class="codeph apex_code">adjustItems</samp> | List&lt;<samp class="codeph apex_code"><a class="xref" href="atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_connectapi_input_adjust_item.htm" title="A price adjustment to an OrderItemSummary. It only supports discounts, not increases.">ConnectApi.​AdjustItemInputRepresentation</a></samp>&gt; | List of price adjustments to
                OrderItemSummaries. | Required | 49.0 |

#### See Also

- [adjustPreview(orderSummaryId, adjustInput)](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_ConnectAPI_OrderSummary_static_methods.htm#apex_ConnectAPI_OrderSummary_adjustPreview_1 "Retrieve the expected results of adjusting the price of one or more OrderItemSummaries from an OrderSummary, without actually executing the adjustment. The response data contains the financial changes that would result from submitting the proposed adjustment.")
- [adjustSubmit(orderSummaryId, adjustInput)](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_ConnectAPI_OrderSummary_static_methods.htm#apex_ConnectAPI_OrderSummary_adjustSubmit_1 "Adjust the price of one or more OrderItemSummaries from an OrderSummary, and create one or two corresponding change orders.")