# Flow Core Action for Order Management: Adjust Order Item Summaries
      Submit

Adjust the price of one or more order product summaries on an order
      summary. You can only apply a discount, not an increase. This action creates one or two change
      order records.

| Available in: Lightning Experience |
| --- |
| Available in: **Enterprise**, **Unlimited**, and **Developer**
                Editions with Salesforce Order Management |

Drag an Action element onto the canvas. Select the **Order Management**         category, and search for **Adjust Order Item Summaries Submit**. 

## Set Input Values

Use values from earlier in the flow to set the inputs.

| Input Parameter | Description |
| --- | --- |
| Order Summary Id | ID of the order summary associated with the order product summaries that you
                want to adjust the prices of. |
| Adjust Order Product Summaries Input | This input is an Apex-defined variable of class [ConnectApi.AdjustOrderItemSummaryInputRepresentation](https://developer.salesforce.com/docs/atlas.en-us.230.0.apexcode.meta/apexcode/apex_connectapi_input_adjust_order_item_summary.htm).<br>The variable has
                  one field, changeItems. This field is a list of Apex-defined
                  variables of class [ConnectApi.AdjustItemInputRepresentation](https://developer.salesforce.com/docs/atlas.en-us.230.0.apexcode.meta/apexcode/apex_connectapi_input_adjust_item.htm).
                  Each of the variables includes these fields:<ul class="ul bulletList">
                    <li class="li">
<span class="keyword parmname">orderItemSummaryId</span> — ID of an order product
                      summary to adjust the price of.</li>

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
| Adjust Order Product Summary Output | This output is an Apex-defined variable of class [ConnectApi.AdjustOrderSummaryOutputRepresentation](https://developer.salesforce.com/docs/atlas.en-us.230.0.apexcode.meta/apexcode/apex_connectapi_output_preview_adjust_output.htm). Depending on the order
                product summaries included in the adjustment, one or two change orders are
                generated. If two change orders are generated, then the
                  changeBalances values combine the values from both of
                  them.<br>
![Note](/docs/resources/img/en-us/230.0?doc_id=images%2Ficon_note.png&folder=order_management_developer_guide)<br>
Note
<br>The sign of a value in the changeBalances field is                   the opposite of the corresponding value on a change order record. For example, a                   discount is a positive value in changeBalances and a negative                   value on a change order record.<br>
<br>
<br>
<br>The orderSummaryId                   field is the ID of the order summary specified in the input.<br>
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
<br>The postFulfillmentChangeOrderId is the ID of the                   change order representing the portion of the adjustment that was applied to order                   product summaries that have been fulfilled.<br>
<br>The                     preFulfillmentChangeOrderId is the ID of the change order                   representing the portion of the adjustment that was applied to order product                   summaries that have not been fulfilled. |

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

In a flow for adjusting the prices of order product summaries, run an Adjust Order Item         Summaries Preview action before running this action. Then display its output for the user to         review. When the user verifies the expected results, pass the same input to this action.

After submitting a price adjustment, process refunds as appropriate:

- If the discount only applied to order product summaries for which payment has not been
          captured, it does not require a refund. This situation normally applies to order products
          in the US that have not been fulfilled.
- If the discount applied to order product summaries that have not been fulfilled and for
          which payment has been captured, process a refund. In this case, pass the
            totalExcessFundsAmount from changeBalances to
          the Ensure Refunds Async action.
- If the discount applied to order product summaries that have been fulfilled, process a
          refund. Pass the postFulfillmentChangeOrderId to the Create Credit
          Memo action, then pass the credit memo to the Ensure Refunds Async action.
- If the discount applied to both fulfilled and unfulfilled order product summaries for
          which payment has been captured, process both refunds. Pass the
            postFulfillmentChangeOrderId to the Create Credit Memo action, then
          pass the credit memo and the totalExcessFundsAmount from
            changeBalances to the Ensure Refunds Async action.

![Important](/docs/resources/img/en-us/230.0?doc_id=images%2Ficon_note_important.png&folder=order_management_developer_guide)

#### Important

Excess funds are not reduced until the payment processor issues a         refund. If you don’t process refunds promptly, subsequent refunds can be inaccurate.         Consider the following example.

1. An order with a total amount of $100 is placed, and the amount is captured
            immediately.
2. A product is canceled from the order, resulting in $20 of excess funds.
3. Before the excess funds are sent to the payment provider in an ensure refunds action,
            another product is canceled. This cancellation adds another $20 of excess funds.
            However, because the original $20 hasn’t been refunded yet, the cancel action returns a
            total excess funds amount of $40.
4. The first excess funds amount ($20) is sent to the payment provider in an ensure
            refunds request.
5. The second excess funds amount ($40)  is sent to the payment provider in an ensure
            refunds request.
6. The payment provider receives requests for $60 of refunds, when the correct refund
            total is $40. Because the total refund amount is less than the total captured amount of
            $100, the payment provider issues $60 in refunds.