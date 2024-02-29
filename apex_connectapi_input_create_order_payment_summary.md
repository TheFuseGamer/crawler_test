# ConnectApi.CreateOrderPaymentSummaryInputRepresentation

An OrderSummary for which to create an OrderPaymentSummary, with the
      payment authorization or payments to include in it.

| Property | Type | Description | Required or Optional | Available Version |
| --- | --- | --- | --- | --- |
| <samp class="codeph apex_code">orderSummaryId</samp> | String | ID of the OrderSummary. | Required | 48.0 |
| <samp class="codeph apex_code">payment​AuthorizationId</samp> | String | ID of the payment authorization. | Either a payment authorization or at least one payment is required. | 48.0 |
| <samp class="codeph apex_code">paymentIds</samp> | List&lt;String&gt; | List of IDs of the payments. | Either a payment authorization or at least one payment is required. | 48.0 |

#### See Also

- [createOrderPaymentSummary(orderPaymentSummaryInput)](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_ConnectAPI_OrderPaymentSummary_static_methods.htm#apex_ConnectAPI_OrderPaymentSummary_createOrderPaymentSummary_1 "Create an OrderPaymentSummary for an OrderSummary. Specify a payment authorization or payments that share the same payment method. In an org with the multicurrency feature enabled, the OrderPaymentSummary inherits the CurrencyIsoCode value from the OrderSummary.")