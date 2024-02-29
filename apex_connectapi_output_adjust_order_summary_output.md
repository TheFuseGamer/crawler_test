# ConnectApi.AdjustOrderSummaryOutputRepresentation

Output representation of the financial changes for an adjust items
      action. For a preview action, these values are the expected output. For a submit action, these
      values are the actual output.

| Property Name | Type | Description | Available Version |
| --- | --- | --- | --- |
| <samp class="codeph apex_code">changeBalances</samp> | <samp class="codeph apex_code"><a class="xref" href="atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_connectapi_output_change_item_output.htm" title="The financial changes resulting from a change to one or more OrderItemSummaries. Most of the values represent the deltas of the values on the associated OrderSummary. The sign of each value is the opposite of the corresponding value on a change order record. For example, a discount is a positive value here and a negative value on a change order record.">ConnectApi.​ChangeItemOutputRepresentation</a></samp> | Expected (for preview) or actual (for submit) financial
                  values for the price adjustment action. Most of the values match the change order
                  values. If two change orders are returned, then these values combine them. The
                  sign of a value in this output is the opposite of the corresponding value on a
                  change order record. For example, a discount is a positive value in <samp class="codeph apex_code">changeBalances</samp> and a negative value on a change
                  order record. | 49.0 |
| <samp class="codeph apex_code">orderSummaryId</samp> | String | ID of the OrderSummary. | 49.0 |
| <samp class="codeph apex_code">postFulfillment​ChangeOrderId</samp> | String | ID of the change Order that holds the
                  financial changes applicable to order products that have been fulfilled. For an
                  adjustPreview call, this value is always null. | 49.0 |
| <samp class="codeph apex_code">preFulfillment​ChangeOrderId</samp> | String | ID of the change Order that holds the
                  financial changes applicable to order products that have not been fulfilled. For
                  an adjustPreview call, this value is always null. | 49.0 |