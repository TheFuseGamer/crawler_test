# Change Item Input

Change to an OrderItemSummary, such as a return or cancel. You
      specify whether to prorate the associated shipping charge based on the price change. The
      OrderItemSummary can’t be a shipping charge.

          - Root XML tag

              - <samp class="codeph nolang">&lt;changeItem&gt;</samp>

          - JSON example

              - ```
{
  "orderItemSummaryId": "10uxx0000004FYDAA2",
  "quantity": 1.0,
  "reason": "Wrong Item",
  "shippingReductionFlag": true
}
```

          - Properties

              - | Name | Type | Description | Required or Optional | Available Version |
| --- | --- | --- | --- | --- |
| <samp class="codeph nolang">orderItem​SummaryId</samp> | String | ID of the OrderItemSummary. | Required | 48.0 |
| <samp class="codeph nolang">quantity</samp> | Double | Quantity to change. Use a positive value. For example, a
                  value of 2 means “cancel or return 2 units.” | Required | 48.0 |
| <samp class="codeph nolang">reason</samp> | String | Reason for the change. The value must match one of the picklist
                  values on the Reason field of the OrderItemSummaryChange object. | Required | 48.0 |
| <samp class="codeph nolang">shippingReduction​Flag</samp> | Boolean | Specifies whether to prorate the shipping
                  charge. | Required | 48.0 |

#### See Also

- [Order Summaries, Preview Cancel](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_order_summaries_preview_cancel.htm "Retrieve the expected change order values for canceling one or more OrderItemSummaries from an OrderSummary, without actually executing the cancel.")
- [Order Summaries, Preview Return](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_order_summaries_preview_return.htm "Retrieve the expected change order values for returning one or more OrderItemSummaries from an OrderSummary, without actually executing the return.")
- [Order Summaries, Submit Cancel](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_order_summaries_submit_cancel.htm "Cancel one or more OrderItemSummaries from an OrderSummary, and create a corresponding change order.")
- [Order Summaries, Submit Return](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_order_summaries_submit_return.htm "Return one or more OrderItemSummaries from an OrderSummary, and create a corresponding change order.")
- [Change Input](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_requests_change_input.htm "A list of changes to OrderItemSummaries that make up an order change, such as a cancel or return.")