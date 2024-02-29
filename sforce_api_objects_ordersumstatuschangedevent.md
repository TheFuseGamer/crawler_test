# OrderSumStatusChangedEvent

    Notifies subscribers of changes to the status of an order summary record. Use
      this event to trigger flows and processes in your order workflow. This object is
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

<samp class="codeph nolang">/event/OrderSumStatusChangedEvent</samp>

## Special Access Rules

OrderSumStatusChangedEvent is available as part of Salesforce Order Management.

## Fields

| Field | Details |
| --- | --- |
| NewStatus | - Type<br>

                        - picklist<br>

                    - Properties<br>

                        - Defaulted on create<br>

                    - Description<br>

                        - Required. The new value of the Status field on the OrderSummary.<br>

                        - Possible values are based on the OrderSummary statuses defined in your
                      org. |
| OldStatus | - Type<br>

                        - picklist<br>

                    - Properties<br>

                        - Defaulted on create<br>

                    - Description<br>

                        - Required. The previous value of the Status field on the OrderSummary.<br>

                        - Possible values are based on the OrderSummary statuses defined in your
                      org. |
| OrderId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Nillable<br>

                    - Description<br>

                        - ID of the original order associated with the OrderSummary. |
| OrderSummaryId | - Type<br>

                        - reference<br>

                    - Properties<br>

                        - Nillable<br>

                    - Description<br>

                        - The ID of the OrderSummary that changed.<br>

                        - This value is functionally required, but is nillable because order summary
                      records can be deleted to comply with data protection and privacy
                      requirements. |
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