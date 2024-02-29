# Order Payment Summaries

Create an OrderPaymentSummary for an OrderSummary. Specify a payment
      authorization or payments that share the same payment method. In an org with the multicurrency
      feature enabled, the OrderPaymentSummary inherits the CurrencyIsoCode value from the
      OrderSummary.

          - Resource

              - ```
/commerce/order-management/order-payment-summaries
```

          - Available version

              - 48.0

          - Requires Chatter

              - No

          - HTTP methods

              - POST

          - Request body for POST

              - [Create Order Payment Summary Input](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_requests_create_order_payment_summary_input.htm "An OrderSummary for which to create an OrderPaymentSummary, with the payment authorization or payments to include in it.")

          - Root XML tag

              - <samp class="codeph nolang">&lt;orderPaymentSummaryInput&gt;</samp>

        - JSON examples

    - ```
{
  "orderSummaryId":"1Osxx0000000000001",
  "paymentAuthorizationId":"2Dgxx00000000W0001"
}
```

              - ```
{
  "orderSummaryId":"1Osxx0000000000001",
  "paymentIds":[  
    "0a3xx0000000085AAA",
    "0a3xx0000000085BBB"
  ]
}
```

          - Properties

              - | Name | Type | Description | Required or Optional | Available Version |
| --- | --- | --- | --- | --- |
| <samp class="codeph nolang">orderSummaryId</samp> | String | ID of the OrderSummary. | Required | 48.0 |
| <samp class="codeph nolang">payment​AuthorizationId</samp> | String | ID of the payment authorization. | Either a payment authorization or at least one payment is
                      required. | 48.0 |
| <samp class="codeph nolang">paymentIds</samp> | String[] | List of IDs of the payments. | Either a payment authorization or at least one payment is
                      required. | 48.0 |

          - Response body for POST

              - - When the HTTP status code indicates success, the response body is a [Create Order Payment Summary Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_create_order_payment_summary_output.htm "ID of the created Order Payment Summary."). The response
                body can still indicate processing errors.
- When the HTTP status code is in the 400 (client error) or 500 (server error)
                range, the response body is an [Error with Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_error_with_output.htm "Contains extra information about errors. In rare cases, an error message isn't enough to describe the reason for a failure. For example, when a conflicting precondition exists, the error result can include the information about the cause of the conflict."). The <samp class="codeph nolang">output</samp> property is a [Create Order Payment Summary Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_create_order_payment_summary_output.htm "ID of the created Order Payment Summary."), and the value
                of the <samp class="codeph nolang">enhancedErrorType</samp> property can be
                ignored.