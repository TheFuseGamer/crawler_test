# Order Summaries, Submit Adjust

Adjust the price of one or more OrderItemSummaries from an
      OrderSummary, and create one or two corresponding change orders.

          - Resource

              - ```
/commerce/order-management/order-summaries/orderSummaryId/actions/adjust-item-submit
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

          - Usage

              - After submitting a price adjustment, process refunds as appropriate:
- If the discount only applied to OrderItemSummaries for which payment has not been
                captured, it does not require a refund. This situation normally applies to
                OrderItemSummaries in the US that have not been fulfilled.
- If the discount applied to OrderItemSummaries that have not been fulfilled and for
                which payment has been captured, process a refund. In this case, pass the <var class="keyword varname">totalExcessFundsAmount</var> from the response body to the
                  [Order Summaries, Ensure Refunds Async](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_order_summaries_ensure_refunds_async.htm "Ensure refunds for a credit memo or excess funds by sending a request to a payment provider. This method inserts a background operation into an asynchronous job queue and returns the ID of that operation so you can track its status. Payment gateway responses appear in the payment gateway log and do not affect the background operation status.") resource.
- If the discount applied to OrderItemSummaries that have been fulfilled, process a
                refund. Pass the <var class="keyword varname">postFulfillmentChangeOrderId</var> from the response
                body to the [Order Summaries, Create Credit Memo](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_order_summaries_create_credit_memo.htm "Create a credit memo to represent the refund for one or more change orders associated with an OrderSummary.") resource, then pass the
                CreditMemo to the [Order Summaries, Ensure Refunds Async](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_order_summaries_ensure_refunds_async.htm "Ensure refunds for a credit memo or excess funds by sending a request to a payment provider. This method inserts a background operation into an asynchronous job queue and returns the ID of that operation so you can track its status. Payment gateway responses appear in the payment gateway log and do not affect the background operation status.") resource.
- If the discount applied to both fulfilled and unfulfilled OrderItemSummaries for
                which payment has been captured, process both refunds. Pass the
                  <var class="keyword varname">postFulfillmentChangeOrderId</var> from the response body to the
                  [Order Summaries, Create Credit Memo](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_order_summaries_create_credit_memo.htm "Create a credit memo to represent the refund for one or more change orders associated with an OrderSummary.") resource, then
                pass the credit memo and the <var class="keyword varname">totalExcessFundsAmount</var> from the response body to the [Order Summaries, Ensure Refunds Async](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_order_summaries_ensure_refunds_async.htm "Ensure refunds for a credit memo or excess funds by sending a request to a payment provider. This method inserts a background operation into an asynchronous job queue and returns the ID of that operation so you can track its status. Payment gateway responses appear in the payment gateway log and do not affect the background operation status.") resource.