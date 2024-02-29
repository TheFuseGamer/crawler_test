# Import Existing Data

Import order and storefront data into Salesforce Order Management
      outside of the B2C Commerce integration.

You can import data such as customer accounts, products, and historical orders outside of         the B2C Commerce integration.

When importing orders, use the [Salesforce B2C Commerce Storefront Order Data Map](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/order_management_b2c_commerce_data_map.htm "These tables illustrate how data in a Salesforce B2C Commerce order packet maps to records in Salesforce Order Management. If you’re implementing your own storefront integration, this map can help you understand the order data requirements.") to identify what data         to include, and load it using the Salesforce Bulk API or Composite API. Allow Order         Management to process each imported order via a Create Order Summary flow or API, as it does         with ingested storefront orders. Doing so ensures proper creation of each OrderSummary and         its related records. When creating an OrderSummary, the source Order record must meet the         following requirements:

- The Order’s Status value must be associated with the <kbd class="ph userinput">Activated</kbd>
          StatusCode.
- At least one OrderDeliveryGroup associated with the Order must exist in Salesforce.

Each OrderSummary has an OrderLifecycleType field, which specifies whether you’ll manage it         with Order Management features. The Create Order Summary flow or API sets the Order         Lifecycle Type field to <kbd class="ph userinput">Managed</kbd> or <kbd class="ph userinput">Unmanaged</kbd>,         and the value can’t be changed. The default value is <kbd class="ph userinput">Managed</kbd>. If you         want to use the unmanaged order lifecycle, implement logic in your Create Order Summary flow         or API calls to set the OrderLifecycleType. For details about the differences between the         managed and unmanaged order lifecycle types, see 	         [Order Lifecycle Management](https://help.salesforce.com/articleView?id=om_order_lifecycle_management.htm&amp;language=en_US "HTML (New Window)") in Salesforce Help.

![Note](/docs/resources/img/en-us/230.0?doc_id=images%2Ficon_note.png&folder=order_management_developer_guide)

#### Note

Examples of orders that use the unmanaged lifecycle type include historical orders and         orders managed by an external system.

When importing order data, consider Order Management’s complex object dependencies. To         maintain data integrity, use a composite REST API request to import order data that lives in         multiple related Salesforce records. For example, you can make one composite request to         import order data in this sequence, which ensures that a record is created after other         records that it references.

![Note](/docs/resources/img/en-us/230.0?doc_id=images%2Ficon_note.png&folder=order_management_developer_guide)

#### Note

This list is a simple example. Real order data usually involves more objects.

1. Shopper account
2. Products
3. Order, which references the account record
4. Order delivery group, which references the order record
5. Order products, which reference the product records, order delivery group record, and
          the order record

If any part of a Composite API request fails, the entire transaction is rolled back. For         information on making Composite API requests, see [Composite](https://developer.salesforce.com/docs/atlas.en-us.230.0.api_rest.meta/api_rest/resources_composite_composite.htm "HTML (New Window)") in the <cite class="cite">REST
          API Developer Guide</cite>.

To import large amounts of data that doesn’t have interobject dependencies, such as catalog         or shopper data, use the Salesforce Bulk API. For information on using the Bulk API, see the             <cite class="cite"><a class="xref" href="https://developer.salesforce.com/docs/atlas.en-us.230.0.api_asynch.meta/api_asynch/asynch_api_intro.htm" target="_blank" title="HTML (New Window)">Bulk API Developer
          Guide</a></cite>.

![Important](/docs/resources/img/en-us/230.0?doc_id=images%2Ficon_note_important.png&folder=order_management_developer_guide)

#### Important

When importing data using API calls, remember that they count toward         your API limits. You can request a temporary increase for importing historical orders by         opening a case with Salesforce Customer Support. Allow at least two weeks for Support to         arrange the increase.

## Salesforce B2C Commerce Data

This table illustrates how some data fields map between B2C Commerce and Salesforce Order         Management. The integration uses these fields to look up records, so if you import or create         Salesforce records used by Order Management, keep them synchronized.

For example, when the integration creates an OrderItem record, it searches for a Product2         record whose StockKeepingUnit matches the product SKU in the order data. If you import         catalog product data, and the StockKeepingUnit values don’t match the product SKU values in         B2C Commerce, then the integration can’t recognize those products. In that case, when an         order comes in with a mismatched product, the integration creates a separate Product2 record         for it.

| B2C Commerce Data | Order Management Object Field |
| --- | --- |
| Shipping Method ID | Order Delivery Method object—Reference ID field |
| Product SKU | Product object—SKU field |
| Payment Processor ID | Payment Gateway object—Reference ID field |
| Site ID / Domain ID | Sales Channel object—Name field |
| Customer Email Address | <ul class="ul bulletList">
                  <li class="li">When using person accounts for the shopper: Account object—Person Email
                    field</li>

                  <li class="li">When using a standard account and contact for the shopper: Contact
                    object—Email field</li>

                </ul> |
| Customer Billing Address First Name and Last Name (concatenated) | Account object—Name field (individual shoppers when not using person
                accounts) |
| Customer Billing Address Company Name | Account object—Name field (business shoppers) |