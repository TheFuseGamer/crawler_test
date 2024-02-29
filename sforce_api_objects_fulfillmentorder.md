# FulfillmentOrder

    Represents a group of products and delivery charges on a single order that
      share the same fulfillment location, delivery method, and recipient. The
      FulfillmentOrderLineItems belonging to a FulfillmentOrder are associated with OrderItemSummary
      objects belonging to a single OrderSummary. This object is available in API version 48.0
    and later.

## Supported Calls

         <samp class="codeph nolang">create()</samp>, <samp class="codeph nolang">delete()</samp>, <samp class="codeph nolang">describeLayout()</samp>, <samp class="codeph nolang">describeSObjects()</samp>, <samp class="codeph nolang">getDeleted()</samp>, <samp class="codeph nolang">getUpdated()</samp>, <samp class="codeph nolang">query()</samp>,           <samp class="codeph nolang">retrieve()</samp>, <samp class="codeph nolang">search()</samp>,           <samp class="codeph nolang">undelete()</samp>, <samp class="codeph nolang">update()</samp>,           <samp class="codeph nolang">upsert()</samp>       

## Special Access Rules

This object is only available in Salesforce Order Management orgs.

## Fields

| Field | Details |
| --- | --- |
| AccountId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort<br>

                    - Description<br>

                        - ID of the Account or Person Account associated with the FulfillmentOrder. It
                      represents the shopper in the storefront. |
| BillToContactId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort<br>

                    - Description<br>

                        - ID of the Contact associated with the FulfillmentOrder. It represents the
                      shopper in the storefront when not using person accounts.<br>

                        - This field is available in API version 49.0 and later. |
| CurrencyIsoCode | - Type<br>

                        - picklist<br>

                    - Properties<br>

                        - Create, Defaulted on create, Filter, Group, Nillable, Restricted picklist,
                      Sort, Update<br>

                    - Description<br>

                        - ISO code for the currency of the OrderSummary associated with the
                      FulfillmentOrder. The default value is USD.<br>

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
| DeliveryMethodId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Create, Filter, Group, Sort, Update<br>

                    - Description<br>

                        - ID of the DeliveryMethod used for this FulfillmentOrder. |
| FulfilledFromLocationId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort, Update<br>

                    - Description<br>

                        - ID of the Location handling this FulfillmentOrder. |
| FulfilledToAddress | - Type<br>

                        - address<br>

                    - Properties<br>

                        - Filter, Nillable<br>

                    - Description<br>

                        - Address of the recipient. |
| FulfilledToCity | - Type<br>

                        - string<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort, Update<br>

                    - Description<br>

                        - Recipient address city. |
| FulfilledToCountry | - Type<br>

                        - string<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort, Update<br>

                    - Description<br>

                        - Recipient address country. |
| FulfilledToEmailAddress | - Type<br>

                        - email<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort, Update<br>

                    - Description<br>

                        - Email address of the recipient. |
| FulfilledTo​GeocodeAccuracy | - Type<br>

                        - picklist<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Restricted picklist, Sort, Update<br>

                    - Description<br>

                        - Accuracy of the geocode for the recipient address.<br>

                        - Possible values are: <ul class="ul bulletList">
                        <li class="li"><samp class="codeph nolang">Address</samp></li>

                        <li class="li"><samp class="codeph nolang">Block</samp></li>

                        <li class="li"><samp class="codeph nolang">City</samp></li>

                        <li class="li"><samp class="codeph nolang">County</samp></li>

                        <li class="li"><samp class="codeph nolang">ExtendedZip</samp></li>

                        <li class="li"><samp class="codeph nolang">NearAddress</samp></li>

                        <li class="li"><samp class="codeph nolang">Neighborhood</samp></li>

                        <li class="li"><samp class="codeph nolang">State</samp></li>

                        <li class="li"><samp class="codeph nolang">Street</samp></li>

                        <li class="li"><samp class="codeph nolang">Unknown</samp></li>

                        <li class="li"><samp class="codeph nolang">Zip</samp></li>

                      </ul> |
| FulfilledToLatitude | - Type<br>

                        - double<br>

                    - Properties<br>

                        - Create, Filter, Nillable, Sort, Update<br>

                    - Description<br>

                        - Used with FulfilledToLongitude to specify the precise geolocation of the
                      recipient address. Acceptable values are numbers between –90 and 90 with up to
                      15 decimal places. |
| FulfilledToLongitude | - Type<br>

                        - double<br>

                    - Properties<br>

                        - Create, Filter, Nillable, Sort, Update<br>

                    - Description<br>

                        - Used with FulfilledToLatitude to specify the precise geolocation of the
                      recipient address. Acceptable values are numbers between –90 and 90 with up to
                      15 decimal places. |
| FulfilledToName | - Type<br>

                        - string<br>

                    - Properties<br>

                        - Create, Filter, Group, Sort, Update<br>

                    - Description<br>

                        - Name on the recipient address. |
| FulfilledToPhone | - Type<br>

                        - phone<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort, Update<br>

                    - Description<br>

                        - Phone number of the recipient. |
| FulfilledToPostalCode | - Type<br>

                        - string<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort, Update<br>

                    - Description<br>

                        - Recipient address postal code. |
| FulfilledToState | - Type<br>

                        - string<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort, Update<br>

                    - Description<br>

                        - Recipient address state. |
| FulfilledToStreet | - Type<br>

                        - textarea<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort, Update<br>

                    - Description<br>

                        - Recipient address street. |
| FulfillmentOrderNumber | - Type<br>

                        - string<br>

                    - Properties<br>

                        - Autonumber, Defaulted on create, Filter, idLookup, Sort<br>

                    - Description<br>

                        - ID of the FulfillmentOrder. |
| GrandTotalAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total, including adjustments and tax, of the products and delivery charges
                      on the FulfillmentOrder. This amount includes all FulfillmentOrderLineItems
                      associated with the FulfillmentOrder. This amount is equal to TotalAmount +
                      TotalTaxAmount. |
| InvoiceId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort, Update<br>

                    - Description<br>

                        - ID of the Invoice associated with the FulfillmentOrder. |
| IsSuspended | - Type<br>

                        - boolean<br>

                    - Properties<br>

                        - Create, Defaulted on create, Filter, Group, Sort, Update<br>

                    - Description<br>

                        - Indicates whether the FulfillmentOrder is suspended. The default value is
                      false. |
| ItemCount | - Type<br>

                        - double<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Sum of the quantities of the FulfillmentOrderLineItems included in the
                      FulfillmentOrder. |
| LastReferencedDate | - Type<br>

                        - dateTime<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Timestamp for when the current user last viewed a record related to this
                      record. |
| LastViewedDate | - Type<br>

                        - dateTime<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Timestamp for when the current user last viewed this record. A null value
                      can mean that this record has only been referenced (LastReferencedDate) and
                      not viewed. |
| OrderId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort<br>

                    - Description<br>

                        - ID of the original Order that generated the FulfillmentOrder. |
| OrderSummaryId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort<br>

                    - Description<br>

                        - ID of the OrderSummary associated with the FulfillmentOrder. |
| OwnerId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Create, Defaulted on create, Filter, Group, Sort, Update<br>

                    - Description<br>

                        - ID of the User who currently owns this FulfillmentOrder. Default value is
                      the User logged in to the API to perform the create. |
| Status | - Type<br>

                        - picklist<br>

                    - Properties<br>

                        - Create, Filter, Group, Sort, Update<br>

                    - Description<br>

                        - Status of the FulfillmentOrder. Each status corresponds to one status
                      category, shown here in parentheses. You can customize the status picklist to
                      represent your business processes, but the status category picklist is fixed
                      because processing is based on those values. If you customize the status
                      picklist, include at least one status value for each status category.<br>

                        - Default values are: <ul class="ul bulletList">
                        <li class="li">
<samp class="codeph nolang">Allocated</samp> (Activated)</li>

                        <li class="li">
<samp class="codeph nolang">Assigned</samp> (Fulfilling)</li>

                        <li class="li">
<samp class="codeph nolang">Cancelled</samp> (Cancelled)</li>

                        <li class="li">
<samp class="codeph nolang">Draft</samp> (Draft)</li>

                        <li class="li">
<samp class="codeph nolang">Fulfilled</samp> (Closed)</li>

                        <li class="li">
<samp class="codeph nolang">Pickpack</samp> (Fulfilling)</li>

                      </ul> |
| StatusCategory | - Type<br>

                        - picklist<br>

                    - Properties<br>

                        - Filter, Group, Restricted picklist, Sort<br>

                    - Description<br>

                        - Status category of the FulfillmentOrder. Processing of the FulfillmentOrder
                      depends on this value. Each status category corresponds to one or more
                      statuses.<br>

                        - Possible values are: <ul class="ul bulletList">
                        <li class="li">
<samp class="codeph nolang">ACTIVATED</samp>—Activated</li>

                        <li class="li">
<samp class="codeph nolang">CANCELLED</samp>—Cancelled</li>

                        <li class="li">
<samp class="codeph nolang">CLOSED</samp>—Closed</li>

                        <li class="li">
<samp class="codeph nolang">DRAFT</samp>—Draft</li>

                        <li class="li">
<samp class="codeph nolang">FULFILLING</samp>—Fulfilling</li>

                      </ul> |
| TaxLocaleType | - Type<br>

                        - picklist<br>

                    - Properties<br>

                        - Filter, Group, Nillable, Restricted picklist, Sort<br>

                    - Description<br>

                        - The system used to handle tax on the original Order associated with the
                      FulfillmentOrder. Gross usually applies to taxes like value-added tax (VAT),
                      and Net usually applies to taxes like sales tax.<br>

                        - Possible values are: <ul class="ul bulletList">
                        <li class="li">
<samp class="codeph nolang">Gross</samp> (displays most prices and
                          taxes as combined values)</li>

                        <li class="li">
<samp class="codeph nolang">Net</samp> (displays most prices and taxes
                          as separate values)</li>

                      </ul><br>

                        - This field is available in API version 49.0 and later. |
| TotalAdjustmentAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total amount of the price adjustments applied to the products on the
                      FulfillmentOrder. This value only includes adjustments to
                      FulfillmentOrderLineItems of type code Product. |
| TotalAdjustment​AmtWithTax | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total amount of the price adjustments applied to the products on the
                      FulfillmentOrder, inclusive of tax. This value only includes adjustments to
                      FulfillmentOrderLineItems of type code Product. This amount is equal to
                      TotalAdjustmentAmount + TotalAdjustmentTaxAmount.<br>

                        - This field is available in API version 49.0 and later. |
| TotalAdjustmentTaxAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Tax on the TotalAdjustmentAmount. |
| TotalAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Adjusted total, not including tax, of the FulfillmentOrderLineItems,
                      including products and delivery charges, on the FulfillmentOrder. |
| TotalDelivery​AdjustAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total amount of the price adjustments applied to the delivery charges on the
                      FulfillmentOrder. This value only includes adjustments to
                      FulfillmentOrderLineItems of type code Charge. |
| TotalDeliveryAdjust​AmtWithTax | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total amount of the price adjustments applied to the delivery charges on the
                      FulfillmentOrder, inclusive of tax. This value only includes adjustments to
                      FulfillmentOrderLineItems of type code Charge. This amount is equal to
                      TotalDeliveryAdjustAmount + TotalDeliveryAdjustTaxAmount.<br>

                        - This field is available in API version 49.0 and later. |
| TotalDelivery​AdjustTaxAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Tax on the TotalDeliveryAdjustAmount. |
| TotalDeliveryAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total of the delivery charges on the FulfillmentOrder. This value only
                      includes FulfillmentOrderLineItems of type code Charge. |
| TotalDelivery​AmtWithTax | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total amount of the delivery charges on the FulfillmentOrder, inclusive of
                      tax. This value only includes FulfillmentOrderLineItems of type code Charge.
                      This amount is equal to TotalDeliveryAmount + TotalDeliveryTaxAmount.<br>

                        - This field is available in API version 49.0 and later. |
| TotalDeliveryTaxAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Tax on the TotalDeliveryAmount. |
| TotalProductAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total price of the products on the FulfillmentOrder. This value only
                      includes FulfillmentOrderLineItems of type code Product. |
| TotalProduct​AmtWithTax | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Total price of the products on the FulfillmentOrder, inclusive of tax. This
                      value only includes FulfillmentOrderLineItems of type code Product. This
                      amount is equal to TotalProductAmount + TotalProductTaxAmount.<br>

                        - This field is available in API version 49.0 and later. |
| TotalProductTaxAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Tax on the TotalProductAmount. |
| TotalTaxAmount | - Type<br>

                        - currency<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                    - Description<br>

                        - Tax on the TotalAmount. |
| Type | - Type<br>

                        - picklist<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort, Update<br>

                    - Description<br>

                        - Type of the FulfillmentOrder. Each type corresponds to one type category,
                      shown here in parentheses. You can customize the type picklist to represent
                      your business processes, but the type category picklist is fixed because
                      processing is based on those values. If you customize the type picklist,
                      include at least one type value for each type category.<br>

                        - Default values are: <ul class="ul bulletList">
                        <li class="li">
<samp class="codeph nolang">Download</samp> (Digital)</li>

                        <li class="li">
<samp class="codeph nolang">Email</samp> (Digital)</li>

                        <li class="li">
<samp class="codeph nolang">In Store Pickup</samp> (Physical)</li>

                        <li class="li">
<samp class="codeph nolang">Retail Store</samp> (Physical)</li>

                        <li class="li">
<samp class="codeph nolang">Supplier</samp> (Drop Ship)</li>

                        <li class="li">
<samp class="codeph nolang">Warehouse</samp> (Physical)</li>

                      </ul> |
| TypeCategory | - Type<br>

                        - picklist<br>

                    - Properties<br>

                        - Filter, Group, Nillable, Restricted picklist, Sort<br>

                    - Description<br>

                        - Type category of the FulfillmentOrder. Processing of the FulfillmentOrder
                      depends on this value. Each type category corresponds to one or more
                      types.<br>

                        - Possible values are: <ul class="ul bulletList">
                        <li class="li">
<samp class="codeph nolang">DIGITAL</samp>—Digital</li>

                        <li class="li">
<samp class="codeph nolang">DROPSHIP</samp>—Drop Ship</li>

                        <li class="li">
<samp class="codeph nolang">PHYSICAL</samp>—Physical</li>

                      </ul> |

## Associated Objects

This object has the following associated objects. Unless noted, they are available in the         same API version as this object.

          - FulfillmentOrderFeed

              - Feed tracking is available for the object.

          - FulfillmentOrderOwnerSharingRule

              - Sharing rules are available for the object.

          - FulfillmentOrderShare

              - Sharing is available for the object.

#### See Also

- [FulfillmentOrderLineItem](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_fulfillmentorderlineitem.htm "Represents a product or delivery charge belonging to a FulfillmentOrder. Corresponds to an OrderItemSummary. This object is available in API version 48.0 and later.")
- [OrderSummary](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_ordersummary.htm "Represents the current properties and state of an order. Corresponds to one or more order objects, consisting of an original object and any change objects applicable to it. This object is available in API version 48.0 and later.")