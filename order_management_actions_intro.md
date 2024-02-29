# Order Management Invocable Actions

Salesforce Order Management provides standard invocable actions to support order management
    functionality.

- **[Salesforce Order Management Actions](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/actions_obj_order_management.htm)**

Manage, fulfill, and service orders in flows with Salesforce Order    Management.
- **[Flow Core Action for Order Management: Adjust Order Item Summaries Preview](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/flow_ref_elements_om_actions_adjust_ois_preview.htm)**

Preview the expected results of adjusting the price of one or more       order product summaries on an order summary, without executing the adjustment. You can only       apply a discount, not an increase. The output of this action contains the values that would be       set on the change orders created by submitting the proposed adjustment.
- **[Flow Core Action for Order Management: Adjust Order Item Summaries Submit](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/flow_ref_elements_om_actions_adjust_ois_submit.htm)**

Adjust the price of one or more order product summaries on an order       summary. You can only apply a discount, not an increase. This action creates one or two change       order records.
- **[Flow Core Action for Order Management: Cancel Fulfillment Order Item](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/flow_ref_elements_om_actions_cancel_fo_item.htm)**

Cancel fulfillment order products from a fulfillment order. You can       cancel more than one product, and specify a quantity to cancel for each of them. This action       doesn’t cancel the associated order product summaries; it only reduces their allocated       quantities. Usually, you reallocate the canceled quantities to a new fulfillment     order.
- **[Flow Core Action for Order Management: Cancel Order Item Summaries Preview](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/flow_ref_elements_om_actions_cancel_ois_preview.htm)**

Preview the expected results of canceling one or more order product       summaries from an order summary without executing the cancel. The output of this action       contains the values that would be set on the change order created by submitting the proposed       cancel.
- **[Flow Core Action for Order Management: Cancel Order Item Summaries Submit](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/flow_ref_elements_om_actions_cancel_ois_submit.htm)**

Cancel one or more order product summaries from an order summary. This       action creates a change order record.
- **[Flow Core Action for Order Management: Create Credit Memo](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/flow_ref_elements_om_actions_create_credit_memo.htm)**

Create a credit memo to represent the refund for one or more change       orders associated with an order summary.
- **[Flow Core Action for Order Management: Create Fulfillment Order](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/flow_ref_elements_om_actions_create_fulfillment_order.htm)**

Create one or more fulfillment orders and fulfillment order products       for an order delivery group summary, which defines a recipient and delivery method. You       specify the order product summaries to fulfill and the fulfillment locations to handle them.       If you specify multiple fulfillment locations, a fulfillment order is created for each       one.
- **[Flow Core Action for Order Management: Create an Invoice from Fulfillment Order](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/flow_ref_elements_om_actions_create_invoice_from_fo.htm)**

Create an invoice for a fulfillment order that doesn’t have       one.
- **[Flow Core Action for Order Management: Create Order Payment Summary](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/flow_ref_elements_om_actions_create_op_summary.htm)**

Create an order payment summary for a payment authorization or       payments that use the same payment method and are attached to the same order     summary.
- **[Flow Core Action for Order Management: Create Order Summary](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/flow_ref_elements_om_actions_create_order_summary.htm)**

Create an order summary based on an order. That order is considered       the original order for the order summary. Subsequent change orders that apply to the order       summary are also represented as order records.
- **[Flow Core Action for Order Management: Ensure Funds Async](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/flow_ref_elements_om_actions_ensure_funds_async.htm)**

Ensure funds for an invoice and apply them to it. If needed, capture       authorized funds by sending a request to a payment provider. This action inserts a background       operation into an asynchronous job queue and returns the ID of that operation so you can track       its status. Payment gateway responses appear in the payment gateway log and do not affect the       background operation status.
- **[Flow Core Action for Order Management: Ensure Refunds Async](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/flow_ref_elements_om_actions_ensure_refunds_async.htm)**

Ensure refunds for a credit memo or excess funds by sending a request to a payment       provider. This action inserts a background operation into an asynchronous job queue and       returns the ID of that operation so you can track its status. Payment gateway responses appear       in the payment gateway log and do not affect the background operation status.
- **[Flow Core Action for Order Management: Return Order Item Summaries Preview](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/flow_ref_elements_om_actions_return_ois_preview.htm)**

Preview the expected results of returning one or more order product       summaries from an order summary without executing the return. The output of this action       contains the values that would be set on the change order created by submitting the proposed       return.
- **[Flow Core Action for Order Management: Return Order Item Summaries Submit](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/flow_ref_elements_om_actions_return_ois_submit.htm)**

Return one or more order product summaries from an order summary. This       action creates a change order record.