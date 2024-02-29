# Flow Core Action for Order Management: Cancel Order Item Summaries
      Preview

Preview the expected results of canceling one or more order product
      summaries from an order summary without executing the cancel. The output of this action
      contains the values that would be set on the change order created by submitting the proposed
      cancel.

| Available in: Lightning Experience |
| --- |
| Available in: **Enterprise**, **Unlimited**, and **Developer**
                Editions with Salesforce Order Management |

Drag an Action element onto the canvas. Select the **Order Management**         category, and search for **Cancel Order Item Summaries Preview**. 

## Set Input Values

Use values from earlier in the flow to set the inputs.

| Input Parameter | Description |
| --- | --- |
| Cancel Order Product Summary Items Input | This input is an Apex-defined variable of class [ConnectApi.ChangeInputRepresentation](https://developer.salesforce.com/docs/atlas.en-us.230.0.apexcode.meta/apexcode/apex_connectapi_input_change.htm).<br>The
                  variable has one field, changeItems. This field is a list of
                  Apex-defined variables of class [ConnectApi.ChangeItemInputRepresentation](https://developer.salesforce.com/docs/atlas.en-us.230.0.apexcode.meta/apexcode/apex_connectapi_input_change_item.htm).
                  Each of the variables includes these fields:<ul class="ul bulletList">
                    <li class="li">
<span class="keyword parmname">orderItemSummaryId</span> — ID of an order product
                      summary to cancel. It can’t be a shipping charge product.</li>

                    <li class="li">
<span class="keyword parmname">quantity</span> — Quantity to cancel.</li>

                    <li class="li">
<span class="keyword parmname">reason</span> — Cancel reason. The value must match one
                      of the picklist values on the Reason field of the Order Product Summary Change
                      object.</li>

                    <li class="li">
<span class="keyword parmname">shippingReductionFlag</span> — Boolean flag that
                      specifies whether to prorate any related delivery charge based on the price
                      change.</li>

                  </ul> |
| Order Summary Id | Reference to the order summary that you want to preview canceling order product
                summaries from. |

## Store Output Values

| Output Parameter | Description |
| --- | --- |
| Cancel Order Product Summary Output | This output is an Apex-defined variable of class [ConnectApi.PreviewCancelOutputRepresentation](https://developer.salesforce.com/docs/atlas.en-us.230.0.apexcode.meta/apexcode/apex_connectapi_output_preview_cancel_output.htm), which contains the values that
                would populate a change order record for the proposed cancel.<br>
![Note](/docs/resources/img/en-us/230.0?doc_id=images%2Ficon_note.png&folder=order_management_developer_guide)<br>
Note
<br>The sign of a                   value in the changeBalances field is the opposite of the                   corresponding value on a change order record. For example, a discount is a                   positive value in changeBalances and a negative value on a                   change order record.<br>
<br>
<br>
<br>The orderSummaryId field is the                   ID of the order summary specified in the input.<br>
<br>The changeBalances field is an Apex-defined variable of class [ConnectApi.ChangeItemOutputRepresentation](https://developer.salesforce.com/docs/atlas.en-us.230.0.apexcode.meta/apexcode/apex_connectapi_output_change_item_output.htm),
                  which includes these fields:<ul class="ul bulletList">
                    <li class="li">
<span class="keyword parmname">grandTotalAmount</span> — Change to the total with
                      tax.</li>

                    <li class="li">
<span class="keyword parmname">totalAdjDeliveryAmtWithTax</span> — Change to the
                      adjusted delivery subtotal, including tax.</li>

                    <li class="li">
<span class="keyword parmname">totalAdjDistAmountWithTax</span> — Change to the total
                      order adjustments, including tax.</li>

                    <li class="li">
<span class="keyword parmname">totalAdjProductAmtWithTax</span> — Change to the
                      adjusted product subtotal, including tax.</li>

                    <li class="li">
<span class="keyword parmname">totalAdjustedDeliveryAmount</span> — Change to the
                      adjusted delivery subtotal.</li>

                    <li class="li">
<span class="keyword parmname">totalAdjustedDeliveryTaxAmount</span> — Change to the
                      adjusted delivery subtotal tax.</li>

                    <li class="li">
<span class="keyword parmname">totalAdjustedProductAmount</span> — Change to the
                      adjusted product subtotal.</li>

                    <li class="li">
<span class="keyword parmname">totalAdjustedProductTaxAmount</span> — Change to the
                      adjusted product subtotal tax.</li>

                    <li class="li">
<span class="keyword parmname">totalAdjustmentDistributedAmount</span> — Change to the
                      total order adjustments.</li>

                    <li class="li">
<span class="keyword parmname">totalAdjustmentDistributedTaxAmount</span> — Change to
                      the total order adjustments tax.</li>

                    <li class="li">
<span class="keyword parmname">totalAmount</span> — Change to the pretax total.</li>

                    <li class="li">
<span class="keyword parmname">totalExcessFundsAmount</span> — The amount of excess
                      funds available on the order payment summaries related to the order summary.
                      It is equal to the captured amount that is owed as a refund but is not
                      associated with an invoice or credit memo. Excess funds normally occur when
                      order products are canceled before fulfillment but after payment is captured.
                      This situation is not common in the US, where funds are normally authorized
                      but not captured until the fulfillment process begins. This value includes all
                      excess funds related to the order summary, not only the funds related to the
                      current action.</li>

                    <li class="li">
<span class="keyword parmname">totalRefundableAmount</span> — The total amount
                      available to be refunded. It is the sum of the excess funds and any
                      outstanding change order grand total amounts that apply to post-fulfillment
                      changes. This value includes all refundable amounts related to the order
                      summary, not only the amount related to the current action.</li>

                    <li class="li">
<span class="keyword parmname">totalTaxAmount</span> — Change to the total tax.</li>

                  </ul> |

## Usage

To set up the Cancel Order Product Summary Items Input:
1. Use Assignment elements to set the orderItemSummaryId,
              quantity, reason, and
              shippingReductionFlag field values on one or more
              ConnectApi.ChangeItemInputRepresentation variables.
2. Use an Assignment element to add the
              ConnectApi.ChangeItemInputRepresentation variables to the
              changeItems field on a
              ConnectApi.ChangeInputRepresentation variable.
3. Use the ConnectApi.ChangeInputRepresentation variable and the
            order summary ID in the action input.

In a flow for canceling order product summaries, display the output of this action for the         user to review before executing the cancel. When the user verifies the expected results,         pass the same input to a Cancel Order Item Summaries Submit action.