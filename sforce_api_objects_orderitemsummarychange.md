# OrderItemSummaryChange

    Represents a change to an OrderItemSummary, usually a reduction in quantity due
      to a cancel or return. Corresponds to a change order item. This object is available in
    API version 48.0 and later.

This object is used for calculations and doesn’t have a default record page.

## Supported Calls

       <samp class="codeph nolang">delete()</samp>,        <samp class="codeph nolang">describeLayout()</samp>,        <samp class="codeph nolang">describeSObjects()</samp>,        <samp class="codeph nolang">getDeleted()</samp>,        <samp class="codeph nolang">getUpdated()</samp>,        <samp class="codeph nolang">query()</samp>,        <samp class="codeph nolang">retrieve()</samp>           

## Special Access Rules

This object is only available in Salesforce Order Management orgs.

## Fields

| Field | Details |
| --- | --- |
| ChangeOrderItemId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Filter, Group, Sort<br>

                    - Description<br>

                        - ID of the associated change order item. |
| ChangeType | - Type<br>

                        - picklist<br>

                    - Properties<br>

                        - Filter, Group, Restricted picklist, Sort<br>

                    - Description<br>

                        - Type of change represented by the OrderItemSummaryChange.<br>

                        - Possible values are: <ul class="ul bulletList">
                        <li class="li"><samp class="codeph nolang">Cancel</samp></li>

                        <li class="li"><samp class="codeph nolang">DeliveryChargeAdjustment</samp></li>

                        <li class="li"><samp class="codeph nolang">ProductAdjustment</samp></li>

                        <li class="li"><samp class="codeph nolang">Return</samp></li>

                      </ul> |
| CurrencyIsoCode | - Type<br>

                        - picklist<br>

                    - Properties<br>

                        - Defaulted on create, Filter, Group, Restricted picklist, Sort<br>

                    - Description<br>

                        - ISO code for the currency of the OrderSummary associated with the
                      OrderItemSummaryChange. The default value is USD.<br>

                        - Possible values are: <ul class="ul bulletList">
                        <li class="li">
<samp class="codeph nolang">DKK</samp>—Danish Krone</li>

                        <li class="li">
<samp class="codeph nolang">EUR</samp>—Euro</li>

                        <li class="li">
<samp class="codeph nolang">GBP</samp>—British Pound</li>

                        <li class="li">
<samp class="codeph nolang">USD</samp>—U.S. Dollar</li>

                      </ul><br>

                        - This field is available in API version 49.0 and later. |
| IsPreFulfillment | - Type<br>

                        - boolean<br>

                    - Properties<br>

                        - Defaulted on create, Filter, Group, Sort<br>

                    - Description<br>

                        - Indicates whether the change occurs before the OrderItemSummary has been
                      fulfilled. |
| OrderItemSummary​ChangeNumber | - Type<br>

                        - string<br>

                    - Properties<br>

                        - Autonumber, Defaulted on create, Filter, idLookup, Sort<br>

                    - Description<br>

                        - ID of the OrderItemSummaryChange. |
| OrderItemSummaryId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Filter, Group, Sort<br>

                    - Description<br>

                        - ID of the OrderItemSummary to which the change applies. |
| OrderSummaryId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Filter, Group, Sort<br>

                    - Description<br>

                        - ID of the OrderSummary to which the associated OrderItemSummary
                      belongs. |
| Reason | - Type<br>

                        - picklist<br>

                    - Properties<br>

                        - Defaulted on create, Filter, Group, Sort<br>

                    - Description<br>

                        - Reason for the change. You can customize this list.<br>

                        - The list has one default value:<ul class="ul bulletList">
                        <li class="li"><samp class="codeph nolang">Unknown</samp></li>

                      </ul> |

#### See Also

- [OrderItemSummary](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_orderitemsummary.htm "Represents the current properties and state of a product or charge on an OrderSummary. Corresponds to one or more order item objects, consisting of an original object and any change objects applicable to it. This object is available in API version 48.0 and later.")