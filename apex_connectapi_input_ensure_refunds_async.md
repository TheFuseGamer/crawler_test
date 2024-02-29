# ConnectApi.EnsureRefundsAsyncInputRepresentation

ID of a credit memo to ensure refunds for, an amount of excess funds
      to refund, or both. At least one is required.

| Property | Type | Description | Required or Optional | Available Version |
| --- | --- | --- | --- | --- |
| <samp class="codeph apex_code">creditMemoId</samp> | String | ID of the credit memo that represents a refund
                  amount. | Optional, but at least one input property is required | 48.0 |
| <samp class="codeph apex_code">excessFundsAmount</samp> | Double | Amount of excess funds to refund. | Optional, but at least one input property is required | 49.0 |

#### See Also

- [ensureRefundsAsync(orderSummaryId, ensureRefundsInput)](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_ConnectAPI_OrderSummary_static_methods.htm#apex_ConnectAPI_OrderSummary_ensureRefundsAsync_1 "Ensure refunds for a credit memo or excess funds by sending a request to a payment provider. This method inserts a background operation into an asynchronous job queue and returns the ID of that operation so you can track its status. Payment gateway responses appear in the payment gateway log and do not affect the background operation status.")