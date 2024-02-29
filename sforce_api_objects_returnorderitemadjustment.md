# ReturnOrderItemAdjustment

    Represents a price adjustment on a return order line item. This object is
    available in API version 50.0 and later. 

## Supported Calls

<samp class="codeph nolang">create()</samp>,  <samp class="codeph nolang">delete()</samp>,  <samp class="codeph nolang">describeLayout()</samp>,  <samp class="codeph nolang">describeSObjects()</samp>,  <samp class="codeph nolang">getDeleted()</samp>, <samp class="codeph nolang">getUpdated()</samp>,  <samp class="codeph nolang">query()</samp>,  <samp class="codeph nolang">retrieve()</samp>,  <samp class="codeph nolang">update()</samp>,  <samp class="codeph nolang">upsert()</samp>

## Special Access Rules

Order Management must be enabled.

## Fields

| Field | Details |
| --- | --- |
| Amount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Create, Filter, Sort<br>

                      - Description<br>

                        - Amount, not including tax, of the adjustment. |
| Description | - Type<br>

                        - textarea<br>

                    - Properties<br>

                        - Create, Nillable, Update<br>

                      - Description<br>

                        - Description of the adjustment. |
| OrderItemAdjustLineSummaryId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort<br>

                      - Description<br>

                          - ID of the order item adjustment line summary associated with the
                      adjustment. |
| ReturnOrderId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Create, Filter, Group, Sort<br>

                      - Description<br>

                        - ID of the return order associated with the return order line item to which
                      the adjustment applies. |
| ReturnOrderItemAdjustmentNumber | - Type<br>

                        - string<br>

                    - Properties<br>

                        - Autonumber, Defaulted on create, Filter, idLookup, Sort<br>

                      - Description<br>

                          - ID of the return order item adjustment. |
| ReturnOrderLineItemId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Create, Filter, Group, Sort<br>

                      - Description<br>

                        - ID of the return order line item to which this adjustment applies. |
| TotalAmtWithTax | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                      - Description<br>

                          - Total amount of the adjustment, inclusive of tax. This amount is equal to                         Amount + TotalTaxAmount. |
| TotalTaxAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                      - Description<br>

                          - Tax on the Amount. |