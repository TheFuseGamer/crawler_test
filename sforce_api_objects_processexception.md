# ProcessException

    Represents a processing failure on an order summary. A separate process is
      required to resolve the failure that caused the process exception before order summary
      processing can continue. This object is available in API version 50.0 and
    later.

## Supported Calls

<samp class="codeph nolang">create()</samp>,  <samp class="codeph nolang">delete()</samp>,  <samp class="codeph nolang">describeLayout()</samp>,  <samp class="codeph nolang">describeSObjects()</samp>,  <samp class="codeph nolang">getDeleted()</samp>, <samp class="codeph nolang">getUpdated()</samp>,  <samp class="codeph nolang">query()</samp>,  <samp class="codeph nolang">retrieve()</samp>,  <samp class="codeph nolang">search()</samp>,  <samp class="codeph nolang">undelete()</samp>,  <samp class="codeph nolang">update()</samp>,  <samp class="codeph nolang">upsert()</samp>

## Fields

| Field | Details |
| --- | --- |
| AttachedToId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Create, Filter, Group, Sort, Update<br>

                      - Description<br>

                          - ID of the object associated with the ProcessException. |
| CaseId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort, Update<br>

                      - Description<br>

                          - ID of the case associated with the ProcessException. |
| Category | - Type<br>

                        - picklist<br>

                    - Properties<br>

                        - Create, Defaulted on create, Filter, Group, Nillable, Sort, Update<br>

                      - Description<br>

                          - ProcessingException type. You can customize the category picklist to
                      represent your business processes.<br>

                          - Possible values are:
                      <ul class="ul bulletList">
                        <li class="li"><samp class="codeph nolang">Fulfillment</samp></li>

                        <li class="li"><samp class="codeph nolang">Invoicing</samp></li>

                        <li class="li"><samp class="codeph nolang">Order Activation</samp></li>

                        <li class="li"><samp class="codeph nolang">Order Approval</samp></li>

                        <li class="li"><samp class="codeph nolang">Payment</samp></li>

                      </ul> |
| Description | - Type<br>

                        - textarea<br>

                    - Properties<br>

                        - Create, Nillable, Update<br>

                      - Description<br>

                          - Detailed description of the ProcessException. |
| ExternalReference | - Type<br>

                        - string<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort, Update<br>

                      - Description<br>

                          - Description of external entities associated with the
                      ProcessException. |
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
| Message | - Type<br>

                        - string<br>

                    - Properties<br>

                        - Create, Filter, Group, Sort, Update<br>

                      - Description<br>

                          - Short description of the ProcessException |
| OrderSummaryId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Create, Filter, Group, Nillable, Sort, Update<br>

                      - Description<br>

                          - ID of the OrderSummary associated with the ProcessException. The
                      ProcessException component is displayed on this OrderSummary. |
| OwnerId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Create, Defaulted on create, Filter, Group, Sort, Update<br>

                      - Description<br>

                        - ID of the User who currently owns this ProcessException. Default value is
                      the User logged in to the API to perform the create. |
| Priority | - Type<br>

                        - picklist<br>

                    - Properties<br>

                        - Create, Defaulted on create, Filter, Group, Nillable, Sort, Update<br>

                      - Description<br>

                          - Resolution priority for the ProcessException. You can customize the
                      priority picklist to represent your business processes.<br>

                          - Possible values are:
                      <ul class="ul bulletList">
                        <li class="li"><samp class="codeph nolang">High</samp></li>

                        <li class="li"><samp class="codeph nolang">Low</samp></li>

                      </ul> |
| ProcessExceptionNumber | - Type<br>

                        - string<br>

                    - Properties<br>

                        - Autonumber, Defaulted on create, Filter, idLookup, Sort<br>

                      - Description<br>

                          - The unique name of the ProcessException, formatted as PE-(00000000). |
| Severity | - Type<br>

                        - picklist<br>

                    - Properties<br>

                        - Create, Defaulted on create, Filter, Group, Nillable, Sort, Update<br>

                      - Description<br>

                          - Severity of the ProcessException. Each severity value corresponds to one
                      severity category. You can customize the severity picklist to represent your
                      business processes. If you customize the severity picklist, include at least
                      one severity value for each severity category.<br>

                          - Possible values are:
                      <ul class="ul bulletList">
                        <li class="li"><samp class="codeph nolang">High</samp></li>

                        <li class="li"><samp class="codeph nolang">Low</samp></li>

                      </ul> |
| SeverityCategory | - Type<br>

                        - picklist<br>

                    - Properties<br>

                        - Filter, Group, Nillable, Restricted picklist, Sort<br>

                      - Description<br>

                        - Severity category of the ProcessException. Each severity category
                      corresponds to one or more severity values. The severity category is used to
                      show the severity icon in the ProcessException list view.<br>

                          - Possible values are:
                      <ul class="ul bulletList">
                        <li class="li"><samp class="codeph nolang">High</samp></li>

                        <li class="li"><samp class="codeph nolang">Low</samp></li>

                      </ul> |
| Status | - Type<br>

                        - picklist<br>

                    - Properties<br>

                        - Create, Defaulted on create, Filter, Group, Sort, Update<br>

                      - Description<br>

                        - Status of the ProcessException. Each status corresponds to one status
                      category, shown here in parentheses. You can customize the status picklist to
                      represent your business processes. If you customize the status picklist,
                      include at least one status value for each status category.<br>

                          - Possible values are:
                      <ul class="ul bulletList">
                        <li class="li">
<samp class="codeph nolang">Ignored</samp> (Inactive)</li>

                        <li class="li">
<samp class="codeph nolang">New</samp> (Active)</li>

                        <li class="li">
<samp class="codeph nolang">Paused</samp> (Inactive)</li>

                        <li class="li">
<samp class="codeph nolang">Resolved</samp> (Resolved)</li>

                        <li class="li">
<samp class="codeph nolang">Triaged</samp> (Active)</li>

                        <li class="li">
<samp class="codeph nolang">Voided</samp> (Inactive)</li>

                      </ul> |
| StatusCategory | - Type<br>

                        - picklist<br>

                    - Properties<br>

                        - Filter, Group, Restricted picklist, Sort<br>

                      - Description<br>

                        - Status category of the ProcessException. Each status category corresponds to
                      one or more statuses.<br>

                          - Possible values are:
                      <ul class="ul bulletList">
                        <li class="li"><samp class="codeph nolang">ACTIVE</samp></li>

                        <li class="li"><samp class="codeph nolang">INACTIVE</samp></li>

                        <li class="li"><samp class="codeph nolang">RESOLVED</samp></li>

                      </ul> |

## Associated Objects

This object has the following associated objects. Unless noted, they are available in the
        same API version as this object.

            - ProcessExceptionOwnerSharingRule

                - Sharing rules are available for the object.

            - ProcessExceptionShare

                - Sharing is available for the object.