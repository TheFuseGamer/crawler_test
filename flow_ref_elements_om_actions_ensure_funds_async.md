# Flow Core Action for Order Management: Ensure Funds Async

Ensure funds for an invoice and apply them to it. If needed, capture
      authorized funds by sending a request to a payment provider. This action inserts a background
      operation into an asynchronous job queue and returns the ID of that operation so you can track
      its status. Payment gateway responses appear in the payment gateway log and do not affect the
      background operation status.

| Available in: Lightning Experience |
| --- |
| Available in: **Enterprise**, **Unlimited**, and **Developer**
                Editions with Salesforce Order Management |

Drag an Action element onto the canvas. Select the **Order Management**         category, and search for **Ensure Funds Async**. 

## Set Input Values

Use values from earlier in the flow to set the inputs.

| Input Parameter | Description |
| --- | --- |
| Ensure Funds Async Input | This input is an Apex-defined variable of class [ConnectApi.EnsureFundsAsyncInputRepresentation](https://developer.salesforce.com/docs/atlas.en-us.230.0.apexcode.meta/apexcode/apex_connectapi_input_ensure_funds_async.htm).<br>The variable has one                   field, invoiceId, which is the ID of the invoice to ensure                   funds for and apply them to. |
| Order Summary Id | Reference to the order summary associated with the invoice. |

## Store Output Values

| Output Parameter | Description |
| --- | --- |
| Ensure Funds Async Output | This value is an Apex-defined variable of class [EnsureFundsAsyncOutputRepresentation](https://developer.salesforce.com/docs/atlas.en-us.230.0.apexcode.meta/apexcode/apex_connectapi_output_ensure_funds_async_output.htm).<br>The                     backgroundOperationId field contains the ID of the                   background operation. |

## Usage

This action checks the order payment summaries associated with the specified order summary         for  funds to pay the invoice balance as follows:

![Note](/docs/resources/img/en-us/230.0?doc_id=images%2Ficon_note.png&folder=order_management_developer_guide)

#### Note

If multiple order payment summaries have the same amount, their order of selection is         random.

1. Verify that the invoice balance doesn’t exceed the total amount of all the order payment
          summaries.
2. If an order payment summary exists with an amount that matches the invoice balance, use
          it.
3. Otherwise, if any order payment summaries exist with an amount greater than the invoice
          balance, use the one with the smallest amount greater than the invoice balance.
4. Otherwise, select order payment summaries in order from largest amount to smallest until
          their amounts meet or exceed the invoice balance.
5. If any selected funds are authorized, capture them.
6. Apply the selected funds to the invoice.