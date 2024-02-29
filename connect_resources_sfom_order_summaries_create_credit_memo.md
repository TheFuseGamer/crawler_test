# Order Summaries, Create Credit Memo

Create a credit memo to represent the refund for one or more change
      orders associated with an OrderSummary.

          - Resource

              - ```
/commerce/order-management/order-summaries/orderSummaryId/actions/create-credit-memo
```

          - Available version

              - 48.0

          - Requires Chatter

              - No

          - HTTP methods

              - POST

          - Request body for POST

              - [Create Credit Memo Input](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_requests_create_credit_memo_input.htm "A list of change orders used to create a credit memo.")

          - Root XML tag

              - <samp class="codeph nolang">&lt;createCreditMemoInput&gt;</samp>

          - JSON example

              - ```
{
  "changeOrderIds": [
    "801R0000000EAAkIAO"
  ]
}
```

          - Properties

              - | Name | Type | Description | Required or Optional | Available Version |
| --- | --- | --- | --- | --- |
| <samp class="codeph nolang">changeOrderIds</samp> | String[] | List of IDs of the change orders. | Required | 48.0 |

          - Response body for POST

              - - When the HTTP status code indicates success, the response body is a [Create Credit Memo Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_create_credit_memo_output.htm "ID of a created Credit Memo."). The response
                body can still indicate processing errors.
- When the HTTP status code is in the 400 (client error) or 500 (server error)
                range, the response body is an [Error with Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_error_with_output.htm "Contains extra information about errors. In rare cases, an error message isn't enough to describe the reason for a failure. For example, when a conflicting precondition exists, the error result can include the information about the cause of the conflict."). The <samp class="codeph nolang">output</samp> property is a [Create Credit Memo Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_create_credit_memo_output.htm "ID of a created Credit Memo."), and the value
                of the <samp class="codeph nolang">enhancedErrorType</samp> property can be
                ignored.