# ConnectApi.BaseOutputRepresentation

Base Order Management output class.

This class is abstract.

Superclass of:
- [ConnectApi.AdjustOrderSummaryOutputRepresentation](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_connectapi_output_adjust_order_summary_output.htm "Output representation of the financial changes for an adjust items action. For a preview action, these values are the expected output. For a submit action, these values are the actual output.")
- [ConnectApi.CreateCreditMemoOutputRepresentation](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_connectapi_output_create_credit_memo_output.htm "ID of a created Credit Memo.")
- [ConnectApi.CreateOrderPaymentSummaryOutputRepresentation](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_connectapi_output_create_order_payment_summary_output.htm "ID of the created Order Payment Summary.")
- [ConnectApi.EnsureFundsAsyncOutputRepresentation](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_connectapi_output_ensure_funds_async_output.htm "ID of the background operation.")
- [ConnectApi.EnsureRefundsAsyncOutputRepresentation](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_connectapi_output_ensure_refunds_async_output.htm "ID of the background operation.")
- [link unavailable]
- [link unavailable]
- [ConnectApi.FulfillmentOrderCancelLineItemsOutputRepresentation](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_connectapi_output_fulfillment_order_cancel_line_items_output.htm "Wraps the base output.")
- [ConnectApi.FulfillmentOrderInvoiceOutputRepresentation](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_connectapi_output_fulfillment_order_invoice_output.htm "ID of the created invoice.")
- [ConnectApi.FulfillmentOrderOutputRepresentation](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_connectapi_output_fulfillment_order_output.htm "A list of IDs of the created FulfillmentOrders.")
- [link unavailable]
- [ConnectApi.OrderSummaryOutputRepresentation](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_connectapi_output_order_summary_output.htm "ID of the created Order Summary.")
- [ConnectApi.PreviewCancelOutputRepresentation](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_connectapi_output_preview_cancel_output.htm "Expected financial values for a proposed cancel action.")
- [ConnectApi.PreviewReturnOutputRepresentation](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_connectapi_output_preview_return_output.htm "Expected financial values for a proposed return action.")
- [link unavailable]
- [ConnectApi.SubmitCancelOutputRepresentation](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_connectapi_output_submit_cancel_output.htm "ID of the change order created for a cancel action, and a set of its financial values.")
- [ConnectApi.SubmitReturnOutputRepresentation](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_connectapi_output_submit_return_output.htm "ID of the change order created for a return action, and a set of its financial values.")

| Property Name | Type | Description | Available Version |
| --- | --- | --- | --- |
| <samp class="codeph apex_code">errors</samp> | List&lt;[<samp class="codeph apex_code">ConnectApi.​ErrorResponse</samp>](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_connectapi_output_error_response.htm "Base error response.")&gt; | Any errors that were returned. | 48.0 |
| <samp class="codeph apex_code">success</samp> | Boolean | Indicates whether the transaction was successful. | 48.0 |