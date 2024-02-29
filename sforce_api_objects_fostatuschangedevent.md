# FOStatusChangedEvent

    Notifies subscribers of changes to the status of a fulfillment order record.
      Use this event to trigger flows and processes in your order workflow. This object is
    available in API version 48.0 and later.

## Supported Calls

<samp class="codeph nolang">describeSObjects()</samp>

## Supported Subscribers

| Subscriber | Supported? |
| --- | --- |
| Apex Triggers | ![Yes](/docs/resources/img/en-us/230.0?doc_id=dev_guides%2Fplatform_events%2Fimages%2Fcheckmark_16.png&folder=order_management_developer_guide) |
| Flows | ![Yes](/docs/resources/img/en-us/230.0?doc_id=dev_guides%2Fplatform_events%2Fimages%2Fcheckmark_16.png&folder=order_management_developer_guide) |
| Processes | ![Yes](/docs/resources/img/en-us/230.0?doc_id=dev_guides%2Fplatform_events%2Fimages%2Fcheckmark_16.png&folder=order_management_developer_guide) |
| Streaming API (CometD) | ![Yes](/docs/resources/img/en-us/230.0?doc_id=dev_guides%2Fplatform_events%2Fimages%2Fcheckmark_16.png&folder=order_management_developer_guide) |

## Streaming API Subscription Channel

<samp class="codeph nolang">/event/FOStatusChangedEvent</samp>

## Special Access Rules

FOStatusChangedEvent is available as part of Salesforce Order Management.

## Fields

| Field | Details |
| --- | --- |
| FulfillmentOrderId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Nillable<br>

                    - Description<br>

                        - ID of the FulfillmentOrder whose status changed.<br>

                        - This value is functionally required, but is nillable because fulfillment
                      order records can be deleted to comply with data protection and privacy
                      requirements. |
| NewStatus | - Type<br>

                        - picklist<br>

                    - Properties<br>

                        - None<br>

                    - Description<br>

                        - Required. The new value of the Status field on the FulfillmentOrder.<br>

                        - Possible values are defined by the Status field picklist on the
                      FulfillmentOrder object. |
| NewStatusCategory | - Type<br>

                        - picklist<br>

                    - Properties<br>

                        - Restricted picklist<br>

                    - Description<br>

                        - Required. The new value of the StatusCategory field on the
                      FulfillmentOrder.<br>

                        - Possible values are: <ul class="ul bulletList">
                        <li class="li"><samp class="codeph nolang">Activated</samp></li>

                        <li class="li"><samp class="codeph nolang">Cancelled</samp></li>

                        <li class="li"><samp class="codeph nolang">Closed</samp></li>

                        <li class="li"><samp class="codeph nolang">Draft</samp></li>

                        <li class="li"><samp class="codeph nolang">Fulfilling</samp></li>

                      </ul> |
| OldStatus | - Type<br>

                        - picklist<br>

                    - Properties<br>

                        - Nillable<br>

                    - Description<br>

                        - The previous value of the Status field on the FulfillmentOrder.<br>

                        - Possible values are defined by the Status field picklist on the
                      FulfillmentOrder object. |
| OldStatusCategory | - Type<br>

                        - picklist<br>

                    - Properties<br>

                        - Nillable, Restricted picklist<br>

                    - Description<br>

                        - The previous value of the StatusCategory field on the FulfillmentOrder.<br>

                        - Possible values are: <ul class="ul bulletList">
                        <li class="li"><samp class="codeph nolang">Activated</samp></li>

                        <li class="li"><samp class="codeph nolang">Cancelled</samp></li>

                        <li class="li"><samp class="codeph nolang">Closed</samp></li>

                        <li class="li"><samp class="codeph nolang">Draft</samp></li>

                        <li class="li"><samp class="codeph nolang">Fulfilling</samp></li>

                      </ul> |
| OrderSummaryId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Nillable<br>

                    - Description<br>

                        - ID of the OrderSummary associated with the FulfillmentOrder. |
| ReplayId | - Type<br>

                        - string<br>

                    - Properties<br>

                        - Nillable<br>

                    - Description<br>

                        - Represents an ID value that is populated by the system
                    and refers to the position of the event in the event stream. Replay ID values
                    aren’t guaranteed to be contiguous for consecutive events. A subscriber can
                    store a replay ID value and use it on resubscription to retrieve missed events
                    that are within the retention window. |