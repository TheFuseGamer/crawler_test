# Adjust Order Summary Output

Output representation of the financial changes for an adjust items
      action. For a preview action, these values are the expected output. For a submit action, these
      values are the actual output.

| Property Name | Type | Description | Filter Group and Version | Available Version |
| --- | --- | --- | --- | --- |
| <samp class="codeph nolang">changeBalances</samp> | [Change Item Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_change_item_output.htm "The financial changes resulting from a change to one or more OrderItemSummaries. Most of the values represent the deltas of the values on the associated OrderSummary. The sign of each value is the opposite of the corresponding value on a change order record. For example, a discount is a positive value here and a negative value on a change order record.") | Expected (for preview) or actual (for submit) financial
                  values for the price adjustment action. Most of the values match the change order
                  values. If two change orders are returned, then these values combine them. The
                  sign of a value in this output is the opposite of the corresponding value on a
                  change order record. For example, a discount is a positive value in <samp class="codeph apex_code">changeBalances</samp> and a negative value on a change
                  order record. | Big, 49.0 | 49.0 |
| <samp class="codeph nolang">orderSummaryId</samp> | String | ID of the OrderSummary. | Big, 49.0 | 49.0 |
| <samp class="codeph nolang">postFulfillment​ChangeOrderId</samp> | String | ID of the change Order that holds the
                  financial changes applicable to order products that have been fulfilled. For an
                  adjustPreview call, this value is always null. | Big, 49.0 | 49.0 |
| <samp class="codeph nolang">preFulfillment​ChangeOrderId</samp> | String | ID of the change Order that holds the
                  financial changes applicable to order products that have not been fulfilled. For
                  an adjustPreview call, this value is always null. | Big, 49.0 | 49.0 |

#### See Also

- [Order Summaries, Preview Adjust](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_order_summaries_preview_adjust.htm "Retrieve the expected results of adjusting the price of one or more OrderItemSummaries from an OrderSummary, without actually executing the adjustment. The response data contains the financial changes that would result from submitting the proposed adjustment.")
- [Order Summaries, Submit Adjust](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_order_summaries_submit_adjust.htm "Adjust the price of one or more OrderItemSummaries from an OrderSummary, and create one or two corresponding change orders.")