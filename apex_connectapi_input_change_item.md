# ConnectApi.ChangeItemInputRepresentation

Change to an OrderItemSummary, such as a return or cancel. You
      specify whether to prorate the associated shipping charge based on the price change. The
      OrderItemSummary can’t be a shipping charge.

| Property | Type | Description | Required or Optional | Available Version |
| --- | --- | --- | --- | --- |
| <samp class="codeph apex_code">orderItem​SummaryId</samp> | String | ID of the OrderItemSummary. | Required | 48.0 |
| <samp class="codeph apex_code">quantity</samp> | Double | Quantity to change. Use a positive value. For example, a
                  value of 2 means “cancel or return 2 units.” | Required | 48.0 |
| <samp class="codeph apex_code">reason</samp> | String | Reason for the change. The value must match one of the picklist
                  values on the Reason field of the OrderItemSummaryChange object. | Required | 48.0 |
| <samp class="codeph apex_code">shipping​Reduction​Flag</samp> | Boolean | Specifies whether to prorate the shipping
                  charge. | Required | 48.0 |

#### See Also

- [ConnectApi.ChangeInputRepresentation](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_connectapi_input_change.htm "A list of changes to OrderItemSummaries that make up an order change, such as a cancel or return.")
- [previewCancel(orderSummaryId, changeInput)](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_ConnectAPI_OrderSummary_static_methods.htm#apex_ConnectAPI_OrderSummary_previewCancel_1 "Retrieve the expected change order values for canceling one or more OrderItemSummaries from an OrderSummary, without actually executing the cancel.")
- [previewReturn(orderSummaryId, changeInput)](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_ConnectAPI_OrderSummary_static_methods.htm#apex_ConnectAPI_OrderSummary_previewReturn_1 "Retrieve the expected change order values for returning one or more OrderItemSummaries from an OrderSummary, without actually executing the return.")
- [submitCancel(orderSummaryId, changeInput)](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_ConnectAPI_OrderSummary_static_methods.htm#apex_ConnectAPI_OrderSummary_submitCancel_1 "Cancel one or more OrderItemSummaries from an OrderSummary, and create a corresponding change order.")
- [submitReturn(orderSummaryId, changeInput)](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_ConnectAPI_OrderSummary_static_methods.htm#apex_ConnectAPI_OrderSummary_submitReturn_1 "Return one or more OrderItemSummaries from an OrderSummary, and create a corresponding change order.")