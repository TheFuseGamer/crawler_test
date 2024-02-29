# Flow Core Action for Order Management: Ensure Refunds
    Async

Ensure refunds for a credit memo or excess funds by sending a request to a payment
      provider. This action inserts a background operation into an asynchronous job queue and
      returns the ID of that operation so you can track its status. Payment gateway responses appear
      in the payment gateway log and do not affect the background operation status.

| Available in: Lightning Experience |
| --- |
| Available in: **Enterprise**, **Unlimited**, and **Developer**
                Editions with Salesforce Order Management |

Drag an Action element onto the canvas. Select the **Order Management**         category, and search for **Ensure Refunds Async**. 

## Set Input Values

Use values from earlier in the flow to set the inputs.

| Input Parameter | Description |
| --- | --- |
| Ensure Refunds Async Input | This input is an Apex-defined variable of class [ConnectApi.EnsureReundsAsyncInputRepresentation](https://developer.salesforce.com/docs/atlas.en-us.230.0.apexcode.meta/apexcode/apex_connectapi_input_ensure_refunds_async.htm).<br>The variable has two
                  fields. You must specify at least one of them.<ul class="ul bulletList">
                    <li class="li">
<span class="keyword parmname">creditMemoId</span> — The ID of the credit memo to
                      ensure refunds for.</li>

                    <li class="li">
<span class="keyword parmname">excessFundsAmount</span> — The amount of excess funds
                      to apply the refunds against.</li>

                  </ul> |
| Order Summary Id | Reference to the order summary associated with the credit memo. |

## Store Output Values

| Output Parameter | Description |
| --- | --- |
| Ensure Refunds Async Output | This value is an Apex-defined variable of class [EnsureRefundsAsyncOutputRepresentation](https://developer.salesforce.com/docs/atlas.en-us.230.0.apexcode.meta/apexcode/apex_connectapi_output_ensure_refunds_async_output.htm).<br>The                     backgroundOperationId field contains the ID of the                   background operation. |