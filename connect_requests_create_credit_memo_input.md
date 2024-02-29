# Create Credit Memo Input

A list of change orders used to create a credit
    memo.

          - Root XML tag

              - <samp class="codeph nolang">&lt;createCreditMemoInput&gt;</samp>

          - JSON example

              - ```
{
  "changeOrderIds": [
    "801R0000000EAAkIAO"
  ]
}
```

          - Properties

              - | Name | Type | Description | Required or Optional | Available Version |
| --- | --- | --- | --- | --- |
| <samp class="codeph nolang">changeOrderIds</samp> | String[] | List of IDs of the change orders. | Required | 48.0 |

#### See Also

- [Order Summaries, Create Credit Memo](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/connect_resources_sfom_order_summaries_create_credit_memo.htm "Create a credit memo to represent the refund for one or more change orders associated with an OrderSummary.")