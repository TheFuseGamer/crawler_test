# Flow Core Action for Order Management: Create Fulfillment
    Order

Create one or more fulfillment orders and fulfillment order products
      for an order delivery group summary, which defines a recipient and delivery method. You
      specify the order product summaries to fulfill and the fulfillment locations to handle them.
      If you specify multiple fulfillment locations, a fulfillment order is created for each
      one.

| Available in: Lightning Experience |
| --- |
| Available in: **Enterprise**, **Unlimited**, and **Developer**
                Editions with Salesforce Order Management |

Drag an Action element onto the canvas. Select the **Order Management**         category, and search for **Create Fulfillment Order**. 

## Set Input Values

Use values from earlier in the flow to set the inputs.

| Input Parameter | Description |
| --- | --- |
| Fulfillment Order Input | This input is an Apex-defined variable of class [ConnectApi.FulfillmentOrderInputRepresentation](https://developer.salesforce.com/docs/atlas.en-us.230.0.apexcode.meta/apexcode/apex_connectapi_input_fulfillment_order.htm).<br>The variable has three fields:<ul class="ul bulletList">
                    <li class="li">
<span class="keyword parmname">fulfillmentGroups</span> — A list of Apex-defined
                      variables of class <a class="xref" href="https://developer.salesforce.com/docs/atlas.en-us.230.0.apexcode.meta/apexcode/apex_connectapi_input_fulfillment_order.htm" target="_blank">ConnectApi.FulfillmentGroupInputRepresentation</a>. A fulfillment order
                      is created for each fulfillment group. A group represents a set of order
                      product summaries to fulfill from a single location, using the same
                      fulfillment type. Each fulfillment group variable has these fields:<ul class="ul bulletList">
                        <li class="li">
<span class="keyword parmname">fulfilledFromLocationId</span> — Reference to the
                          fulfillment location.</li>

                        <li class="li">
<span class="keyword parmname">fulfillmentType</span> — The fulfillment type.
                          Specify one of the values you’ve defined for the <span class="keyword parmname">Type</span>
                          field picklist on the Fulfillment Order object.</li>

                        <li class="li">
<span class="keyword parmname">orderItemSummaries</span> — A list of Apex-defined
                          variables of class <a class="xref" href="https://developer.salesforce.com/docs/atlas.en-us.230.0.apexcode.meta/apexcode/apex_connectapi_input_order_item_summary.htm" target="_blank">ConnectApi.OrderItemSummaryInputRepresentation</a>. Each variable
                          has these fields:<ul class="ul bulletList">
                            <li class="li">
<span class="keyword parmname">orderItemSummaryId</span> — Reference to an
                              order product summary.</li>

                            <li class="li">
<span class="keyword parmname">quantity</span> — The quantity of the order
                              product summary to allocate to the fulfillment order.</li>

                          </ul>
</li>

                      </ul>
</li>

                    <li class="li">
<span class="keyword parmname">orderDeliveryGroupSummaryId</span> — Reference to the
                      order delivery group summary associated with the order product summaries.</li>

                    <li class="li">
<span class="keyword parmname">orderSummaryId</span> — Reference to the order summary
                      associated with the order product summaries.</li>

                  </ul> |

## Store Output Values

| Output Parameter | Description |
| --- | --- |
| Fulfillment Order Output | This value is an Apex-defined variable of class [ConnectApi.FulfillmentOrderOutputRepresentation](https://developer.salesforce.com/docs/atlas.en-us.230.0.apexcode.meta/apexcode/apex_connectapi_output_fulfillment_order_output.htm).<br>The                     fulfillmentOrderIds field is a list of IDs of the created                   fulfillment orders. |

## Usage

To set up the Fulfillment Order Input:

1. Use Assignment elements to set the orderItemSummaryId and
            quantity field values on one or more
            ConnectApi.OrderItemSummaryInputRepresentation variables for each
          fulfillment group.
2. Use Assignment elements to add the
            ConnectApi.OrderItemSummaryInputRepresentation variables to the
            orderItemSummaries fields on one or more
            ConnectApi.FulfillmentGroupInputRepresentation variables, one for
          each fulfillment group.
3. Use Assignment elements to set the fulfilledFromLocationId and
            fulfillmentType field values on the fulfillment group
          variables.
4. Use Assignment elements to add the fulfillment group variables to the
            fulfillmentGroups field on a
            ConnectApi.FulfillmentOrderInputRepresentation variable.
5. Use Assignment elements to set the orderDeliveryGroupSummaryId and
            orderSummaryId field values on the
            ConnectApi.FulfillmentOrderInputRepresentation variable.
6. Use the ConnectApi.FulfillmentOrderInputRepresentation variable in
          the action input.