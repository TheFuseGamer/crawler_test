# Flow Core Action for Order Management: Create Credit Memo

Create a credit memo to represent the refund for one or more change
      orders associated with an order summary.

| Available in: Lightning Experience |
| --- |
| Available in: **Enterprise**, **Unlimited**, and **Developer**
                Editions with Salesforce Order Management |

Drag an Action element onto the canvas. Select the **Order Management**         category, and search for **Create Credit Memo**. 

## Set Input Values

Use values from earlier in the flow to set the inputs.

| Input Parameter | Description |
| --- | --- |
| Credit Memo Input | This input is an Apex-defined variable of class [ConnectApi.CreateCreditMemoInputRepresentation](https://developer.salesforce.com/docs/atlas.en-us.230.0.apexcode.meta/apexcode/apex_connectapi_input_create_credit_memo.htm).<br>The variable has one                   field, changeOrderIds, which is a list of IDs of the change                   orders to create a credit memo for. |
| Order Summary Id | Reference to the order summary associated with the change orders. |

## Store Output Values

| Output Parameter | Description |
| --- | --- |
| Credit Memo Output | This value is an Apex-defined variable of class [ConnectApi.CreateCreditMemoOutputRepresentation](https://developer.salesforce.com/docs/atlas.en-us.230.0.apexcode.meta/apexcode/apex_connectapi_output_create_credit_memo_output.htm).<br>The                     creditMemoId field contains the ID of the created credit                   memo. |

## Usage

To set up the Credit Memo Input, first use Assignment elements to add the change order IDs         to a list of strings variable. Then use that variable in the action input.