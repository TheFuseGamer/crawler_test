# ConnectApi.EnsureFundsAsyncInputRepresentation

ID of an invoice to ensure funds for and apply them
    to.

| Property | Type | Description | Required or Optional | Available Version |
| --- | --- | --- | --- | --- |
| <samp class="codeph apex_code">invoiceId</samp> | String | ID of the invoice. | Required | 48.0 |

#### See Also

- [ensureFundsAsync(orderSummaryId, ensureFundsInput)](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_ConnectAPI_OrderSummary_static_methods.htm#apex_ConnectAPI_OrderSummary_ensureFundsAsync_1 "Ensure funds for an invoice and apply them to it. If needed, capture authorized funds by sending a request to a payment provider. This method inserts a background operation into an asynchronous job queue and returns the ID of that operation so you can track its status. Payment gateway responses appear in the payment gateway log and do not affect the background operation status.")