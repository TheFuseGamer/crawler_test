# Flow Core Action for Order Management: Adjust Order Item Summaries
      Preview

Preview the expected results of adjusting the price of one or more
      order product summaries on an order summary, without executing the adjustment. You can only
      apply a discount, not an increase. The output of this action contains the values that would be
      set on the change orders created by submitting the proposed adjustment.

| Available in: Lightning Experience |
| --- |
| Available in: **Enterprise**, **Unlimited**, and **Developer**
                Editions with Salesforce Order Management |

Drag an Action element onto the canvas. Select the **Order Management**         category, and search for **Adjust Order Item Summaries Preview**. 

## Set Input Values

Use values from earlier in the flow to set the inputs.

| Input Parameter | Description |
| --- | --- |
| Order Summary Id | ID of the order summary associated with the order product summaries that you
                want to preview adjusting the prices of. |
| Adjust Order Product Summaries Input | This input is an Apex-defined variable of class [ConnectApi.AdjustOrderItemSummaryInputRepresentation](https://developer.salesforce.com/docs/atlas.en-us.230.0.apexcode.meta/apexcode/apex_connectapi_input_adjust_order_item_summary.htm).<br>The variable has
                  one field, changeItems. This field is a list of Apex-defined
                  variables of class [ConnectApi.AdjustItemInputRepresentation](https://developer.salesforce.com/docs/atlas.en-us.230.0.apexcode.meta/apexcode/apex_connectapi_input_adjust_item.htm).
                  Each of the variables includes these fields:<ul class="ul bulletList">
                    <li class="li">
<span class="keyword parmname">orderItemSummaryId</span> — ID of an order product
                      summary to preview a price adjustment for.</li>

                    <li class="li">
<span class="keyword parmname">description</span> — Optional description of the
                      adjustment.</li>

                    <li class="li">
<span class="keyword parmname">adjustmentType</span> — Describes how the adjustment
                      amount is calculated. It can have one of these values:<a name="adjustmenttypevalues"><!-- --></a><ul class="ul bulletList" id="adjustmenttypevalues">
                        <li class="li">
<kbd class="ph userinput">AmountWithTax</kbd>—The value of
                            <span class="keyword parmname">discountValue</span> is the adjustment, including
                          tax.</li>

                        <li class="li">
<kbd class="ph userinput">AmountWithoutTax</kbd>—The value of
                            <span class="keyword parmname">discountValue</span> is the adjustment, not including tax.
                          Tax is calculated on the value and added.</li>

                        <li class="li">
<kbd class="ph userinput">Percentage</kbd>—The value of
                            <span class="keyword parmname">discountValue</span> is a percentage discount. It is
                          divided by 100, and then multiplied by the total price and total tax
                          amount of the order product summary to determine the adjustment
                          amount.</li>

                      </ul>
</li>

                    <li class="li">
<span class="keyword parmname">discountValue</span> — The value used to calculate the
                      adjustment amount, as described by the adjustmentType. It must be a negative
                      value.</li>

                    <li class="li">
<span class="keyword parmname">reason</span> — Adjustment reason. The value must match
                      one of the picklist values on the Reason field of the Order Product Summary
                      Change object.</li>

                  </ul> |

## Store Output Values

| Output Parameter | Description |
| --- | --- |
| Adjust Order Product Summary Output | This output is an Apex-defined variable of class [ConnectApi.AdjustOrderSummaryOutputRepresentation](https://developer.salesforce.com/docs/atlas.en-us.230.0.apexcode.meta/apexcode/apex_connectapi_output_preview_adjust_output.htm), which contains the
                financial changes that would result from the proposed adjustment. Most of the values
                represent the deltas of the values on the associated order summary.<br>
![Note](/docs/resources/img/en-us/230.0?doc_id=images%2Ficon_note.png&folder=order_management_developer_guide)<br>
Note
<br>The sign of                   a value in the changeBalances field is the opposite of the                   corresponding value on a change order record. For example, a discount is a                   positive value in changeBalances and a negative value on a                   change order record.<br>
<br>
<br>
<br>The orderSummaryId field is the                   ID of the order summary specified in the input.<br>
<br>The
                    changeBalances field is an Apex-defined variable of class
                    [ConnectApi.ChangeItemOutputRepresentation](https://developer.salesforce.com/docs/atlas.en-us.230.0.apexcode.meta/apexcode/apex_connectapi_output_change_item_output.htm),
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
                      order products are canceled before fulfillment but after payment has been
                      captured. This situation is not common in the US, where funds are normally
                      authorized but not captured until the fulfillment process begins. This value
                      includes all excess funds related to the order summary, not only the funds
                      related to the current action.</li>

                    <li class="li">
<span class="keyword parmname">totalRefundableAmount</span> — The total amount
                      available to be refunded. It is the sum of the excess funds and any
                      outstanding change order grand total amounts that apply to post-fulfillment
                      changes. This value includes all refundable amounts related to the order
                      summary, not only the amount related to the current action.</li>

                    <li class="li">
<span class="keyword parmname">totalTaxAmount</span> — Change to the total tax.</li>

                  </ul>
<br>
<br>The postFulfillmentChangeOrderId field is always                   null for a preview action.<br>
<br>The                     preFulfillmentChangeOrderId field is always null for a                   preview action. |

## Usage

To set up the Adjust Order Product Summaries Input:
1. Use Assignment elements to set the orderItemSummaryId,
              description, adjustmentType,
              discountValue, and reason field values on
            one or more ConnectApi.AdjustItemInputRepresentation
            variables.
2. Use an Assignment element to add the
              ConnectApi.AdjustItemInputRepresentation variables to the
              changeItems field on a
              ConnectApi.AdjustOrderItemSummaryInputRepresentation
            variable.
3. Use the ConnectApi.AdjustOrderItemSummaryInputRepresentation
            variable and the order summary ID in the action input.

In a flow for adjusting the prices of order product summaries, display the output of this         action for the user to review before executing the adjustment. When the user verifies the         expected results, pass the same input to an Adjust Order Item Summaries Submit action.