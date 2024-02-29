# Flow Core Action for Order Management: Create Order
    Summary

Create an order summary based on an order. That order is considered
      the original order for the order summary. Subsequent change orders that apply to the order
      summary are also represented as order records.

| Available in: Lightning Experience |
| --- |
| Available in: **Enterprise**, **Unlimited**, and **Developer**
                Editions with Salesforce Order Management |

Drag an Action element onto the canvas. Select the **Order Management**         category, and search for **Create Order Summary**. 

## Set Input Values

Use values from earlier in the flow to set the inputs.

| Input Parameter | Description |
| --- | --- |
| Order Summary Create Input | This input is an Apex-defined variable of class [ConnectApi.OrderSummaryInputRepresentation](https://developer.salesforce.com/docs/atlas.en-us.230.0.apexcode.meta/apexcode/apex_connectapi_input_order_summary.htm).<br>The variable has
                  four fields:<ul class="ul bulletList">
                    
                    <li class="li">
<samp class="codeph apex_code">name</samp>—Optional. Order summary
                      number to assign to the order summary.</li>

                    <li class="li">
<span class="keyword parmname">orderId</span> — The ID of the original order to create
                      an order summary for.</li>

                    <li class="li">
<span class="keyword parmname">orderLifeCycleType</span> —
                      Optional.
                      Specifies whether the order is managed in Salesforce Order
                      Management or by an external system. It can have one of these values:<a name="orderlifecycletypevalues"><!-- --></a><ul class="ul bulletList" id="orderlifecycletypevalues">
                        <li class="li">
<kbd class="ph userinput">MANAGED</kbd>—The order is managed in Salesforce
                          Order Management. If no value is specified, the default is
                            <kbd class="ph userinput">MANAGED</kbd>.</li>

                        <li class="li">
<kbd class="ph userinput">UNMANAGED</kbd>—The order is managed by an
                          external system.</li>

                      </ul>
</li>

                    <li class="li">
<samp class="codeph apex_code">status</samp>—Optional. Status to
                      assign to the order summary. The value must match one of the picklist values
                      on the Status field of the Order Summary object.</li>

                  </ul> |

## Store Output Values

| Output Parameter | Description |
| --- | --- |
| Order Summary Output | This value is an Apex-defined variable of class [OrderSummaryOutputRepresentation](https://developer.salesforce.com/docs/atlas.en-us.230.0.apexcode.meta/apexcode/apex_connectapi_output_order_summary_output.htm).<br>The                     orderSummaryId field contains the ID of the created order                   summary. |