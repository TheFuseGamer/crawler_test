# ConnectApi.OrderSummaryInputRepresentation

An order from which to create an OrderSummary, and whether it is
      managed in Salesforce Order Management. Optionally, you can specify an OrderNumber or
      Status.

| Property | Type | Description | Required or Optional | Available Version |
| --- | --- | --- | --- | --- |
| <samp class="codeph apex_code">name</samp> | String | Specifies an OrderNumber to assign to the order
                summary. | Optional | 50.0 |
| <samp class="codeph apex_code">orderId</samp> | String | ID of the original order. | Required | 48.0 |
| <samp class="codeph apex_code">orderLifeCycleType</samp> | String | Specifies whether the order is managed in
                  Salesforce Order Management or by an external system. It can have one of these
                  values:<ul class="ul bulletList" id="orderlifecycletypevalues">
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

#### See Also

- [createOrderSummary(orderSummaryInput)](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_ConnectAPI_OrderSummaryCreation_static_methods.htm#apex_ConnectAPI_OrderSummaryCreation_createOrderSummary_1 "Create an OrderSummary based on an order. That order is considered the original order for the OrderSummary. Subsequent change orders that apply to the OrderSummary are also represented as orders. You can specify whether the order is managed in Salesforce Order Management or by an external system. Most Salesforce Order Management APIs can run only on orders that it manages.")