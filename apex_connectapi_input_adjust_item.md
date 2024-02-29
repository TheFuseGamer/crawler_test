# ConnectApi.AdjustItemInputRepresentation

A price adjustment to an OrderItemSummary. It only supports
      discounts, not increases.

| Property | Type | Description | Required or Optional | Available Version |
| --- | --- | --- | --- | --- |
| <samp class="codeph apex_code">adjustmentType</samp> | String | Describes how the amount is calculated. It can have one
                  of these values:<ul class="ul bulletList" id="adjustmenttypevalues">
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
| <samp class="codeph apex_code">amount</samp> | Double | Value used to calculate the adjustment amount, as described by
                  the adjustmentType. It must be a negative value. | Required | 49.0 |
| <samp class="codeph apex_code">description</samp> | String | Description of the adjustment. | Optional | 49.0 |
| <samp class="codeph apex_code">orderItem​SummaryId</samp> | String | ID of the OrderItemSummary. | Required | 49.0 |
| <samp class="codeph apex_code">reason</samp> | String | Reason for the adjustment. The value must match one of the
                  picklist values on the Reason field of the OrderItemSummaryChange
                object. | Required | 49.0 |

#### See Also

- [ConnectApi.AdjustOrderItemSummaryInputRepresentation](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_connectapi_input_adjust_order_item_summary.htm "A list of price adjustments to OrderItemSummaries that make up a price adjustment to an order.")
- [adjustPreview(orderSummaryId, adjustInput)](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_ConnectAPI_OrderSummary_static_methods.htm#apex_ConnectAPI_OrderSummary_adjustPreview_1 "Retrieve the expected results of adjusting the price of one or more OrderItemSummaries from an OrderSummary, without actually executing the adjustment. The response data contains the financial changes that would result from submitting the proposed adjustment.")
- [adjustSubmit(orderSummaryId, adjustInput)](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_ConnectAPI_OrderSummary_static_methods.htm#apex_ConnectAPI_OrderSummary_adjustSubmit_1 "Adjust the price of one or more OrderItemSummaries from an OrderSummary, and create one or two corresponding change orders.")