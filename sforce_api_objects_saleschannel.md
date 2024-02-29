# SalesChannel

    Represents the origin of an order. For example, a web storefront, physical
      store, marketplace, or mobile app. Usually you will set up a SalesChannel for each Site in
      your B2C Commerce implementation. This object is available in API version 48.0 and
    later.

## Supported Calls

       <samp class="codeph nolang">create()</samp>,          <samp class="codeph nolang">delete()</samp>,          <samp class="codeph nolang">describeLayout()</samp>,          <samp class="codeph nolang">describeSObjects()</samp>,          <samp class="codeph nolang">getDeleted()</samp>,          <samp class="codeph nolang">getUpdated()</samp>,          <samp class="codeph nolang">query()</samp>,          <samp class="codeph nolang">retrieve()</samp>,          <samp class="codeph nolang">search()</samp>,          <samp class="codeph nolang">undelete()</samp>,          <samp class="codeph nolang">update()</samp>,          <samp class="codeph nolang">upsert()</samp>           

## Special Access Rules

This object is only available in Salesforce Order Management orgs.

## Fields

| Field | Details |
| --- | --- |
| Description | - Type<br>

                        - textarea<br>

                    - Properties<br>

                        - Create, Nillable, Update<br>

                      - Description<br>

                          - Description of the SalesChannel. |
| ExternalChannelNumber | - Type<br>

                        - string<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort, Update<br>

                      - Description<br>

                          - External system identifier for the SalesChannel. |
| LastReferencedDate | - Type<br>

                        - dateTime<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                      - Description<br>

                          - The timestamp for when the current user last viewed a record related to this record. |
| LastViewedDate | - Type<br>

                        - dateTime<br>

                    - Properties<br>

                        - Filter, Nillable, Sort<br>

                      - Description<br>

                        - The timestamp for when the current user last viewed this record. A null
                      value can mean that this record has only been referenced (LastReferencedDate)
                      and not viewed. |
| OwnerId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Create, Defaulted on create, Filter, Group, Sort, Update<br>

                      - Description<br>

                          - The ID of the user who currently owns this SalesChannel. Default value is
                      the user logged in to the API to perform the create. |
| SalesChannelName | - Type<br>

                        - string<br>

                    - Properties<br>

                        - Create, Filter, Group, idLookup, Sort, Update<br>

                      - Description<br>

                          - Name of the SalesChannel. |

#### See Also

- [OrderSummary](atlas.en-us.230.0.order_management_developer_guide.meta/order_management_developer_guide/sforce_api_objects_ordersummary.htm "Represents the current properties and state of an order. Corresponds to one or more order objects, consisting of an original object and any change objects applicable to it. This object is available in API version 48.0 and later.")