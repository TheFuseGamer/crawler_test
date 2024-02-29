# ConnectApi.SubmitReturnOutputRepresentation

ID of the change order created for a return action, and a set of its
      financial values.

Subclass of [ConnectApi.BaseOutputRepresentation](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_connectapi_output_base_output.htm "Base Order Management output class.").

| Property Name | Type | Description | Available Version |
| --- | --- | --- | --- |
| <samp class="codeph apex_code">changeBalances</samp> | <samp class="codeph apex_code"><a class="xref" href="atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/apex_connectapi_output_change_item_output.htm" title="The financial changes resulting from a change to one or more OrderItemSummaries. Most of the values represent the deltas of the values on the associated OrderSummary. The sign of each value is the opposite of the corresponding value on a change order record. For example, a discount is a positive value here and a negative value on a change order record.">ConnectApi.​ChangeItem​OutputRepresentation</a></samp> | Financial values resulting from the
                return. | 48.0 |
| <samp class="codeph apex_code">changeOrderId</samp> | String | ID of the created change order. | 48.0 |