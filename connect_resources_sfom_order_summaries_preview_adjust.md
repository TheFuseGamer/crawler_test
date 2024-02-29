# Order Summaries, Preview Adjust

Retrieve the expected results of adjusting the price of one or more
      OrderItemSummaries from an OrderSummary, without actually executing the adjustment. The
      response data contains the financial changes that would result from submitting the proposed
      adjustment.

          - Resource

              - ```
/commerce/order-management/order-summaries/orderSummaryId/actions/adjust-item-preview
```

          - Available version

              - 49.0

          - Requires Chatter

              - No

          - HTTP methods

              - POST

          - Request body for POST

              - [Adjust Order Item Summary Input](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_requests_adjust_order_item_summary_input.htm "A list of price adjustments to OrderItemSummaries that make up a price adjustment to an order.")

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

          - Response body for POST

              - - When the HTTP status code indicates success, the response body is an [Adjust Order Summary Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_adjust_order_summary.htm "Output representation of the financial changes for an adjust items action. For a preview action, these values are the expected output. For a submit action, these values are the actual output."). The response body can still
                indicate processing errors.
- When the HTTP status code is in the 400 (client error) or 500 (server error)
                range, the response body is an [Error with Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_error_with_output.htm "Contains extra information about errors. In rare cases, an error message isn't enough to describe the reason for a failure. For example, when a conflicting precondition exists, the error result can include the information about the cause of the conflict."). The <samp class="codeph nolang">output</samp> property is an [Adjust Order Summary Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_adjust_order_summary.htm "Output representation of the financial changes for an adjust items action. For a preview action, these values are the expected output. For a submit action, these values are the actual output."), and the value of the <samp class="codeph nolang">enhancedErrorType</samp> property can be ignored.