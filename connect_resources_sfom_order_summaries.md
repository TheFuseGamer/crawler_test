# Order Summaries

Create an OrderSummary based on an order. That order is considered
      the original order for the OrderSummary. Subsequent change orders that apply to the
      OrderSummary are also represented as orders. You can specify whether the order is managed in
      Salesforce Order Management or by an external system. Most Salesforce Order Management APIs
      can run only on orders that it manages.

          - Resource

              - ```
/commerce/order-management/order-summaries
```

          - Available version

              - 48.0

          - Requires Chatter

              - No

          - HTTP methods

              - POST

          - Request body for POST

              - [Order Summary Input](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_requests_order_summary_input.htm "An order from which to create an OrderSummary, and whether it is managed in Salesforce Order Management. Optionally, you can specify an OrderNumber or Status.")

          - Root XML tag

              - <samp class="codeph nolang">&lt;orderSummaryInput&gt;</samp>

          - JSON example

              - ```
{
  "orderId": "801xx000003GbTgAAK"
}
```

          - Properties

              - | Name | Type | Description | Required or Optional | Available Version |
| --- | --- | --- | --- | --- |
| <samp class="codeph apex_code">name</samp> | String | Specifies an OrderNumber to assign to the order
                summary. | Optional | 50.0 |
| <samp class="codeph nolang">orderId</samp> | String | ID of the original order. | Required | 48.0 |
| <samp class="codeph nolang">orderLifeCycleType</samp> | String | Specifies whether the order is managed in
                  Salesforce Order Management or by an external system. It can have one of these
                  values:<ul class="ul bulletList">
                  <li class="li">
<samp class="codeph apex_code">MANAGED</samp>—Managed in Salesforce
                    Order Management.</li>

                  <li class="li">
<samp class="codeph apex_code">UNMANAGED</samp>—Managed by an
                    external system.</li>

                </ul>
If no value is specified, the default is
                    <samp class="codeph apex_code">MANAGED</samp>. | Optional | 49.0 |
| <samp class="codeph apex_code">status</samp> | String | Specifies a status to assign to the order summary. The value
                  must match one of the picklist values on the Status field of the OrderSummary
                  object. | Optional | 50.0 |

          - Response body for POST

              - - When the HTTP status code indicates success, the response body is an [Order Summary Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_order_summary_output.htm "ID of the created Order Summary."). The response body can still
                indicate processing errors.
- When the HTTP status code is in the 400 (client error) or 500 (server error)
                range, the response body is an [Error with Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_error_with_output.htm "Contains extra information about errors. In rare cases, an error message isn't enough to describe the reason for a failure. For example, when a conflicting precondition exists, the error result can include the information about the cause of the conflict."). The <samp class="codeph nolang">output</samp> property is an [Order Summary Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_order_summary_output.htm "ID of the created Order Summary."), and the value of the <samp class="codeph nolang">enhancedErrorType</samp> property can be ignored.