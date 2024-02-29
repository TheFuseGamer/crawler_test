# Order Summaries, Ensure Refunds Async

Ensure refunds for a credit memo or excess funds by sending a request to a payment
      provider. This method inserts a background operation into an asynchronous job queue and
      returns the ID of that operation so you can track its status. Payment gateway responses appear
      in the payment gateway log and do not affect the background operation status.

          - Resource

              - ```
/commerce/order-management/order-summaries/orderSummaryId/async-actions/ensure-refunds-async
```

          - Available version

              - 48.0

          - Requires Chatter

              - No

          - HTTP methods

              - POST

          - Request body for POST

              - [Ensure Refunds Async Input](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_requests_ensure_refunds_async_input.htm "ID of a credit memo to ensure refunds for, an amount of excess funds to refund, or both. At least one is required.")

          - Root XML tag

              - <samp class="codeph nolang">&lt;ensureRefundsAsyncInput&gt;</samp>

          - JSON example

              - ```
{
  "creditMemoId": "50gR000000000JNIAY"
}
```

          - Properties

              - | Name | Type | Description | Required or Optional | Available Version |
| --- | --- | --- | --- | --- |
| <samp class="codeph nolang">creditMemoId</samp> | String | ID of the credit memo that represents a refund
                  amount. | Optional, but at least one input property is required | 48.0 |
| <samp class="codeph apex_code">excessFundsAmount</samp> | Double | Amount of excess funds to refund. | Optional, but at least one input property is required | 49.0 |

          - Response body for POST

              - - When the HTTP status code indicates success, the response body is an [Ensure Refunds Async Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_ensure_refunds_async_output.htm "ID of the background operation."). The response
                body can still indicate processing errors.
- When the HTTP status code is in the 400 (client error) or 500 (server error)
                range, the response body is an [Error with Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_error_with_output.htm "Contains extra information about errors. In rare cases, an error message isn't enough to describe the reason for a failure. For example, when a conflicting precondition exists, the error result can include the information about the cause of the conflict."). The <samp class="codeph nolang">output</samp> property is an [Ensure Refunds Async Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_ensure_refunds_async_output.htm "ID of the background operation."), and the value
                of the <samp class="codeph nolang">enhancedErrorType</samp> property can be
                ignored.