# Adjust Order Item Summary Input

A list of price adjustments to OrderItemSummaries that make up a
      price adjustment to an order.

          - Root XML tag

              - <samp class="codeph nolang">&lt;adjustOrderItemSummaryInput&gt;</samp>

          - JSON example

              - ```
{
  "adjustItems": [{
    "reason": "Unknown",
    "amount": 45,
    "appeasementType": "AmountWithoutTax",
    "orderItemSummaryId": "10uxx0000004EXLAA2",
    "description": "foobar"
  }]
}
```

          - Properties

              - | Name | Type | Description | Required or Optional | Available Version |
| --- | --- | --- | --- | --- |
| <samp class="codeph nolang">adjustItems</samp> | [Adjust Item Input](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_requests_adjust_item_input.htm "A price adjustment to an OrderItemSummary. It only supports discounts, not increases.")[] | List of price adjustments to
                OrderItemSummaries. | Required | 49.0 |

#### See Also

- [Order Summaries, Preview Adjust](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_order_summaries_preview_adjust.htm "Retrieve the expected results of adjusting the price of one or more OrderItemSummaries from an OrderSummary, without actually executing the adjustment. The response data contains the financial changes that would result from submitting the proposed adjustment.")
- [Order Summaries, Submit Adjust](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_order_summaries_submit_adjust.htm "Adjust the price of one or more OrderItemSummaries from an OrderSummary, and create one or two corresponding change orders.")