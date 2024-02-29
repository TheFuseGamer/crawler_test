# ReturnOrder

Represents the return or repair of inventory or products in Field		Service, or the return of order products in Order Management. This object is	available in API version 42.0 and later.

	
		
Return orders are available in Lightning Experience, Salesforce Classic, the Salesforce mobile			app, the Field Service mobile app for Android and iOS, and communities			built using Salesforce Tabs + Visualforce.

	

	

## Supported Calls

				
<samp class="codeph nolang">create()</samp>, <samp class="codeph nolang">delete()</samp>, <samp class="codeph nolang">describeLayout()</samp>, <samp class="codeph nolang">describeSObjects()</samp>, <samp class="codeph nolang">getDeleted()</samp>, <samp class="codeph nolang">getUpdated()</samp>, <samp class="codeph nolang">query()</samp>,				<samp class="codeph nolang">retrieve()</samp>, <samp class="codeph nolang">search()</samp>, <samp class="codeph nolang">undelete()</samp>, <samp class="codeph nolang">update()</samp>, <samp class="codeph nolang">upsert()</samp>

	

	

## Special Access Rules

				
Field Service or Order Management must be enabled.

	

	

## Fields

				

| Field Name | Details |
| --- | --- |
| AccountId | - Type<br>
									    - reference<br>
																									- Properties<br>
									    - Create, Filter, Group, Nillable, Sort, Update<br>
																									- Description<br>
									    - The account associated with the return order. |
| CaseId | - Type<br>
									    - reference<br>
																									- Properties<br>
									    - Create, Filter, Group, Nillable, Sort, Update<br>
																									- Description<br>
									    - The case associated with the return order. |
| ContactId | - Type<br>
									    - reference<br>
																									- Properties<br>
									    - Create, Filter, Group, Nillable, Sort, Update<br>
																									- Description<br>
									    - The contact associated with the return order. |
| Description | - Type<br>
									    - textarea<br>
																									- Properties<br>
									    - Create, Nillable, Update<br>
																									- Description<br>
									    - Notes or context about the return order. |
| DestinationLocationId | - Type<br>
									    - reference<br>
																									- Properties<br>
									    - Create, Filter, Group, Nillable, Sort, Update<br>
																									- Description<br>
									    - The location where the items are being returned to. For										example, if the return order tracks the return of										products from a technician’s van to a warehouse, the										warehouse is the destination location. |
| ExpectedArrivalDate | - Type<br>
									    - dateTime<br>
																									- Properties<br>
									    - Create, Filter, Nillable, Sort, Update<br>
																									- Description<br>
									    - The date when the items are expected to arrive at the										destination location. |
| ExpirationDate | - Type<br>
									    - dateTime<br>
																									- Properties<br>
									    - Create, Filter, Nillable, Sort, Update<br>
																									- Description<br>
									    - Authorizations can’t be captured after their expiration										dates.<br>
									    - This field is available in API version 50.0 and										later. |
| GrandTotalAmount | - Type<br>
									    - currency<br>
																									- Properties<br>
									    - Filter, Nillable, Sort<br>
																									- Description<br>
									    - Total, including adjustments and tax, of the products										and delivery charges on the return order. This includes										all return order line items associated with the return										order. This amount is equal to TotalAmount +										TotalTaxAmount.<br>
									    - This is a calculated field.<br>
									    - This field is available in API version 50.0 and										later. |
| LastReferencedDate | - Type<br>
									    - dateTime<br>
																									- Properties<br>
									    - Filter, Nillable, Sort<br>
																									- Description<br>
									    - The date when the return order was last modified. Its										label in the user interface is Last Modified											Date. |
| LastViewedDate | - Type<br>
									    - dateTime<br>
																									- Properties<br>
									    - Filter, Nillable, Sort<br>
																									- Description<br>
									    - The date when the return order was last viewed. |
| LifeCycleType | - Type<br>
									    - picklist<br>
																									- Properties<br>
									    - Filter, Group, Nillable, Restricted picklist, Sort<br>
																									- Description<br>
									    - Specifies whether the order summary is managed by										Salesforce Order Management (MANAGED) or by an external										system (UNMANAGED). An unmanaged order summary is stored										in Salesforce for reference purposes.<br>
									    - <ul class="ul bulletList">											<li class="li">Some Order Management APIs reject input records											that are associated with unmanaged order											summaries.</li>
											<li class="li">Order Management does not update financial											bucket fields on some records that are associated											with unmanaged order summaries.</li>
											<li class="li">A user with the EditUnmanagedOrderSummaries or											B2BCommerceIntegrator permission can edit certain											fields on objects related to unmanaged order											summaries that are normally only accessible via											APIs.</li>
										</ul><br>
									    - Possible values are: <ul class="ul bulletList">											<li class="li">
<samp class="codeph nolang">MANAGED</samp>—Managed</li>
											<li class="li">
<samp class="codeph nolang">UNMANAGED</samp>—Unmanaged</li>
										</ul><br>
									    - This field is available in API version 50.0 and										later. |
| OrderId | - Type<br>
									    - reference<br>
																									- Properties<br>
									    - Create, Filter, Group, Nillable, Sort, Update<br>
																									- Description<br>
									    - The order associated with the return order. When you										associated a return order with an order, you can										associate the return order’s line items with order										products. |
| OrderSummaryId | - Type<br>
									    - reference<br>
																									- Properties<br>
									    - Create, Filter, Group, Nillable, Sort<br>
																									- Description<br>
									    - ID of the order summary associated with the return										order.<br>
									    - This field is available in API version 50.0 and										later. |
| OwnerId | - Type<br>
									    - reference<br>
																									- Properties<br>
									    - Create, Defaulted on create, Filter, Group, Sort,										Update<br>
																									- Description<br>
									    - The owner of the return order. |
| ProductRequestId | - Type<br>
									    - reference<br>
																									- Properties<br>
									    - Create, Filter, Group, Nillable, Sort, Update<br>
																									- Description<br>
									    - The product request associated with the return order.										When you associated a return order with a product										request, you can associate the return order’s line items										with the product request’s line items.<br>A return order											might be related to a product request if the return											order tracks the return of unused products or											products to be repaired or replaced. For example, a											technician creates a product request for three											motors to prepare for a field visit. If the											technician finds that only two motors are needed,											they can create a return order to return the third											to the original location, and list the product											request in this field. |
| ProductServiceCampaignId | - Type<br>
									    - reference<br>
																									- Properties<br>
									    - Create, Filter, Group, Nillable, Sort, Update<br>
																									- Description<br>
									    - The product service campaign associated with the return										order |
| ReturnOrderNumber | - Type<br>
									    - string<br>
																									- Properties<br>
									    - Autonumber, Defaulted on create, Filter, idLookup, Sort<br>
																									- Description<br>
									    - (Read only) Auto-generated number identifying the return										order. |
| ReturnedById | - Type<br>
									    - reference<br>
																									- Properties<br>
									    - Create, Filter, Group, Nillable, Sort, Update<br>
																									- Description<br>
									    - ID of the user returning the items. |
| ShipFromAddress | - Type<br>
									    - address<br>
																									- Properties<br>
									    - Filter, Nillable<br>
																									- Description<br>
									    - The return shipping address. This address tracks the										location of the items at the start of the return or										repair. For example, if a customer is returning an item,										the Ship From address is the customer’s address. |
| ShipFromCity | - Type<br>
									    - string<br>
																									- Properties<br>
									    - Create, Filter, Group, Nillable, Sort, Update<br>
																									- Description<br>
									    - The city of the return shipping address. This address										tracks the location of the items at the start of the										return or repair. For example, if a customer is										returning an item, the Ship From address is the										customer’s address. |
| ShipFromCountry | - Type<br>
									    - string<br>
																									- Properties<br>
									    - Create, Filter, Group, Nillable, Sort, Update<br>
																									- Description<br>
									    - The country of the return shipping address. This address										tracks the location of the items at the start of the										return or repair. For example, if a customer is										returning an item, the Ship From address is the										customer’s address. |
| ShipFromGeocodeAccuracy | - Type<br>
									    - picklist<br>
																									- Properties<br>
									    - Create, Filter, Group, Nillable, Restricted picklist,										Sort, Update<br>
																									- Description<br>
									    - Accuracy level of the geocode for the return shipping										address. See Compound Field Considerations and Limitations for details on geolocation compound											fields.<br>
![Note](/docs/resources/img/en-us/230.0?doc_id=images%2Ficon_note.png&folder=order_management_developer_guide)<br>
Note
<br>This field is available in the API											only. |
| ShipFromLatitude | - Type<br>
									    - double<br>
																									- Properties<br>
									    - Create, Filter, Nillable, Sort, Update<br>
																									- Description<br>
									    - Used with Longitude to specify the precise geolocation										of the return shipping address. Acceptable values are										numbers between –90 and 90 with up to 15 decimal places.										See Compound Field Considerations and Limitations for details on geolocation compound											fields.<br>
![Note](/docs/resources/img/en-us/230.0?doc_id=images%2Ficon_note.png&folder=order_management_developer_guide)<br>
Note
<br>This field is available in the API											only. |
| ShipFromLongitude | - Type<br>
									    - double<br>
																									- Properties<br>
									    - Create, Filter, Nillable, Sort, Update<br>
																									- Description<br>
									    - Used with Latitude to specify the precise geolocation of										the return shipping address. Acceptable values are										numbers between –180 and 180 with up to 15 decimal										places. See Compound Field Considerations and Limitations for details on geolocation compound											fields.<br>
![Note](/docs/resources/img/en-us/230.0?doc_id=images%2Ficon_note.png&folder=order_management_developer_guide)<br>
Note
<br>This field is available in the API											only. |
| ShipFromPostalCode | - Type<br>
									    - string<br>
																									- Properties<br>
									    - Create, Filter, Group, Nillable, Sort, Update<br>
																									- Description<br>
									    - The postal code of the return shipping address. This										address tracks the location of the items at the start of										the return or repair. For example, if a customer is										returning an item, the Ship From address is the										customer’s address. |
| ShipFromState | - Type<br>
									    - string<br>
																									- Properties<br>
									    - Create, Filter, Group, Nillable, Sort, Update<br>
																									- Description<br>
									    - The state of the return shipping address. This address										tracks the location of the items at the start of the										return or repair. For example, if a customer is										returning an item, the Ship From address is the										customer’s address. |
| ShipFromStreet | - Type<br>
									    - textarea<br>
																									- Properties<br>
									    - Create, Filter, Group, Nillable, Sort, Update<br>
																									- Description<br>
									    - The street of the return shipping address. This address										tracks the location of the items at the start of the										return or repair. For example, if a customer is										returning an item, the Ship From address is the										customer’s address. |
| ShipmentType | - Type<br>
									    - picklist<br>
																									- Properties<br>
									    - Create, Defaulted on create, Filter, Group, Nillable,										Sort, Update<br>
																									- Description<br>
									    - The type of shipment associated with the return order.										Available values are:<ul class="ul bulletList">											<li class="li">Standard (default value)</li>
											<li class="li">Rush</li>
											<li class="li">Overnight</li>
											<li class="li">Next Business Day</li>
											<li class="li">Pickup</li>
										</ul> |
| SourceLocationId | - Type<br>
									    - reference<br>
																									- Properties<br>
									    - Create, Filter, Group, Nillable, Sort, Update<br>
																									- Description<br>
									    - The items’ location at the start of the return or										repair. For example, if the return order tracks the										return of products from a technician’s service vehicle										to a warehouse, the service vehicle is the source										location. |
| Status | - Type<br>
									    - picklist<br>
																									- Properties<br>
									    - Create, Defaulted on create, Filter, Group, Nillable,										Sort, Update<br>
																									- Description<br>
									    - The status of the return order. Available values are:<ul class="ul bulletList">											<li class="li">Draft</li>
											<li class="li">Submitted</li>
											<li class="li">Approved</li>
											<li class="li">Canceled</li>
											<li class="li">Closed</li>
										</ul> |
| StatusCategory | - Type<br>
									    - picklist<br>
																									- Properties<br>
									    - Defaulted on create, Filter, Group, Nillable, Restricted										picklist, Sort<br>
																									- Description<br>
									    - Status category of the return order. Processing of the										return order depends on this value. Each status category										corresponds to one or more statuses.<br>
									    - Possible values are: <ul class="ul bulletList">											<li class="li"><samp class="codeph nolang">Activated</samp></li>
											<li class="li"><samp class="codeph nolang">Canceled</samp></li>
											<li class="li"><samp class="codeph nolang">Closed</samp></li>
											<li class="li"><samp class="codeph nolang">Draft</samp></li>
										</ul><br>
									    - This field is available in API version 50.0 and										later. |
| TaxLocaleType | - Type<br>
									    - picklist<br>
																									- Properties<br>
									    - Filter, Group, Nillable, Restricted picklist, Sort<br>
																									- Description<br>
									    - The system used to handle tax on the original order										associated with the return order. Gross usually applies										to taxes like value-added tax (VAT), and Net usually										applies to taxes like sales tax.<br>
									    - Possible values are: <ul class="ul bulletList">											<li class="li">
<samp class="codeph nolang">Gross</samp>											(displays most prices and taxes as combined											values)</li>
											<li class="li">
<samp class="codeph nolang">Net</samp>											(displays most prices and taxes as separate											values)</li>
										</ul><br>
									    - This field is available in API version 50.0 and										later. |
| TotalAmount | - Type<br>
									    - currency<br>
																									- Properties<br>
									    - Filter, Nillable, Sort<br>
																									- Description<br>
									    - Adjusted total, not including tax, of the return order										line items, including products and delivery charges, on										the ReturnOrder.<br>
									    - This is a calculated field.<br>
									    - This field is available in API version 50.0 and										later. |
| TotalDeliveryAdjustAmount | - Type<br>
									    - currency<br>
																									- Properties<br>
									    - Filter, Nillable, Sort<br>
																									- Description<br>
									    - Total amount of the price adjustments applied to the										delivery charges on the return order. This value only										includes adjustments to return order line items of type										code Charge.<br>
									    - This is a calculated field.<br>
									    - This field is available in API version 50.0 and										later. |
| TotalDeliveryAdjustAmtWithTax | - Type<br>
									    - currency<br>
																									- Properties<br>
									    - Filter, Nillable, Sort<br>
																									- Description<br>
									    - Total amount of the price adjustments applied to the										delivery charges on the return order, inclusive of tax.										This value only includes adjustments to return order										line items of type code Charge. This amount is equal to										TotalDeliveryAdjustAmount +										TotalDeliveryAdjustTaxAmount.<br>
									    - This is a calculated field.<br>
									    - This field is available in API version 50.0 and										later. |
| TotalDeliveryAdjustTaxAmount | - Type<br>
									    - currency<br>
																									- Properties<br>
									    - Filter, Nillable, Sort<br>
																									- Description<br>
									    - Tax on the TotalDeliveryAdjustmentAmount.<br>
									    - This is a calculated field.<br>
									    - This field is available in API version 50.0 and										later. |
| TotalDeliveryAmount | - Type<br>
									    - currency<br>
																									- Properties<br>
									    - Filter, Nillable, Sort<br>
																									- Description<br>
									    - Total of the delivery charges on the return order. This										value only includes return order line items of type code										Charge.<br>
									    - This is a calculated field.<br>
									    - This field is available in API version 50.0 and										later. |
| TotalDeliveryAmtWithTax | - Type<br>
									    - currency<br>
																									- Properties<br>
									    - Filter, Nillable, Sort<br>
																									- Description<br>
									    - Total amount of the delivery charges on the return										order, inclusive of tax. This value only includes return										order line items of type code Charge. This amount is										equal to TotalDeliveryAmount +										TotalDeliveryTaxAmount.<br>
									    - This is a calculated field.<br>
									    - This field is available in API version 50.0 and										later. |
| TotalDeliveryTaxAmount | - Type<br>
									    - currency<br>
																									- Properties<br>
									    - Filter, Nillable, Sort<br>
																									- Description<br>
									    - Tax on the TotalDeliveryAmount.<br>
									    - This is a calculated field.<br>
									    - This field is available in API version 50.0 and										later. |
| TotalProductAdjustAmount | - Type<br>
									    - currency<br>
																									- Properties<br>
									    - Filter, Nillable, Sort<br>
																									- Description<br>
									    - Total amount of the price adjustments applied to the										products on the return order. This value only includes										adjustments to return order line items of type code										Product.<br>
									    - This is a calculated field.<br>
									    - This field is available in API version 50.0 and										later. |
| TotalProductAdjustAmtWithTax | - Type<br>
									    - currency<br>
																									- Properties<br>
									    - Filter, Nillable, Sort<br>
																									- Description<br>
									    - Total amount of the price adjustments applied to the										products on the return order, inclusive of tax. This										value only includes adjustments to return order line										items of type code Product. This amount is equal to										TotalProductAdjustAmount +										TotalProductAdjustTaxAmount.<br>
									    - This is a calculated field.<br>
									    - This field is available in API version 50.0 and										later. |
| TotalProductAdjustTaxAmount | - Type<br>
									    - currency<br>
																									- Properties<br>
									    - Filter, Nillable, Sort<br>
																									- Description<br>
									    - Tax on the TotalProductAdjustmentAmount.<br>
									    - This is a calculated field.<br>
									    - This field is available in API version 50.0 and										later. |
| TotalProductAmount | - Type<br>
									    - currency<br>
																									- Properties<br>
									    - Filter, Nillable, Sort<br>
																									- Description<br>
									    - Total of the product charges on the return order. This										value only includes return order line items of type code										Product.<br>
									    - This is a calculated field.<br>
									    - This field is available in API version 50.0 and										later. |
| TotalProductAmtWithTax | - Type<br>
									    - currency<br>
																									- Properties<br>
									    - Filter, Nillable, Sort<br>
																									- Description<br>
									    - Total amount of the product charges on the return order,										inclusive of tax. This value only includes return order										line items of type code Product. This amount is equal to										TotalProductAmount + TotalProductTaxAmount.<br>
									    - This is a calculated field.<br>
									    - This field is available in API version 50.0 and										later. |
| TotalProductTaxAmount | - Type<br>
									    - currency<br>
																									- Properties<br>
									    - Filter, Nillable, Sort<br>
																									- Description<br>
									    - Tax on the TotalProductAmount.<br>
									    - This is a calculated field.<br>
									    - This field is available in API version 50.0 and										later. |
| TotalTaxAmount | - Type<br>
									    - currency<br>
																									- Properties<br>
									    - Filter, Nillable, Sort<br>
																									- Description<br>
									    - Tax on the TotalAmount.<br>
									    - This is a calculated field.<br>
									    - This field is available in API version 50.0 and										later. |

	

	

## Usage

				
You can use return orders to track customer returns, customer repairs, or the return of inventory from a technician’s van stock to a warehouse or supplier. Customers can			initiate a return from a community, or agents can create return orders in response to a customer call or technician request.

		
Return orders are composed of return order line items, which allow you to add details about the items being returned. To represent the returned items, each line item must list			one or more of the following: product, product item, asset, product request line item, and order product. Return orders can be associated with a product request, case, account,			contact, and order if needed. This versatility lets you use return orders to track a wide range of return scenarios.

	

	

## Associated Objects

				
This object has the following associated objects. Unless noted, they are available in the same API version as this object.

		
							- ReturnOrderFeed

				    - Feed tracking is available for the object.

										- ReturnOrderHistory

				    - History is available for tracked fields of the object.

										- ReturnOrderOwnerSharingRule

				    - Sharing rules are available for the object.

										- ReturnOrderShare

				    - Sharing is available for the object.