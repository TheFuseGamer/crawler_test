# Order Summaries, Preview Cancel

Retrieve the expected change order values for canceling one or more
      OrderItemSummaries from an OrderSummary, without actually executing the
    cancel.

          - Resource

              - ```
/commerce/order-management/order-summaries/orderSummaryId/actions/preview-cancel
```

          - Available version

              - 48.0

          - Requires Chatter

              - No

          - HTTP methods

              - POST

          - Request body for POST

              - [Change Input](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_requests_change_input.htm "A list of changes to OrderItemSummaries that make up an order change, such as a cancel or return.")

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

          - Response body for POST

              - - When the HTTP status code indicates success, the response body is a [Preview Cancel Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_preview_cancel_output.htm "Expected financial values for a proposed cancel action."). The response body can still
                indicate processing errors.
- When the HTTP status code is in the 400 (client error) or 500 (server error)
                range, the response body is an [Error with Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_error_with_output.htm "Contains extra information about errors. In rare cases, an error message isn't enough to describe the reason for a failure. For example, when a conflicting precondition exists, the error result can include the information about the cause of the conflict."). The <samp class="codeph nolang">output</samp> property is a [Preview Cancel Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_preview_cancel_output.htm "Expected financial values for a proposed cancel action."), and the value of the <samp class="codeph nolang">enhancedErrorType</samp> property can be ignored.