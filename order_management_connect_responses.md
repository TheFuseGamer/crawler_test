# Salesforce Order Management Responses

Salesforce Order Management includes these Chatter Connect API responses.

- **[Adjust Order Summary Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_adjust_order_summary.htm)**

Output representation of the financial changes for an adjust items       action. For a preview action, these values are the expected output. For a submit action, these       values are the actual output.
- **[Change Item Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_change_item_output.htm)**

The financial changes resulting from a change to one or more       OrderItemSummaries. Most of the values represent the deltas of the values on the associated       OrderSummary. The sign of each value is the opposite of the corresponding value on a change       order record. For example, a discount is a positive value here and a negative value on a       change order record.
- **[Create Credit Memo Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_create_credit_memo_output.htm)**

ID of a created Credit Memo.
- **[Create Order Payment Summary Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_create_order_payment_summary_output.htm)**

ID of the created Order Payment Summary.
- **[Ensure Funds Async Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_ensure_funds_async_output.htm)**

ID of the background operation.
- **[Ensure Refunds Async Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_ensure_refunds_async_output.htm)**

ID of the background operation.
- **[Error Response Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_error_response.htm)**

Error response representation
- **[Error with Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_error_with_output.htm)**

Contains extra information about errors. In rare cases, an error message isn't enough to   describe the reason for a failure. For example, when a conflicting precondition exists, the error   result can include the information about the cause of the conflict.
- **[Fulfillment Order Cancel Line Items Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_fulfillment_order_cancel_line_items_output.htm)**

Wraps the base output.
- **[Fulfillment Order Invoice Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_fulfillment_order_invoice_output.htm)**

ID of the created invoice.
- **[Fulfillment Order Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_fulfillment_order_output.htm)**

A list of IDs of the created FulfillmentOrders.
- **[Order Summary Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_order_summary_output.htm)**

ID of the created Order Summary.
- **[Preview Cancel Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_preview_cancel_output.htm)**

Expected financial values for a proposed cancel     action.
- **[Preview Return Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_preview_return_output.htm)**

Expected financial values for a proposed return     action.
- **[Submit Cancel Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_submit_cancel_output.htm)**

ID of the change order created for a cancel action, and a set of its       financial values.
- **[Submit Return Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_submit_return_output.htm)**

ID of the change order created for a return action, and a set of its       financial values.