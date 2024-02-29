# Order Summaries, Submit Return

Return one or more OrderItemSummaries from an OrderSummary, and
      create a corresponding change order.

          - Resource

              - ```
/commerce/order-management/order-summaries/orderSummaryId/actions/submit-return
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

              - - When the HTTP status code indicates success, the response body is a [Submit Return Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_submit_return_output.htm "ID of the change order created for a return action, and a set of its financial values."). The response body can still
                indicate processing errors.
- When the HTTP status code is in the 400 (client error) or 500 (server error)
                range, the response body is an [Error with Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_error_with_output.htm "Contains extra information about errors. In rare cases, an error message isn't enough to describe the reason for a failure. For example, when a conflicting precondition exists, the error result can include the information about the cause of the conflict."). The <samp class="codeph nolang">output</samp> property is a [Submit Return Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_submit_return_output.htm "ID of the change order created for a return action, and a set of its financial values."), and the value of the <samp class="codeph nolang">enhancedErrorType</samp> property can be ignored.

          - Usage

              - After submitting a return, process a refund. Pass the <var class="keyword varname">changeOrderId</var>
            from the response body to the [Order Summaries, Create Credit Memo](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_order_summaries_create_credit_memo.htm "Create a credit memo to represent the refund for one or more change orders associated with an OrderSummary.") resource, then pass the
            CreditMemo to the [Order Summaries, Ensure Refunds Async](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_order_summaries_ensure_refunds_async.htm "Ensure refunds for a credit memo or excess funds by sending a request to a payment provider. This method inserts a background operation into an asynchronous job queue and returns the ID of that operation so you can track its status. Payment gateway responses appear in the payment gateway log and do not affect the background operation status.") resource.