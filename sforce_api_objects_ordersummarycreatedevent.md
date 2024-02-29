# OrderSummaryCreatedEvent

    Notifies subscribers of the creation of an order summary record. Use this event
      to trigger flows and processes in your order workflow. This object is available in API
    version 48.0 and later.

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

<samp class="codeph nolang">/event/OrderSummaryCreatedEvent</samp>

## Special Access Rules

OrderSummaryCreatedEvent is available as part of Salesforce Order Management.

## Fields

| Field | Details |
| --- | --- |
| OrderId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Nillable<br>

                    - Description<br>

                        - ID of the original order associated with the created OrderSummary. |
| OrderSummaryId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Nillable<br>

                    - Description<br>

                        - ID of the created OrderSummary |
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