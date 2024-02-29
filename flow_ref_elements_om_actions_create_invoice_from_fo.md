# Flow Core Action for Order Management: Create an Invoice from
      Fulfillment Order

Create an invoice for a fulfillment order that doesn’t have
      one.

| Available in: Lightning Experience |
| --- |
| Available in: **Enterprise**, **Unlimited**, and **Developer**
                Editions with Salesforce Order Management |

Drag an Action element onto the canvas. Select the **Order Management**         category, and search for **Create an Invoice from Fulfillment Order**. 

## Set Input Values

Use values from earlier in the flow to set the inputs.

| Input Parameter | Description |
| --- | --- |
| Fulfillment Order Id | Reference to the fulfillment order that needs an invoice. |

## Store Output Values

| Output Parameter | Description |
| --- | --- |
| Invoice creation output | This value is an Apex-defined variable of class [ConnectApi.FulfillmentOrderInvoiceOutputRepresentation](https://developer.salesforce.com/docs/atlas.en-us.230.0.apexcode.meta/apexcode/apex_connectapi_output_fulfillment_order_invoice_output.htm).<br>The                     invoiceId field contains the ID of the created                 invoice. |