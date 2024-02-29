# Order Summaries, Ensure Funds Async

Ensure funds for an invoice and apply them to it. If needed, capture
      authorized funds by sending a request to a payment provider. This method inserts a background
      operation into an asynchronous job queue and returns the ID of that operation so you can track
      its status. Payment gateway responses appear in the payment gateway log and do not affect the
      background operation status.

          - Resource

              - ```
/commerce/order-management/order-summaries/orderSummaryId/async-actions/ensure-funds-async
```

          - Available version

              - 48.0

          - Requires Chatter

              - No

          - HTTP methods

              - POST

          - Request body for POST

              - [Ensure Funds Async Input](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_requests_ensure_funds_async_input.htm "ID of an invoice to ensure funds for and apply them to.")

          - Root XML tag

              - <samp class="codeph nolang">&lt;ensureFundsAsyncInput&gt;</samp>

          - JSON example

              - ```
{
  "invoiceId": "50gR000000000JNIAY"
}
```

          - Properties

              - | Name | Type | Description | Required or Optional | Available Version |
| --- | --- | --- | --- | --- |
| <samp class="codeph nolang">invoiceId</samp> | String | ID of the invoice. | Required | 48.0 |

          - Response body for POST

              - - When the HTTP status code indicates success, the response body is an [Ensure Funds Async Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_ensure_funds_async_output.htm "ID of the background operation."). The response
                body can still indicate processing errors.
- When the HTTP status code is in the 400 (client error) or 500 (server error)
                range, the response body is an [Error with Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_error_with_output.htm "Contains extra information about errors. In rare cases, an error message isn't enough to describe the reason for a failure. For example, when a conflicting precondition exists, the error result can include the information about the cause of the conflict."). The <samp class="codeph nolang">output</samp> property is an [Ensure Funds Async Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_ensure_funds_async_output.htm "ID of the background operation."), and the value
                of the <samp class="codeph nolang">enhancedErrorType</samp> property can be
                ignored.

          - Usage

              - This method checks the OrderPaymentSummaries associated with the specified         OrderSummary for  funds to apply to the invoice balance as follows:

![Note](/docs/resources/img/en-us/230.0?doc_id=images%2Ficon_note.png&folder=order_management_developer_guide)

#### Note

If multiple OrderPaymentSummaries have the same amount, their order of         selection is random.

1. Verify that the invoice balance doesn’t exceed the total amount of all the
          OrderPaymentSummaries.
2. If an OrderPaymentSummary exists with an amount that matches the invoice balance, use
          it.
3. Otherwise, if any OrderPaymentSummaries exist with an amount greater than the invoice
          balance, use the one with the smallest amount greater than the invoice balance.
4. Otherwise, select OrderPaymentSummaries in order from largest amount to smallest until
          their amounts meet or exceed the invoice balance.
5. If any selected funds are authorized, capture them.
6. Apply the selected funds to the invoice.