# Flow Core Action for Order Management: Cancel Fulfillment Order
      Item

Cancel fulfillment order products from a fulfillment order. You can
      cancel more than one product, and specify a quantity to cancel for each of them. This action
      doesn’t cancel the associated order product summaries; it only reduces their allocated
      quantities. Usually, you reallocate the canceled quantities to a new fulfillment
    order.

| Available in: Lightning Experience |
| --- |
| Available in: **Enterprise**, **Unlimited**, and **Developer**
                Editions with Salesforce Order Management |

Drag an Action element onto the canvas. Select the **Order Management**         category, and search for **Cancel Fulfillment Order Item**. 

## Set Input Values

Use values from earlier in the flow to set the inputs.

| Input Parameter | Description |
| --- | --- |
| Cancel Fulfillment Order Items Input | This input is an Apex-defined variable of class [ConnectApi.FulfillmentOrderLineItemsToCancelInputRepresentation](https://developer.salesforce.com/docs/atlas.en-us.230.0.apexcode.meta/apexcode/apex_connectapi_input_fulfillment_order_line_items_to_cancel.htm).<br>The                   variable has one field, fulfillmentOrderLineItemsToCancel,                   which is a list of Apex-defined variables of class [ConnectApi.FulfillmentOrderLineItemInputRepresentation](https://developer.salesforce.com/docs/atlas.en-us.230.0.apexcode.meta/apexcode/apex_connectapi_input_fulfillment_order_line_item.htm). Each of those                   variables includes these fields:<br>
<ul class="ul bulletList">
                  <li class="li">
<span class="keyword parmname">fulfillmentOrderLineItemId</span> — Reference to the
                    fulfillment order product to cancel.</li>

                  <li class="li">
<span class="keyword parmname">quantity</span> — Quantity to cancel.</li>

                </ul> |
| Fulfillment Order Id | Reference to the fulfillment order that you want to cancel fulfillment order
                items from. |

## Store Output Values

| Output Parameter | Description |
| --- | --- |
| Cancel Fulfillment Order Items Output | This value is an Apex-defined variable of class [ConnectApi.FulfillmentOrderCancelLineItemsOutputRepresentation](https://developer.salesforce.com/docs/atlas.en-us.230.0.apexcode.meta/apexcode/apex_connectapi_output_fulfillment_order_cancel_line_items_output.htm).<br>This                   action doesn’t return any data. |

## Usage

To set up the Cancel Fulfillment Order Items Input, first use Assignment elements to set         the fulfillmentOrderLineItemId and quantity field         values on one or more           ConnectApi.FulfillmentOrderLineItemInputRepresentation variables.         Then use an Assignment element to add those variables to the           FulfillmentOrderLineItemsToCancel field on a           ConnectApi.FulfillmentOrderLineItemsToCancelInputRepresentation         variable. Use that variable in the action input.