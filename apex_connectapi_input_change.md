# ConnectApi.ChangeInputRepresentation

A list of changes to OrderItemSummaries that make up an order
      change, such as a cancel or return.

| Property | Type | Description | Required or Optional | Available Version |
| --- | --- | --- | --- | --- |
| <samp class="codeph apex_code">changeItems</samp> | List&lt;<samp class="codeph apex_code"><a class="xref" href="atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_connectapi_input_change_item.htm" title="Change to an OrderItemSummary, such as a return or cancel. You specify whether to prorate the associated shipping charge based on the price change. The OrderItemSummary can’t be a shipping charge.">ConnectApi.​ChangeItemInput​Representation</a></samp>&gt; | List of changes to OrderItemSummaries. | Required | 48.0 |

#### See Also

- [previewCancel(orderSummaryId, changeInput)](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_ConnectAPI_OrderSummary_static_methods.htm#apex_ConnectAPI_OrderSummary_previewCancel_1 "Retrieve the expected change order values for canceling one or more OrderItemSummaries from an OrderSummary, without actually executing the cancel.")
- [previewReturn(orderSummaryId, changeInput)](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_ConnectAPI_OrderSummary_static_methods.htm#apex_ConnectAPI_OrderSummary_previewReturn_1 "Retrieve the expected change order values for returning one or more OrderItemSummaries from an OrderSummary, without actually executing the return.")
- [submitCancel(orderSummaryId, changeInput)](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_ConnectAPI_OrderSummary_static_methods.htm#apex_ConnectAPI_OrderSummary_submitCancel_1 "Cancel one or more OrderItemSummaries from an OrderSummary, and create a corresponding change order.")
- [submitReturn(orderSummaryId, changeInput)](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_ConnectAPI_OrderSummary_static_methods.htm#apex_ConnectAPI_OrderSummary_submitReturn_1 "Return one or more OrderItemSummaries from an OrderSummary, and create a corresponding change order.")