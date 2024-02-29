# Order Management Standard Objects

Salesforce Order Management provides standard objects to support order management
    functionality.

- **[FulfillmentOrder](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_fulfillmentorder.htm)**

     Represents a group of products and delivery charges on a single order that       share the same fulfillment location, delivery method, and recipient. The       FulfillmentOrderLineItems belonging to a FulfillmentOrder are associated with OrderItemSummary       objects belonging to a single OrderSummary. This object is available in API version 48.0     and later.
- **[FulfillmentOrderItemAdjustment](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_fulfillmentorderitemadjustment.htm)**

     Represents a price adjustment on a FulfillmentOrderLineItem. Corresponds to an       OrderItemAdjustmentLineSummary associated with the corresponding OrderItemSummary. This     object is available in API version 48.0 and later.
- **[FulfillmentOrderItemTax](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_fulfillmentorderitemtax.htm)**

     Represents the tax on a FulfillmentOrderLineItem or       FulfillmentOrderItemAdjustment. Corresponds to an OrderItemTaxLineItemSummary. This     object is available in API version 48.0 and later.
- **[FulfillmentOrderLineItem](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_fulfillmentorderlineitem.htm)**

     Represents a product or delivery charge belonging to a FulfillmentOrder.       Corresponds to an OrderItemSummary. This object is available in API version 48.0 and     later.
- **[OrderAdjustmentGroupSummary](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_orderadjustmentgroupsummary.htm)**

     Represents the current properties and state of a group of related price       adjustments. Associated with a set of OrderItemAdjustmentLineSummaries that apply to       OrderItemSummaries belonging to one OrderSummary. Corresponds to one or more order adjustment       group objects, consisting of an original object and any change objects applicable to it.     This object is available in API version 48.0 and later.
- **[OrderDeliveryGroupSummary](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_orderdeliverygroupsummary.htm)**

     Represents the current properties and state of a group of OrderItemSummaries,       belonging to one OrderSummary, to be fulfilled using the same delivery method and delivered to       the same address. A single shipment can include them all, but that is not guaranteed.       Corresponds to one or more order delivery group objects, consisting of an original object and       any change objects applicable to it. This object is available in API version 48.0 and     later.
- **[OrderItemAdjustmentLineSummary](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_orderitemadjustmentlinesummary.htm)**

     Represents the current properties and state of price adjustments on an       OrderItemSummary. Corresponds to one or more order item adjustment line item objects,       consisting of an original object and any change objects applicable to it. This object is     available in API version 48.0 and later.
- **[OrderItemSummary](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_orderitemsummary.htm)**

     Represents the current properties and state of a product or charge on an       OrderSummary. Corresponds to one or more order item objects, consisting of an original object       and any change objects applicable to it. This object is available in API version 48.0 and     later.
- **[OrderItemSummaryChange](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_orderitemsummarychange.htm)**

     Represents a change to an OrderItemSummary, usually a reduction in quantity due       to a cancel or return. Corresponds to a change order item. This object is available in     API version 48.0 and later.
- **[OrderItemTaxLineItemSummary](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_orderitemtaxlineitemsummary.htm)**

     Represents the current tax on an OrderItemSummary or       OrderItemAdjustmentLineSummary. Corresponds to one or more order item tax line items,       consisting of an original object and any change objects applicable to it. This object is     available in API version 48.0 and later.
- **[OrderPaymentSummary](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_orderpaymentsummary.htm)**

     Represents the current properties and state of payments using a single payment       method that are applied to one OrderSummary. This object is available in API version 48.0     and later.
- **[OrderSummary](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_ordersummary.htm)**

     Represents the current properties and state of an order. Corresponds to one or       more order objects, consisting of an original object and any change objects applicable to       it. This object is available in API version 48.0 and later.
- **[ProcessException](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_processexception.htm)**

     Represents a processing failure on an order summary. A separate process is       required to resolve the failure that caused the process exception before order summary       processing can continue. This object is available in API version 50.0 and     later.
- **[ReturnOrder](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_returnorder.htm)**

Represents the return or repair of inventory or products in Field 			Service, or the return of order products in Order Management. This object is 		available in API version 42.0 and later.
- **[ReturnOrderItemAdjustment](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_returnorderitemadjustment.htm)**

     Represents a price adjustment on a return order line item. This object is     available in API version 50.0 and later.
- **[ReturnOrderItemTax](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_returnorderitemtax.htm)**

     Represents the tax on a return order line item or return order item       adjustment. This object is available in API version 50.0 and later.
- **[ReturnOrderLineItem](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_returnorderlineitem.htm)**

Represents a specific product that is returned or repaired as part of 			a return order in Field service, or a specific order item that is returned as part of a 			return order in Order Management. This object is available in API version 42.0 and 		later.
- **[SalesChannel](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_saleschannel.htm)**

     Represents the origin of an order. For example, a web storefront, physical       store, marketplace, or mobile app. Usually you will set up a SalesChannel for each Site in       your B2C Commerce implementation. This object is available in API version 48.0 and     later.
- **[Order Summary Entity Relationship Diagram](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/order_management_order_summary_erd.htm)**

This diagram illustrates some of the relationships between the OrderSummary object and   other objects used in Salesforce Order Management.
- **[Salesforce B2C Commerce Storefront Order Data Map](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/order_management_b2c_commerce_data_map.htm)**

These tables illustrate how data in a Salesforce B2C Commerce order packet maps to   records in Salesforce Order Management. If you’re implementing your own storefront integration,   this map can help you understand the order data requirements.
- **[Import Existing Data](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/order_management_import_data.htm)**

Import order and storefront data into Salesforce Order Management       outside of the B2C Commerce integration.