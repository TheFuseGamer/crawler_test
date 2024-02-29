# Create Order Payment Summary Input

An OrderSummary for which to create an OrderPaymentSummary, with the
      payment authorization or payments to include in it.

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

#### See Also

- [Order Payment Summaries](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_order_payment_summaries.htm "Create an OrderPaymentSummary for an OrderSummary. Specify a payment authorization or payments that share the same payment method. In an org with the multicurrency feature enabled, the OrderPaymentSummary inherits the CurrencyIsoCode value from the OrderSummary.")