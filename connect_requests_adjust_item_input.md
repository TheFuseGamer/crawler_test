# Adjust Item Input

A price adjustment to an OrderItemSummary. It only supports
      discounts, not increases.

          - Root XML tag

              - <samp class="codeph nolang">&lt;adjustItem&gt;</samp>

          - JSON example

              - ```
{
  "reason": "Unknown",
  "amount": 45,
  "appeasementType": "AmountWithoutTax",
  "orderItemSummaryId": "10uxx0000004EXLAA2",
  "description": "foobar"
}
```

          - Properties

              - | Name | Type | Description | Required or Optional | Available Version |
| --- | --- | --- | --- | --- |
| <samp class="codeph nolang">adjustmentType</samp> | String | Describes how the amount is calculated. It can have one
                  of these values:<ul class="ul bulletList">
                    <li class="li">
<samp class="codeph apex_code">AmountWithTax</samp>—Value of amount is the adjustment,
                    including tax.</li>

                    <li class="li">
<samp class="codeph apex_code">AmountWithoutTax</samp>—Value of amount is the
                    adjustment, not including tax. Tax is calculated on the value and added.</li>

                    <li class="li">
<samp class="codeph apex_code">Percentage</samp>—Value of amount is a percentage
                    discount. It is divided by 100, and then multiplied by the TotalPrice and
                    TotalTaxAmount of the OrderItemSummary to determine the adjustment amount.</li>

                </ul> | Required | 49.0 |
| <samp class="codeph nolang">amount</samp> | Double | Value used to calculate the adjustment amount, as described by
                  the adjustmentType. It must be a negative value. | Required | 49.0 |
| <samp class="codeph nolang">description</samp> | String | Description of the adjustment. | Optional | 49.0 |
| <samp class="codeph nolang">orderItemSummaryId</samp> | String | ID of the OrderItemSummary. | Required | 49.0 |
| <samp class="codeph nolang">reason</samp> | String | Reason for the adjustment. The value must match one of the
                  picklist values on the Reason field of the OrderItemSummaryChange
                object. | Required | 49.0 |

#### See Also

- [Order Summaries, Preview Adjust](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_order_summaries_preview_adjust.htm "Retrieve the expected results of adjusting the price of one or more OrderItemSummaries from an OrderSummary, without actually executing the adjustment. The response data contains the financial changes that would result from submitting the proposed adjustment.")
- [Order Summaries, Submit Adjust](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_order_summaries_submit_adjust.htm "Adjust the price of one or more OrderItemSummaries from an OrderSummary, and create one or two corresponding change orders.")