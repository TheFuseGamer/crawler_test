# ReturnOrderLineItem

Represents a specific product that is returned or repaired as part of		a return order in Field service, or a specific order item that is returned as part of a		return order in Order Management. This object is available in API version 42.0 and	later.

	
		
Return orders are available in Lightning Experience, Salesforce Classic, the Salesforce mobile			app, the Field Service mobile app for Android and iOS, and communities			built using Salesforce Tabs + Visualforce.

	

	

## Supported Calls

				
<samp class="codeph nolang">create()</samp>, <samp class="codeph nolang">delete()</samp>, <samp class="codeph nolang">describeLayout()</samp>, <samp class="codeph nolang">describeSObjects()</samp>, <samp class="codeph nolang">getDeleted()</samp>, <samp class="codeph nolang">getUpdated()</samp>, <samp class="codeph nolang">query()</samp>,				<samp class="codeph nolang">retrieve()</samp>, <samp class="codeph nolang">search()</samp>, <samp class="codeph nolang">undelete()</samp>, <samp class="codeph nolang">update()</samp>, <samp class="codeph nolang">upsert()</samp>

	

	

## Special Access Rules

				
Field Service or Order Management must be enabled.

	

	

## Fields

				

| Field Name | Details |
| --- | --- |
| AssetId | - Type<br>
									    - reference<br>
																									- Properties<br>
									    - Create, Filter, Group, Nillable, Sort, Update<br>
																									- Description<br>
									    - The asset associated with the return order line item.										One or more of the following fields must be filled out:										AssetId, OrderItemId, Product2Id, ProductItemId, and										ProductRequestLineItemId. |
| ChangeOrderItemId | - Type<br>
									    - reference<br>
																									- Properties<br>
									    - Create, Filter, Group, Nillable, Sort<br>
																									- Description<br>
									    - ID of the change order item associated with the return										order line item.<br>
									    - This field is available in API version 50.0 and										later. |
| Description | - Type<br>
									    - textarea<br>
																									- Properties<br>
									    - Create, Nillable, Update<br>
																									- Description<br>
									    - Notes or context about the return order line item. |
| DestinationLocationId | - Type<br>
									    - reference<br>
																									- Properties<br>
									    - Create, Filter, Group, Nillable, Sort, Update<br>
																									- Description<br>
									    - The location where the items are being returned to. For										example, if the return order tracks the return of										products from a technician’s van to a warehouse, the										warehouse is the destination location. |
| GrossUnitPrice | - Type<br>
									    - currency<br>
																									- Properties<br>
									    - Create, Filter, Nillable, Sort, Update<br>
																									- Description<br>
									    - Unit price, including tax, of the product represented by										the associated order item summary.<br>
									    - This field is available in API version 50.0 and										later. |
| LastReferencedDate | - Type<br>
									    - dateTime<br>
																									- Properties<br>
									    - Filter, Nillable, Sort<br>
																									- Description<br>
									    - The date when the return order line item was last										modified. Its label in the user interface is											Last Modified Date. |
| LastViewedDate | - Type<br>
									    - dateTime<br>
																									- Properties<br>
									    - Filter, Nillable, Sort<br>
																									- Description<br>
									    - The date when the return order line item was last										viewed. |
| OrderItemId | - Type<br>
									    - reference<br>
																									- Properties<br>
									    - Create, Filter, Group, Nillable, Sort, Update<br>
																									- Description<br>
									    - The order product associated with the return order line										item. One or more of the following fields must be filled										out: AssetId, OrderItemId, Product2Id, ProductItemId,										and ProductRequestLineItemId. |
| OrderItemSummaryId | - Type<br>
									    - reference<br>
																									- Properties<br>
									    - Create, Filter, Group, Nillable, Sort<br>
																									- Description<br>
									    - ID of the order item summary associated with the return										order line item.<br>
									    - This field is available in API version 50.0 and										later. |
| ProcessingPlan | - Type<br>
									    - picklist<br>
																									- Properties<br>
									    - Create, Defaulted on create, Filter, Group, Nillable,										Sort, Update<br>
																									- Description<br>
									    - Indicates the preferred fate of the items following										their return. Available values are:<ul class="ul bulletList">											<li class="li">
<samp class="codeph nolang">Repair</samp>—Repair the items and											return them to the owner</li>
											<li class="li">
<samp class="codeph nolang">Discard</samp>—Discard the items</li>
											<li class="li">
<samp class="codeph nolang">Salvage</samp>—Salvage the items’											working parts</li>
											<li class="li">
<samp class="codeph nolang">Restock</samp>—Return the items to your											inventory</li>
										</ul> |
| Product2Id | - Type<br>
									    - reference<br>
																									- Properties<br>
									    - Create, Filter, Group, Nillable, Sort, Update<br>
																									- Description<br>
									    - The product associated with the return order line item.										One or more of the following fields must be filled out:										AssetId, OrderItemId, Product2Id, ProductItemId, and										ProductRequestLineItemId. |
| ProductItemId | - Type<br>
									    - reference<br>
																									- Properties<br>
									    - Create, Filter, Group, Nillable, Sort, Update<br>
																									- Description<br>
									    - The product item representing the location of the										product at the start of the return. One or more of the										following fields must be filled out: AssetId,										OrderItemId, Product2Id, ProductItemId, and										ProductRequestLineItemId. |
| ProductRequestLineItemId | - Type<br>
									    - reference<br>
																									- Properties<br>
									    - Create, Filter, Group, Nillable, Sort, Update<br>
																									- Description<br>
									    - The product request line item associated with the return										order line item. One or more of the following fields										must be filled out: AssetId, OrderItemId, Product2Id,										ProductItemId, and ProductRequestLineItemId. |
| ProductServiceCampaignId | - Type<br>
									    - reference<br>
																									- Properties<br>
									    - Filter, Group, Nillable, Sort<br>
																									- Description<br>
									    - The product service campaign associated with the return										order line item. |
| ProductServiceCampaignItemId | - Type<br>
									    - reference<br>
																									- Properties<br>
									    - Create, Filter, Group, Nillable, Sort, Update<br>
																									- Description<br>
									    - The product service campaign item associated with the										return order line item. |
| QuantityExpected | - Type<br>
									    - double<br>
																									- Properties<br>
									    - Create, Filter, Nillable, Sort, Update<br>
																									- Description<br>
									    - The quantity of items expected to be returned.<br>
									    - This field is available in API version 50.0 and										later. |
| QuantityReceived | - Type<br>
									    - double<br>
																									- Properties<br>
									    - Create, Filter, Nillable, Sort, Update<br>
																									- Description<br>
									    - The actual quantity of items received for return.<br>
									    - This field is available in API version 50.0 and										later. |
| QuantityRejected | - Type<br>
									    - double<br>
																									- Properties<br>
									    - Create, Filter, Nillable, Sort, Update<br>
																									- Description<br>
									    - The quantity of items rejected for return.<br>
									    - This field is available in API version 50.0 and										later. |
| QuantityReturned | - Type<br>
									    - double<br>
																									- Properties<br>
									    - Create, Filter, Sort, Update<br>
																									- Description<br>
									    - The quantity of items being returned. If multiple types										of products are being returned, track each product in a										different return order line item. |
| QuantityUnitOfMeasure | - Type<br>
									    - picklist<br>
																									- Properties<br>
									    - Create, Filter, Group, Nillable, Sort, Update<br>
																									- Description<br>
									    - Units of the returned items; for example, kilograms or										liters. Quantity Unit of Measure picklist values are										inherited from the Quantity Unit of Measure field on										products. |
| ReasonForRejection | - Type<br>
									    - picklist<br>
																									- Properties<br>
									    - Create, Defaulted on create, Filter, Group, Nillable,										Sort, Update<br>
																									- Description<br>
									    - Reason for rejecting returned items on this return order										line item.<br>
									    - Possible values are: <ul class="ul bulletList">											<li class="li"><samp class="codeph nolang">Damaged											Item</samp></li>
											<li class="li"><samp class="codeph nolang">Expired											Warranty</samp></li>
											<li class="li"><samp class="codeph nolang">Missing Item or											Part</samp></li>
											<li class="li"><samp class="codeph nolang">Wrong											Item</samp></li>
										</ul><br>
									    - This field is available in API version 50.0 and										later. |
| ReasonForReturn | - Type<br>
									    - picklist<br>
																									- Properties<br>
									    - Create, Defaulted on create, Filter, Group, Nillable,										Sort, Update<br>
																									- Description<br>
									    - The reason the items are being returned. Available										values are:<ul class="ul bulletList">											<li class="li"><samp class="codeph nolang">Damaged</samp></li>
											<li class="li"><samp class="codeph nolang">Defective</samp></li>
											<li class="li"><samp class="codeph nolang">Duplicate											Order</samp></li>
											<li class="li"><samp class="codeph nolang">Wrong											Item</samp></li>
											<li class="li"><samp class="codeph nolang">Wrong											Quantity</samp></li>
											<li class="li"><samp class="codeph nolang">Not											Satisfied</samp></li>
											<li class="li"><samp class="codeph nolang">Outdated</samp></li>
											<li class="li"><samp class="codeph nolang">Other</samp></li>
										</ul> |
| RepaymentMethod | - Type<br>
									    - picklist<br>
																									- Properties<br>
									    - Create, Defaulted on create, Filter, Group, Nillable,										Sort, Update<br>
																									- Description<br>
									    - The method by which the customer or owner will be										reimbursed for the items being returned. Available										values are:<ul class="ul bulletList">											<li class="li">
<samp class="codeph nolang">Replace</samp>—The items will be											replaced</li>
											<li class="li">
<samp class="codeph nolang">Refund</samp>—The items will be returned											and the owner will be refunded</li>
											<li class="li">
<samp class="codeph nolang">Credit</samp>—The items will be returned											and the owner will receive credit for them</li>
											<li class="li">
<samp class="codeph nolang">Return</samp>—The items will be returned											to the owner (for example, following their											repair)</li>
										</ul> |
| ReturnOrderId | - Type<br>
									    - reference<br>
																									- Properties<br>
									    - Create, Filter, Group, Sort<br>
																									- Description<br>
									    - The return order that the return order line item belongs										to. |
| ReturnOrderLineItemNumber | - Type<br>
									    - string<br>
																									- Properties<br>
									    - Autonumber, Defaulted on create, Filter, idLookup, Sort<br>
																									- Description<br>
									    - (Read only) Auto-generated number that identifies the										return order line item. |
| SourceLocationId | - Type<br>
									    - reference<br>
																									- Properties<br>
									    - Create, Filter, Group, Nillable, Sort, Update<br>
																									- Description<br>
									    - The items’ location at the start of the return or										repair. For example, if the return order tracks the										return of products from a technician’s service vehicle										to a warehouse, the service vehicle is the source										location. |
| TotalAdjustmentAmount | - Type<br>
									    - currency<br>
																									- Properties<br>
									    - Filter, Nillable, Sort<br>
																									- Description<br>
									    - Total of all price adjustments applied to the return										order line item.<br>
									    - This is a calculated field.<br>
									    - This field is available in API version 50.0 and										later. |
| TotalAdjustmentAmountWithTax | - Type<br>
									    - currency<br>
																									- Properties<br>
									    - Filter, Nillable, Sort<br>
																									- Description<br>
									    - Total amount of the price adjustments applied to the										return order line item, inclusive of tax. This amount is										equal to TotalAdjustmentAmount +										TotalAdjustmentTaxAmount.<br>
									    - This is a calculated field.<br>
									    - This field is available in API version 50.0 and										later. |
| TotalAdjustmentTaxAmount | - Type<br>
									    - currency<br>
																									- Properties<br>
									    - Filter, Nillable, Sort<br>
																									- Description<br>
									    - Tax on the TotalAdjustmentAmount.<br>
									    - This is a calculated field.<br>
									    - This field is available in API version 50.0 and										later. |
| TotalAmount | - Type<br>
									    - currency<br>
																									- Properties<br>
									    - Filter, Nillable, Sort<br>
																									- Description<br>
									    - Total, including adjustments and tax, of the return										order line item.<br>
									    - This is a calculated field.<br>
									    - This field is available in API version 50.0 and										later. |
| TotalLineAmount | - Type<br>
									    - currency<br>
																									- Properties<br>
									    - Create, Defaulted on create, Filter, Nillable, Sort,										Update<br>
																									- Description<br>
									    - Total, not including adjustments or tax, of the return										order line item.<br>
									    - This field is available in API version 50.0 and										later. |
| TotalLineAmountWithTax | - Type<br>
									    - currency<br>
																									- Properties<br>
									    - Filter, Nillable, Sort<br>
																									- Description<br>
									    - Total price of the return order line item, inclusive of										tax. This amount is equal to TotalLineAmount +										TotalLineTaxAmount.<br>
									    - This is a calculated field.<br>
									    - This field is available in API version 50.0 and										later. |
| TotalLineTaxAmount | - Type<br>
									    - currency<br>
																									- Properties<br>
									    - Filter, Nillable, Sort<br>
																									- Description<br>
									    - Tax on the TotalLineAmount.<br>
									    - This is a calculated field.<br>
									    - This field is available in API version 50.0 and										later. |
| TotalPrice | - Type<br>
									    - currency<br>
																									- Properties<br>
									    - Filter, Nillable, Sort<br>
																									- Description<br>
									    - Total, including adjustments but not tax, of the return										order line item. Equal to UnitPrice times Quantity.<br>
									    - This is a calculated field. |
| TotalTaxAmount | - Type<br>
									    - currency<br>
																									- Properties<br>
									    - Filter, Nillable, Sort<br>
																									- Description<br>
									    - Tax on the TotalAmount.<br>
									    - This is a calculated field.<br>
									    - This field is available in API version 50.0 and										later. |
| Type | - Type<br>
									    - picklist<br>
																									- Properties<br>
									    - Create, Filter, Group, Nillable, Restricted picklist,										Sort, Update<br>
																									- Description<br>
									    - Type of the return order line item. Matches the type of										the associated order item summary. Delivery Charge										indicates that the return order line item represents a										delivery charge. Order Product indicates that it										represents any other type of product, service, or										charge. Each type corresponds to one type code.<br>
									    - Possible values are: <ul class="ul bulletList">											<li class="li"><samp class="codeph nolang">Delivery											Charge</samp></li>
											<li class="li"><samp class="codeph nolang">Order											Product</samp></li>
										</ul><br>
									    - This field is available in API version 50.0 and										later. |
| TypeCode | - Type<br>
									    - picklist<br>
																									- Properties<br>
									    - Create, Filter, Group, Nillable, Restricted picklist,										Sort, Update<br>
																									- Description<br>
									    - Type code of the return order line item. Matches the										type code of the associated order item summary.										Processing depends on this value. Charge indicates that										the return order line item represents a delivery charge.										Product indicates that it represents an other type of										product, service, or charge. Each type category										corresponds to one or more types.<br>
									    - Possible values are: <ul class="ul bulletList">											<li class="li"><samp class="codeph nolang">Charge</samp></li>
											<li class="li"><samp class="codeph nolang">Product</samp></li>
										</ul><br>
									    - This field is available in API version 50.0 and										later. |
| UnitPrice | - Type<br>
									    - currency<br>
																									- Properties<br>
									    - Create, Defaulted on create, Filter, Nillable, Sort,										Update<br>
																									- Description<br>
									    - Unit price of the return order line item.<br>
									    - This field is available in API version 50.0 and										later. |

	

	

## Associated Objects

				
This object has the following associated objects. Unless noted, they are available in the same API version as this object.

		
							- ReturnOrderLineItemFeed

				    - Feed tracking is available for the object.

										- ReturnOrderLineItemHistory

				    - History is available for tracked fields of the object.