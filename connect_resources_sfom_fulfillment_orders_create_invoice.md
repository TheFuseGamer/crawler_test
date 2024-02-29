# Fulfillment Orders, Create Invoice

Create an invoice for a FulfillmentOrder that doesn’t have
    one.

          - Resource

              - ```
/commerce/fulfillment/fulfillment-orders/fulfillmentOrderId/actions/create-invoice
```

          - Available version

              - 48.0

          - Requires Chatter

              - No

          - HTTP methods

              - POST

          - Request body for POST

              - [Fulfillment Order Invoice Input](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_requests_fulfillment_order_invoice_input.htm "Use an empty request body for this input.")

          - Root XML tag

              - <samp class="codeph nolang">&lt;fulfillmentOrderInvoiceInput&gt;</samp>

          - JSON example

              - ```
{
}
```

          - Properties

              - None.

          - Response body for POST

              - - When the HTTP status code indicates success, the response body is a [Fulfillment Order Invoice Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_fulfillment_order_invoice_output.htm "ID of the created invoice."). The response
                body can still indicate processing errors.
- When the HTTP status code is in the 400 (client error) or 500 (server error)
                range, the response body is an [Error with Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_error_with_output.htm "Contains extra information about errors. In rare cases, an error message isn't enough to describe the reason for a failure. For example, when a conflicting precondition exists, the error result can include the information about the cause of the conflict."). The <samp class="codeph nolang">output</samp> property is a [Fulfillment Order Invoice Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_fulfillment_order_invoice_output.htm "ID of the created invoice."), and the value
                of the <samp class="codeph nolang">enhancedErrorType</samp> property can be
                ignored.