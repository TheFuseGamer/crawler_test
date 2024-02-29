# Preview Return Output

Expected financial values for a proposed return
    action.

| Property Name | Type | Description | Filter Group and Version | Available Version |
| --- | --- | --- | --- | --- |
| <samp class="codeph nolang">changeBalances</samp> | [Change Item Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_change_item_output.htm "The financial changes resulting from a change to one or more OrderItemSummaries. Most of the values represent the deltas of the values on the associated OrderSummary. The sign of each value is the opposite of the corresponding value on a change order record. For example, a discount is a positive value here and a negative value on a change order record.") | Expected financial values for the proposed return
                  action. | Big, 48.0 | 48.0 |
| <samp class="codeph nolang">errors</samp> | [Error Response Output](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_responses_error_response.htm "Error response representation")[] | Any errors that were returned. | Big, 48.0 | 48.0 |
| <samp class="codeph nolang">orderSummaryId</samp> | String | ID of the OrderSummary. | Big, 48.0 | 48.0 |
| <samp class="codeph nolang">success</samp> | Boolean | Indicates whether the transaction was successful. | Big, 48.0 | 48.0 |