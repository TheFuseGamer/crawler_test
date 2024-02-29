# Change Input

A list of changes to OrderItemSummaries that make up an order
      change, such as a cancel or return.

          - Root XML tag

              - <samp class="codeph nolang">&lt;changeInput&gt;</samp>

          - JSON example

              - ```
{
  "changeItems": [
    {
      "orderItemSummaryId": "10uxx0000004FYDAA2",
      "quantity": 1.0,
      "reason": "Wrong Item",
      "shippingReductionFlag": true
    }
  ]
}
```

          - Properties

              - | Name | Type | Description | Required or Optional | Available Version |
| --- | --- | --- | --- | --- |
| <samp class="codeph nolang">changeItems</samp> | [Change Item Input](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_requests_change_item_input.htm "Change to an OrderItemSummary, such as a return or cancel. You specify whether to prorate the associated shipping charge based on the price change. The OrderItemSummary can’t be a shipping charge.")[] | List of changes to OrderItemSummaries. | Required | 48.0 |

#### See Also

- [Order Summaries, Preview Cancel](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_order_summaries_preview_cancel.htm "Retrieve the expected change order values for canceling one or more OrderItemSummaries from an OrderSummary, without actually executing the cancel.")
- [Order Summaries, Preview Return](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_order_summaries_preview_return.htm "Retrieve the expected change order values for returning one or more OrderItemSummaries from an OrderSummary, without actually executing the return.")
- [Order Summaries, Submit Cancel](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_order_summaries_submit_cancel.htm "Cancel one or more OrderItemSummaries from an OrderSummary, and create a corresponding change order.")
- [Order Summaries, Submit Return](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_order_summaries_submit_return.htm "Return one or more OrderItemSummaries from an OrderSummary, and create a corresponding change order.")