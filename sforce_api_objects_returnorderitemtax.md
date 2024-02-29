# ReturnOrderItemTax

    Represents the tax on a return order line item or return order item
      adjustment. This object is available in API version 50.0 and later. 

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

                        - Amount of tax represented by the return order item tax. |
| Description | - Type<br>

                        - textarea<br>

                    - Properties<br>

                        - Create, Nillable, Update<br>

                      - Description<br>

                        - Description of the return order item tax. |
| OrderItemTaxLineItemSummaryId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort<br>

                      - Description<br>

                        - ID of the order item tax line item summary associated with the order item
                      summary that corresponds to the return order line item to which the tax
                      applies. |
| Rate | - Type<br>

                        - percent<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                      - Description<br>

                          - Tax rate used to calculate the Amount. |
| ReturnOrderId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Create, Filter, Group, Sort<br>

                      - Description<br>

                        - ID of the associated return order. |
| ReturnOrderItemAdjustmentId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort<br>

                      - Description<br>

                        - If this object represents a tax on an adjustment, this value is the ID of
                      the return order item adjustment to which the tax applies. If this value is
                      null, the adjustment applies to a return order line item. |
| ReturnOrderItemTaxNumber | - Type<br>

                        - string<br>

                    - Properties<br>

                        - Autonumber, Defaulted on create, Filter, idLookup, Sort<br>

                      - Description<br>

                          - ID of the return order item tax. |
| ReturnOrderLineItemId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Create, Filter, Group, Sort<br>

                      - Description<br>

                          - If this object represents a tax on a return order line item, this value is
                      the ID of that return order line item. If this object represents a tax on an
                      adjustment, this value is the ID of the return order line item to which the
                      adjustment applies. |
| TaxEffectiveDate | - Type<br>

                        - date<br>

                    - Properties<br>

                        - Filter, Group, Nillable, Sort<br>

                      - Description<br>

                          - Date on which the Amount was calculated. Important due to tax rate changes
                      over time. |
| Type | - Type<br>

                        - picklist<br>

                    - Properties<br>

                        - Create, Filter, Group, Restricted picklist, Sort, Update<br>

                      - Description<br>

                          - Shows whether the amount on the tax line is an estimate or the final
                      calculated amount. Doesn’t set a value by default. Users can define automation
                      to set and change the value as needed.<br>

                          - Possible values are: <ul class="ul bulletList">
                        <li class="li"><samp class="codeph nolang">Actual</samp></li>

                        <li class="li"><samp class="codeph nolang">Estimated</samp></li>

                      </ul> |