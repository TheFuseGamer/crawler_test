# Change Item Output

The financial changes resulting from a change to one or more
      OrderItemSummaries. Most of the values represent the deltas of the values on the associated
      OrderSummary. The sign of each value is the opposite of the corresponding value on a change
      order record. For example, a discount is a positive value here and a negative value on a
      change order record.

| Property Name | Type | Description | Filter Group and Version | Available Version |
| --- | --- | --- | --- | --- |
| <samp class="codeph nolang">grandTotalAmount</samp> | Double | Change to the GrandTotalAmount field. | Big, 48.0 | 48.0 |
| <samp class="codeph apex_code">totalAdjDelivery​AmtWithTax</samp> | Double | Change to the TotalAdjDeliveryAmtWithTax
                  field. | 49.0 |  |
| <samp class="codeph apex_code">totalAdjDist​AmountWithTax</samp> | Double | Change to the TotalAdjDistAmountWithTax
                  field. | 49.0 |  |
| <samp class="codeph apex_code">totalAdjProduct​AmtWithTax</samp> | Double | Change to the TotalAdjProductAmtWithTax
                  field. | 49.0 |  |
| <samp class="codeph nolang">totalAdjusted​DeliveryAmount</samp> | Double | Change to the TotalAdjustedDeliveryAmount
                  field. | Big, 48.0 | 48.0 |
| <samp class="codeph nolang">totalAdjusted​DeliveryTax​Amount</samp> | Double | Change to the
                  TotalAdjustedDeliveryTaxAmount field. | Big, 48.0 | 48.0 |
| <samp class="codeph nolang">totalAdjusted​ProductAmount</samp> | Double | Change to the TotalAdjustedProductAmount
                  field. | Big, 48.0 | 48.0 |
| <samp class="codeph nolang">totalAdjusted​ProductTax​Amount</samp> | Double | Change to the
                  TotalAdjustedProductTaxAmount field. | Big, 48.0 | 48.0 |
| <samp class="codeph nolang">totalAdjustment​Distributed​Amount</samp> | Double | Change to the
                  TotalAdjustmentDistributedAmount field. | Big, 48.0 | 48.0 |
| <samp class="codeph nolang">totalAdjustment​Distributed​TaxAmount</samp> | Double | Change to the
                  TotalAdjustmentDistributedTaxAmount field. | Big, 48.0 | 48.0 |
| <samp class="codeph nolang">totalAmount</samp> | Double | Change to the TotalAmount field. | Big, 48.0 | 48.0 |
| <samp class="codeph nolang">totalExcess​FundsAmount</samp> | Double | Amount of excess funds available on the
                  OrderPaymentSummaries related to the OrderSummary. It is equal to the captured
                  amount that is owed as a refund but is not associated with an invoice or credit
                  memo. Excess funds normally occur when order items are canceled before fulfillment
                  but after payment has been captured. This situation is not common in the US, where
                  funds are normally authorized but not captured until the fulfillment process
                  begins. This value includes all current excess funds related to the OrderSummary,
                  not only the funds related to the current change. | Big, 48.0 | 48.0 |
| <samp class="codeph nolang">totalRefundable​Amount</samp> | Double | Total amount available to be refunded. It is the
                  sum of the excess funds and any outstanding change order grand total amounts that
                  apply to post-fulfillment changes. This value includes all current refundable
                  amounts related to the OrderSummary, not only the amount related to the current
                  change. | Big, 48.0 | 48.0 |
| <samp class="codeph nolang">totalTaxAmount</samp> | Double | Change to the TotalTaxAmount field. | Big, 48.0 | 48.0 |

#### See Also

- [Preview Cancel Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_preview_cancel_output.htm "Expected financial values for a proposed cancel action.")
- [Preview Return Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_preview_return_output.htm "Expected financial values for a proposed return action.")
- [Submit Cancel Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_submit_cancel_output.htm "ID of the change order created for a cancel action, and a set of its financial values.")
- [Submit Return Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_submit_return_output.htm "ID of the change order created for a return action, and a set of its financial values.")
- [Adjust Order Summary Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_adjust_order_summary.htm "Output representation of the financial changes for an adjust items action. For a preview action, these values are the expected output. For a submit action, these values are the actual output.")