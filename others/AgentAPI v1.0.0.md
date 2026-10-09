- **openapi:** 3.0.0
# info

- **title:** Agent API
- **version:** v1.0.0
- **description:** 
Use Agent API to communicate with AI agents in your org. Get access to your topics and actions in Agentforce by sending messages to AI agents. Create a Salesforce app in your org, generate a token, and then start using the API. To onboard to this API, see [Get Started with the Agent API](/docs/ai/agentforce/guide/agent-api-get-started.html) and [Agent API Examples](/docs/ai/agentforce/guide/agent-api-examples.html).

## Postman Collection

The quickest way to get started with the Agent API is with our [Postman collection](https://www.postman.com/salesforce-developers/salesforce-developers/collection/gwv9bjy/agent-api).

## Endpoints

- [Start a Session](?meta=startSession): Start a session with an agent.
- [Send a Message (sync)](?meta=sendMessage): Send a sync message to the agent on an active session.
- [Send a Message (streaming)](?meta=sendMessageStream): Send a streaming message to the agent on an active session.
- [End a Session](?meta=endSession): End a session.
- [Submit Feedback](?meta=submitFeedback): Submit feedback for a message.


# servers

| url | description |
| --- | --- |
| https://api.salesforce.com/einstein/ai-agent/v1 | Agent API - Production Environment |

# paths

## /agents/{id}/sessions

### post

- **summary:** Start a session
- **description:** Begin an agent session. The endpoint contains the ID of the Salesforce agent. You can find this ID in the URL of the agent details page. When you select the agent from Setup, use the ID at the end of the URL.
- **operationId:** startSession
#### parameters

| in | name | description | required | schema |
| --- | --- | --- | --- | --- |
| path | id | The ID of the Salesforce agent. You can find this ID in the URL of the agent details page. When you select the agent from Setup, use the ID at the end of the URL. | true | [object Object] |
| header | Authorization | Authorization information that contains the JWT. | true | [object Object] |

#### requestBody

- **description:** Request payload to initiate a session.
- **required:** true
##### content

###### application/json

###### schema

- **$ref:** #/components/schemas/StartSessionRequest




#### responses

##### 200

- **$ref:** #/components/responses/StartSessionResponse

##### 400

- **$ref:** #/components/responses/BadRequestError

##### 401

- **$ref:** #/components/responses/UnauthorizedError

##### 403

- **$ref:** #/components/responses/ForbiddenError

##### 404

- **$ref:** #/components/responses/NotFoundError

##### 422

- **$ref:** #/components/responses/RequestProcessingException

##### 423

- **$ref:** #/components/responses/ServerBusyError

##### 429

- **$ref:** #/components/responses/TooManyRequestsError

##### 503

- **$ref:** #/components/responses/ServiceUnavailable

##### default

- **$ref:** #/components/responses/ErrorResponse




## /sessions/{session-id}/messages

### post

- **summary:** Send a message (synchronous)
- **description:** Send a synchronous message to the agent on an active session. The endpoint contains the ID of the active session, which was returned in the response of the Start Session call.
- **operationId:** sendMessage
#### parameters

| in | name | description | required | schema |
| --- | --- | --- | --- | --- |
| path | session-id | The ID of the active session, which is the `sessionId` value returned from the Start Session call. | true | [object Object] |
| header | Authorization | Authorization information that contains the JWT. | true | [object Object] |

#### requestBody

- **description:** Request payload to continue the chat.
- **required:** true
##### content

###### application/json

###### schema

- **$ref:** #/components/schemas/SendMessageRequest




#### responses

##### 200

- **$ref:** #/components/responses/SendMessageSyncResponse

##### 400

- **$ref:** #/components/responses/BadRequestError

##### 401

- **$ref:** #/components/responses/UnauthorizedError

##### 403

- **$ref:** #/components/responses/ForbiddenError

##### 404

- **$ref:** #/components/responses/NotFoundError

##### 422

- **$ref:** #/components/responses/RequestProcessingException

##### 423

- **$ref:** #/components/responses/ServerBusyError

##### 429

- **$ref:** #/components/responses/TooManyRequestsError

##### 503

- **$ref:** #/components/responses/ServiceUnavailable

##### default

- **$ref:** #/components/responses/ErrorResponse




## /sessions/{session-id}/messages/stream

### post

- **summary:** Send a message (streaming)
- **description:** Send a streaming message to the agent on an active session. Returns an SSE stream in the response. The endpoint contains the ID of the active session, which was returned in the response of the Start Session call.
- **operationId:** sendMessageStream
- **x-sse:** true
#### parameters

| in | name | description | required | schema |
| --- | --- | --- | --- | --- |
| path | session-id | The ID of the active session, which is the `sessionId` value returned from the Start Session call. | true | [object Object] |
| header | Authorization | Authorization information that contains the JWT. | true | [object Object] |
| header | Accept | Indicates which content type the sender is able to understand. For this endpoint, specify `text/event-stream`. | true | [object Object] |

#### requestBody

- **description:** Request payload to continue the chat.
- **required:** true
##### content

###### application/json

###### schema

- **$ref:** #/components/schemas/SendMessageRequest




#### responses

##### 200

- **$ref:** #/components/responses/StreamMessageResponse

##### 400

- **$ref:** #/components/responses/BadRequestError

##### 401

- **$ref:** #/components/responses/UnauthorizedError

##### 403

- **$ref:** #/components/responses/ForbiddenError

##### 404

- **$ref:** #/components/responses/NotFoundError

##### 422

- **$ref:** #/components/responses/RequestProcessingException

##### 423

- **$ref:** #/components/responses/ServerBusyError

##### 429

- **$ref:** #/components/responses/TooManyRequestsError

##### 503

- **$ref:** #/components/responses/ServiceUnavailable

##### default

- **$ref:** #/components/responses/ErrorResponse




## /sessions/{session-id}

### delete

- **summary:** End an active session
- **description:** Send a message to the agent to end a session. The endpoint contains the ID of the active session, which was returned in the response of the Start Session call.
- **operationId:** endSession
#### parameters

| in | name | description | required | schema | example | allowEmptyValue |
| --- | --- | --- | --- | --- | --- | --- |
| path | session-id | The ID of the active session, which is the `sessionId` value returned from the Start Session call. | true | [object Object] |  |  |
| header | Authorization | Authorization information that contains the JWT. | true | [object Object] |  |  |
| header | x-session-end-reason | The reason the session ended. | true | [object Object] | UserRequest | false |

#### responses

##### 200

- **$ref:** #/components/responses/SendMessageSyncResponse

##### 400

- **$ref:** #/components/responses/BadRequestError

##### 401

- **$ref:** #/components/responses/UnauthorizedError

##### 403

- **$ref:** #/components/responses/ForbiddenError

##### 404

- **$ref:** #/components/responses/NotFoundError

##### 422

- **$ref:** #/components/responses/RequestProcessingException

##### 423

- **$ref:** #/components/responses/ServerBusyError

##### 429

- **$ref:** #/components/responses/TooManyRequestsError

##### 503

- **$ref:** #/components/responses/ServiceUnavailable

##### default

- **$ref:** #/components/responses/ErrorResponse




## /sessions/{session-id}/feedback

### post

- **summary:** Submit feedback
- **description:** Submit feedback for a message. Feedback data is stored in Data 360.
- **operationId:** submitFeedback
#### parameters

| in | name | description | required | schema |
| --- | --- | --- | --- | --- |
| path | session-id | The ID of the session, which is the `sessionId` value returned from the Start Session call. | true | [object Object] |
| header | Authorization | Authorization information that contains the JWT. | true | [object Object] |

#### requestBody

- **description:** The feedback payload.
- **required:** true
##### content

###### application/json

###### schema

- **$ref:** #/components/schemas/FeedbackMessage




#### responses

##### 202

- **description:** Feedback successfully accepted.

##### 400

- **$ref:** #/components/responses/BadRequestError

##### 401

- **$ref:** #/components/responses/UnauthorizedError

##### 403

- **$ref:** #/components/responses/ForbiddenError

##### 404

- **$ref:** #/components/responses/NotFoundError

##### 422

- **$ref:** #/components/responses/RequestProcessingException

##### 423

- **$ref:** #/components/responses/ServerBusyError

##### 429

- **$ref:** #/components/responses/TooManyRequestsError

##### 503

- **$ref:** #/components/responses/ServiceUnavailable

##### default

- **$ref:** #/components/responses/ErrorResponse





# components

## securitySchemes

### jwtBearer

- **type:** http
- **scheme:** bearer
- **description:** Salesforce OAuth access token obtained using the JWT Bearer flow. To learn more, see [Get Started with the Agent API](/docs/ai/agentforce/guide/agent-api-get-started.html).


## schemas

### ResponseSessionId

- **description:** Agent session ID. Use this value for the session ID when sending messages or ending a session.
- **type:** string
- **example:** 57904eb6-5352-4c5e-adf6-5f100572cf5d
- **nullable:** false

### ExternalSessionKey

- **description:** UUID that you provide for the conversation. You can use this parameter to trace the conversation in your agent's event logs.
- **type:** string
- **example:** 57904eb6-5352-4c5e-adf6-5f100572cf5d
- **nullable:** false

### StartSessionRequest

- **type:** object
#### properties

##### externalSessionKey

- **$ref:** #/components/schemas/ExternalSessionKey

##### instanceConfig

- **$ref:** #/components/schemas/InstanceConfig

##### tz

- **description:** Client timezone where the customer starts the chat. Uses the tz database timezone format. Can be null.
- **type:** string
- **example:** America/Los_Angeles

##### variables

- **$ref:** #/components/schemas/Variables

##### featureSupport

- **deprecated:** true
- **$ref:** #/components/schemas/SessionFeature

##### streamingCapabilities

- **$ref:** #/components/schemas/StreamingCapability

##### bypassUser

- **description:** Indicates whether to use the agent-assigned user instead of the logged in user. If set to `true`, the API uses the user associated with the agent. If set to `false`, the API uses the user associated with the token. Set this value to `true` when using the client credentials flow. Defaults to `false`.
- **type:** boolean
- **example:** true


#### required

- externalSessionKey
- instanceConfig


### SendMessageRequest

- **description:** Represents a send message request.
- **type:** object
#### properties

##### message

- **$ref:** #/components/schemas/AbstractRequestMessage

##### variables

- **$ref:** #/components/schemas/Variables


#### required

- message


### CancelMessage

- **description:** Represents a cancel message request.
#### allOf

| $ref | type | properties |
| --- | --- | --- |
| #/components/schemas/AbstractRequestMessage |  |  |
|  | object | [object Object] |


### ReplyMessage

- **description:** Used when answering a question with a choice of multiple records.
#### allOf

| $ref | type | properties | required |
| --- | --- | --- | --- |
| #/components/schemas/AbstractRequestMessage |  |  |  |
|  | object | [object Object] | reply |


### StartSessionSyncResponseMessage

- **type:** object
#### properties

##### sessionId

- **$ref:** #/components/schemas/ResponseSessionId

##### _links

- **$ref:** #/components/schemas/SyncLinks

##### messages

- **description:** Array of initial messages. Each message can be one of the following response message types: [Inform](?meta=type%3AInformMessage), [TextChunk](?meta=type%3ATextChunkMessage), [ValidationFailureChunk](?meta=type%3AValidationFailureChunkMessage), [ProgressIndicator](?meta=type%3AProgressIndicatorMessage), [Inquire](?meta=type%3AInquireMessage), [Confirm](?meta=type%3AConfirmMessage), [Failure](?meta=type%3AFailureMessage), [Escalate](?meta=type%3AEscalateMessage), [SessionEnded](?meta=type%3ASessionEndedMessage), [EndOfTurn](?meta=type%3AEndOfTurnMessage), [Error](?meta=type%3AErrorMessage).

- **type:** array
- **minimum:** 0
###### items

- **$ref:** #/components/schemas/AbstractResponseMessage



#### required

- sessionId
- _links
- messages


### SendMessagesSyncResponseMessage

- **type:** object
#### properties

##### messages

- **type:** array
- **description:** Array of response messages. Each message can be one of the following response message types: [Inform](?meta=type%3AInformMessage), [TextChunk](?meta=type%3ATextChunkMessage), [ValidationFailureChunk](?meta=type%3AValidationFailureChunkMessage), [ProgressIndicator](?meta=type%3AProgressIndicatorMessage), [Inquire](?meta=type%3AInquireMessage), [Confirm](?meta=type%3AConfirmMessage), [Failure](?meta=type%3AFailureMessage), [Escalate](?meta=type%3AEscalateMessage), [SessionEnded](?meta=type%3ASessionEndedMessage), [EndOfTurn](?meta=type%3AEndOfTurnMessage), [Error](?meta=type%3AErrorMessage).

- **minimum:** 0
###### items

- **$ref:** #/components/schemas/AbstractResponseMessage


##### _links

- **$ref:** #/components/schemas/SyncLinks


#### required

- messages
- _links


### FeedbackMessage

- **type:** object
#### properties

##### feedbackId

- **$ref:** #/components/schemas/FeedbackId

##### feedback

- **$ref:** #/components/schemas/FeedbackRating

##### text

- **type:** string
- **description:** Textual representation of user feedback.
- **example:** Email looks great.

##### details

- **type:** object
- **description:** Additional details to provide as key value pairs.
- **additionalProperties:** true
- **maxProperties:** 10
###### example

- **userId:** uid



#### required

- feedbackId
- feedback


### FeedbackRating

- **type:** string
- **description:** Feedback rating, suggesting a thumbs up or thumbs down.
#### enum

- GOOD
- BAD


### ServerSentEvent

- **description:** Server sent event (SSE) contents.
- **type:** object
#### properties

##### id

- **description:** Event ID.
- **type:** string
- **example:** 1692632086370-0

##### event

- **$ref:** #/components/schemas/EventType

##### retry

- **description:** Reserved for future use.
- **type:** number

##### data

- **description:** Data associated with this event.
###### oneOf

| $ref |
| --- |
| #/components/schemas/CopilotEvent |
| #/components/schemas/ErrorEvent |



#### required

- event
- data


### ErrorEvent

- **$ref:** #/components/schemas/Error

### EventType

- **description:** Type of streaming event. See [Inform](?meta=type%3AInformMessage), [TextChunk](?meta=type%3ATextChunkMessage), [ValidationFailureChunk](?meta=type%3AValidationFailureChunkMessage), [ProgressIndicator](?meta=type%3AProgressIndicatorMessage), [Inquire](?meta=type%3AInquireMessage), [Confirm](?meta=type%3AConfirmMessage), [Failure](?meta=type%3AFailureMessage), [Escalate](?meta=type%3AEscalateMessage), [SessionEnded](?meta=type%3ASessionEndedMessage), [EndOfTurn](?meta=type%3AEndOfTurnMessage), [Error](?meta=type%3AErrorMessage).
- **type:** string
#### enum

- UNKNOWN
- END_OF_TURN
- PROGRESS_INDICATOR
- INFORM
- INQUIRE
- CONFIRM
- FAILURE
- SESSION_ENDED
- ERROR
- ESCALATE
- TEXT_CHUNK


### CopilotEvent

- **description:** Event wrapper.
- **type:** object
#### properties

##### timestamp

- **description:** Event timestamp.
- **type:** number
- **example:** 1716299066

##### originEventId

- **$ref:** #/components/schemas/EventId

##### traceId

- **description:** Event trace ID.
- **type:** string
- **example:** 69feac6d79e075633486f4f722fd97c3

##### offset

- **description:** Event offset.
- **type:** number

##### message

- **$ref:** #/components/schemas/AbstractResponseMessage
- **description:** Response message. Message can be one of the following response message types: [Inform](?meta=type%3AInformMessage), [TextChunk](?meta=type%3ATextChunkMessage), [ValidationFailureChunk](?meta=type%3AValidationFailureChunkMessage), [ProgressIndicator](?meta=type%3AProgressIndicatorMessage), [Inquire](?meta=type%3AInquireMessage), [Confirm](?meta=type%3AConfirmMessage), [Failure](?meta=type%3AFailureMessage), [Escalate](?meta=type%3AEscalateMessage), [SessionEnded](?meta=type%3ASessionEndedMessage), [EndOfTurn](?meta=type%3AEndOfTurnMessage), [Error](?meta=type%3AErrorMessage).




### EndOfTurnMessage

- **description:** Represents the end of the turn.
#### allOf

| $ref |
| --- |
| #/components/schemas/AbstractResponseMessage |


### ProgressIndicatorMessage

- **description:** Represents a progress indicator.
#### allOf

| $ref | type | properties | required |
| --- | --- | --- | --- |
| #/components/schemas/AbstractResponseMessage |  |  |  |
|  | object | [object Object] | indicatorType,message |


### ProgressIndicatorType

- **type:** string
- **description:** Indicates the type of progress indicator.
- **example:** ACTION
#### enum

- ACTION


### PlanTemplateMessage

- **description:** Represents a plan template message.
#### allOf

| $ref | type | description | properties | required |
| --- | --- | --- | --- | --- |
| #/components/schemas/AbstractRequestMessage |  |  |  |  |
|  | object | Represents the type of message to be sent by client when it wants to execute an existing plan. | [object Object] | details |


### AbstractRequestMessage

- **description:** Represents the message to be sent. Can be one of the following request message types: [Text](?meta=type%3ATextMessage), [Reply](?meta=type%3AReplyMessage), [Cancel](?meta=type%3ACancelMessage), [TransferFailed](?meta=type%3ATransferFailedMessage), [TransferSucceeded](?meta=type%3ATransferSucceededMessage), [PlanTemplate](?meta=type%3APlanTemplateMessage).
- **type:** object
#### properties

##### type

- **type:** string
###### enum

- Text
- Reply
- Cancel
- TransferFailed
- TransferSucceeded
- PlanTemplate

- **description:** Request message type. Can be one of the following types: [Text](?meta=type%3ATextMessage), [Reply](?meta=type%3AReplyMessage), [Cancel](?meta=type%3ACancelMessage), [TransferFailed](?meta=type%3ATransferFailedMessage), [TransferSucceeded](?meta=type%3ATransferSucceededMessage), [PlanTemplate](?meta=type%3APlanTemplateMessage).


##### sequenceId

- **$ref:** #/components/schemas/SequenceId


#### required

- type
- sequenceId

#### example

- **type:** Text
- **sequenceId:** 1
- **text:** Can you provide a summary of my orders?


### AbstractResponseMessage

- **type:** object
- **description:** Response message. Message can be one of the following response message types: [Inform](?meta=type%3AInformMessage), [TextChunk](?meta=type%3ATextChunkMessage), [ValidationFailureChunk](?meta=type%3AValidationFailureChunkMessage), [ProgressIndicator](?meta=type%3AProgressIndicatorMessage), [Inquire](?meta=type%3AInquireMessage), [Confirm](?meta=type%3AConfirmMessage), [Failure](?meta=type%3AFailureMessage), [Escalate](?meta=type%3AEscalateMessage), [SessionEnded](?meta=type%3ASessionEndedMessage), [EndOfTurn](?meta=type%3AEndOfTurnMessage), [Error](?meta=type%3AErrorMessage).

#### properties

##### id

- **$ref:** #/components/schemas/MessageId

##### type

- **type:** string
- **description:** Indicates the type of message. Can be one of the following strings: [Inform](?meta=type%3AInformMessage), [TextChunk](?meta=type%3ATextChunkMessage), [ValidationFailureChunk](?meta=type%3AValidationFailureChunkMessage), [ProgressIndicator](?meta=type%3AProgressIndicatorMessage), [Inquire](?meta=type%3AInquireMessage), [Confirm](?meta=type%3AConfirmMessage), [Failure](?meta=type%3AFailureMessage), [Escalate](?meta=type%3AEscalateMessage), [SessionEnded](?meta=type%3ASessionEndedMessage), [EndOfTurn](?meta=type%3AEndOfTurnMessage), [Error](?meta=type%3AErrorMessage).
- **example:** Inform


#### required

- id
- type


### TextChunkMessage

- **description:** Represents a chunk of the text response.
#### allOf

| $ref | type | properties | required |
| --- | --- | --- | --- |
| #/components/schemas/AbstractResponseMessage |  |  |  |
|  | object |  |  |
|  |  | [object Object] | offset,message,formatType |


### TextFormatType

- **type:** string
- **description:** The text format type.
#### enum

- Unknown
- Text


### ValidationFailureChunkMessage

- **description:** Indicates that there was a failure validating the agent's response. If you receive a validation failure chunk, remove all previously rendered chunks and display only the new streamed content.
#### allOf

| $ref | type | properties | required |
| --- | --- | --- | --- |
| #/components/schemas/AbstractResponseMessage |  |  |  |
|  | object |  |  |
|  |  | [object Object] | offset |


### InformMessage

- **description:** Informs caller of response.
#### allOf

| $ref | type | properties | required |
| --- | --- | --- | --- |
| #/components/schemas/AbstractResponseMessage |  |  |  |
|  | object | [object Object] | message,isContentSafe,feedbackId |


### InquireMessage

- **description:** Indicates that more information is required.
#### allOf

| $ref | type | properties | required |
| --- | --- | --- | --- |
| #/components/schemas/AbstractResponseMessage |  |  |  |
|  | object | [object Object] | feedbackId,collect |


### InquireCollectMessage

- **type:** object
- **description:** Inquire type
#### properties

##### targetType

- **$ref:** #/components/schemas/TargetTypeId

##### targetProperty

- **$ref:** #/components/schemas/TargetPropertyId

##### data

- **$ref:** #/components/schemas/SourceTypeMessage


#### required

- targetType


### ConfirmMessage

- **description:** Indicates that the agent is asking the user to verify that an action should be taken.
#### allOf

| $ref | type | properties | required |
| --- | --- | --- | --- |
| #/components/schemas/AbstractResponseMessage |  |  |  |
|  | object | [object Object] | feedbackId,confirm |


### ErrorMessage

- **description:** Indicates there was an error in the response.
#### allOf

| $ref | type | properties | required |
| --- | --- | --- | --- |
| #/components/schemas/AbstractResponseMessage |  |  |  |
|  | object | [object Object] | feedbackId,httpStatus,error,message,expected |


### SessionFeature

- **type:** string
- **description:** Defines how the session supports message processing.
- **example:** Sync
#### enum

- Sync
- Streaming


### ChunkType

- **description:** Defines the types of stream chunks you'd like to receive when streaming.
- **type:** string
#### enum

- Text


### StreamingCapability

- **type:** object
- **description:** Describes the streaming capabilities.
#### properties

##### chunkTypes

- **type:** array
- **description:** Array of chunk types.
- **minimum:** 0
###### items

- **$ref:** #/components/schemas/ChunkType




### RichContentCapability

- **type:** object
#### properties

##### messageTypes

- **type:** array
- **minimum:** 1
###### items

- **$ref:** #/components/schemas/MessageTypeCapability



#### required

- messageTypes


### MessageTypeCapability

- **type:** object
#### properties

##### messageType

- **$ref:** #/components/schemas/MessageType

##### formatTypes

- **type:** array
- **minimum:** 1
###### items

- **$ref:** #/components/schemas/FormatTypeCapability



#### required

- messageType
- formatTypes


### FormatTypeCapability

- **type:** object
#### properties

##### formatType

- **$ref:** #/components/schemas/FormatType


#### required

- formatType


### MessageType

- **description:** Message type that supports rich content output formats.
* `ChoicesMessage`: Represents multiple choice content.

- **type:** string
#### enum

- ChoicesMessage

- **example:** ChoicesMessage

### FormatType

- **type:** string
- **description:** The rendering format of a message. Describes how the message looks.
- **example:** MessageDefinition
#### enum

- MessageDefinition
- Text


### PlanId

- **type:** string
- **description:** Unique ID to identify the plan.
- **example:** 9247bbd8-5ed9-11ee-8c99-0242ac120002

### ContentSafety

- **type:** boolean
- **description:** Indicates whether the content is deemed as safe. A false value doesn't necessarily mean that the content isn't toxic.
- **example:** true

### CitedReference

- **type:** object
#### properties

##### type

- **type:** string
- **description:** Type of citation. This value can be either a CRM record (`record`) or an external link (`link`).
###### enum

- record
- link


##### value

- **type:** string
- **description:** External link address.

##### recordId

- **type:** string
- **description:** Salesforce org record ID.

##### label

- **type:** string
- **description:** UI label for citation.

##### inlineMetadata

- **description:** Inline metadata information used for inline citations.
- **type:** array
###### items

- **$ref:** #/components/schemas/InlineReferenceMetadata



#### required

- type
- value


### InlineReferenceMetadata

- **type:** object
#### properties

##### claim

- **type:** string
- **description:** Text from the agent response relevant to this reference.

##### location

- **type:** integer
- **description:** Index location for where this citation should be placed.


#### required

- claim
- location


### SourceTypeMessage

- **type:** object
- **description:** Bundle for a source type.
#### properties

##### type

- **$ref:** #/components/schemas/SourceTypeId

##### property

- **$ref:** #/components/schemas/SourcePropertyId

##### value

- **$ref:** #/components/schemas/TypeValue


#### required

- type
- value


### SourceTypeId

- **type:** string
- **description:** The action type ID. See [Agent Actions](https://help.salesforce.com/s/articleView?id=ai.copilot_actions.htm).
- **example:** copilotActionOutput/EmployeeCopilot__UpdateRecordFields

### SourcePropertyId

- **type:** string
- **description:** The action property ID. See [Agent Actions](https://help.salesforce.com/s/articleView?id=ai.copilot_actions.htm).
- **example:** result

### TargetTypeId

- **type:** string
- **description:** The action type ID. See [Agent Actions](https://help.salesforce.com/s/articleView?id=ai.copilot_actions.htm).
- **example:** @aiFunctionInput/BookFlight

### TargetTypeMessage

- **type:** object
- **description:** Bundle for a target type.
#### properties

##### type

- **$ref:** #/components/schemas/TargetTypeId

##### property

- **$ref:** #/components/schemas/TargetPropertyId

##### value

- **$ref:** #/components/schemas/TypeValue


#### required

- type
- value


### TargetPropertyId

- **type:** string
- **description:** The action property ID. See [Agent Actions](https://help.salesforce.com/s/articleView?id=ai.copilot_actions.htm).
- **example:** flightInfo

### TypeValue

- **description:** A type value.
- **example:** a free form string or an object or an array

### MessageId

- **description:** UUID that references this message.
- **type:** string
- **example:** a133c185-73a7-4adf-b6d9-b7fd62babb4e

### SequenceId

- **description:** Client-generated sequence number of the message in a session. Increase this number for each subsequent message.
- **type:** number
- **example:** 1

### SyncLinks

- **description:** List of Agentforce endpoints for HATEOS compliance.
- **type:** object
#### properties

##### self

- **$ref:** #/components/schemas/HyperLink

##### messages

- **$ref:** #/components/schemas/HyperLink

##### session

- **$ref:** #/components/schemas/HyperLink

##### end

- **$ref:** #/components/schemas/HyperLink


#### required

- self


### HyperLink

- **description:** Hyperlink object included in the links schema.
- **type:** object
#### properties

##### href

- **description:** Link to the endpoint.
- **type:** string
- **example:** https://api.salesforce.com/sessions



### InReplyToMessageId

- **description:** Message ID of the previous response you are replying to.
- **type:** string
- **example:** a133c185-73a7-4adf-b6d9-b7fd62babb4e

### Variables

- **type:** array
- **description:** Array of custom and context agent variables passed to the agent during a session. See [Agent Variables](https://help.salesforce.com/s/articleView?id=ai.agent_variables.htm). Many variables are read-only and can only be set during the start session call. By default, context variables (which have the `$Context` prefix) aren't editable after the session has started, except for the `$Context.EndUserLanguage` variable. You can only modify editable variables during a send message call. When specifying variables that are derived from custom fields, omit the `__c` suffix. For instance, `Conversation_Key__c` becomes `$Context.Conversation_Key`. This array can be null.
#### items

- **$ref:** #/components/schemas/Variable


### Variable

- **description:** Custom or context variable passed to the agent during a session. See [Agent Variables](https://help.salesforce.com/s/articleView?id=ai.agent_variables.htm). Many variables are read-only and can only be set during the start session call. By default, context variables (which have the `$Context` prefix) aren't editable after the session has started, except for the `$Context.EndUserLanguage` variable. You can only modify editable variables during a send message call. When specifying variables that are derived from custom fields, omit the `__c` suffix. For instance, `Conversation_Key__c` becomes `$Context.Conversation_Key`.
- **type:** object
#### properties

##### name

- **description:** API name for the agent variable.
- **type:** string
- **example:** $Context.EndUserLanguage

##### type

- **description:** Variable type.
- **type:** string
- **example:** Text
###### enum

- Object
- Json
- Boolean
- Date
- DateTime
- Money
- Number
- Text
- Ref
- List


##### value

- **description:** Variable value.
- **type:** string
- **example:** en_US


#### required

- name
- type
- value


### BooleanVariable

#### allOf

| $ref | type | properties | required |
| --- | --- | --- | --- |
| #/components/schemas/Variable |  |  |  |
|  | object | [object Object] | value |


### DateVariable

#### allOf

| $ref | type | properties | required |
| --- | --- | --- | --- |
| #/components/schemas/Variable |  |  |  |
|  | object | [object Object] | value |


### DateTimeVariable

#### allOf

| $ref | type | properties | required |
| --- | --- | --- | --- |
| #/components/schemas/Variable |  |  |  |
|  | object | [object Object] | value |


### MoneyVariable

#### allOf

| $ref | type | properties | required |
| --- | --- | --- | --- |
| #/components/schemas/Variable |  |  |  |
|  | object | [object Object] | value |


### NumberVariable

#### allOf

| $ref | type | properties | required |
| --- | --- | --- | --- |
| #/components/schemas/Variable |  |  |  |
|  | object | [object Object] | value |


### TextVariable

#### allOf

| $ref | type | properties | required |
| --- | --- | --- | --- |
| #/components/schemas/Variable |  |  |  |
|  | object | [object Object] | value |


### ObjectVariable

#### allOf

| $ref | type | properties | required |
| --- | --- | --- | --- |
| #/components/schemas/Variable |  |  |  |
|  | object | [object Object] | value |


### RefVariable

#### allOf

| $ref | type | properties | required |
| --- | --- | --- | --- |
| #/components/schemas/Variable |  |  |  |
|  | object | [object Object] | value |


### ListVariable

#### allOf

| $ref | type | properties | required |
| --- | --- | --- | --- |
| #/components/schemas/Variable |  |  |  |
|  | object | [object Object] | value |


### JsonVariable

#### allOf

| $ref | type | properties | required |
| --- | --- | --- | --- |
| #/components/schemas/Variable |  |  |  |
|  | object | [object Object] | value |


### Referrer

- **type:** object
#### properties

##### type

- **description:** Referrer type.
- **type:** string
###### enum

- Salesforce:Core:Bot:Id
- Salesforce:BotRuntime:Session:Id

- **example:** Salesforce:Core:Bot:Id

##### value

- **type:** string
- **description:** ID of referrer.
- **example:** string


#### required

- type
- value


### TransferFailedMessage

- **description:** Represents a transfer failed message.
#### allOf

| $ref | type | properties | required |
| --- | --- | --- | --- |
| #/components/schemas/AbstractRequestMessage |  |  |  |
|  | object | [object Object] | reason |


### TransferSucceededMessage

- **description:** Represents a transfer succeeded message.
#### allOf

| $ref | type | properties |
| --- | --- | --- |
| #/components/schemas/AbstractRequestMessage |  |  |
|  | object | [object Object] |


### EndSessionReason

- **type:** string
#### enum

- UserRequest
- Transfer
- Expiration
- Error
- Other

- **example:** Transfer
- **nullable:** false

### TextMessage

- **description:** Represents a text request.
#### allOf

| $ref | type | properties | required |
| --- | --- | --- | --- |
| #/components/schemas/AbstractRequestMessage |  |  |  |
|  | object | [object Object] | text |


### SessionEndedMessage

- **description:** Indicates the session has ended.
#### allOf

| $ref | type | properties | required |
| --- | --- | --- | --- |
| #/components/schemas/AbstractResponseMessage |  |  |  |
|  | object | [object Object] | reason |


### FailureMessage

- **description:** Indicates that something didn't execute properly.
#### allOf

| $ref | type | properties | required |
| --- | --- | --- | --- |
| #/components/schemas/AbstractResponseMessage |  |  |  |
|  | object | [object Object] | feedbackId,code |


### EscalateMessage

- **description:** Indicates that a human rep should handle this request. The escalation message is automatically translated based on the end user's language setting. If the language isn't supported, the original message is returned without translation.
#### allOf

| $ref | type | properties | required |
| --- | --- | --- | --- |
| #/components/schemas/AbstractResponseMessage |  |  |  |
|  | object | [object Object] | feedbackId,targets |


### InstanceConfig

- **type:** object
- **description:** API configuration parameters.
#### properties

##### endpoint

- **description:** My Domain URL for your Salesforce org. From Setup, search for My Domain. Copy the value shown in the Current My Domain URL field. See [Get Started with Agent API](/docs/ai/agentforce/guide/agent-api-get-started.html).
- **type:** string
- **example:** https://d5e000009s7bceah-dev-ed.my.salesforce.com/


#### required

- endpoint


### FeedbackId

- **type:** string
- **description:** Unique ID to identify the generation. Used to submit feedback.
- **example:** 9247bbd8-5ed9-11ee-8c99-0242ac120002

### EventId

- **type:** string
- **description:** Unique ID to identify the event.
- **example:** auMZc8ZRv37sIW2iJKq3M9MFx1YvV11A2x

### Status

- **type:** object
#### properties

##### status

- **type:** string
- **description:** Health status of Agent API.
###### enum

- UP
- DOWN

- **example:** UP


#### required

- status


### Error

- **type:** object
#### properties

##### status

- **description:** HTTP status.
- **type:** integer
- **format:** int32

##### path

- **description:** Request path.
- **type:** string

##### requestId

- **description:** Request ID. A UUID in string format to help with request tracking.
- **type:** string

##### error

- **description:** Error class name.
- **type:** string

##### message

- **description:** Exception message.
- **type:** string

##### timestamp

- **description:** Unix timestamp.
- **type:** number


#### required

- status
- path
- requestId
- error
- message
- timestamp

#### example

- **status:** 500
- **path:** /agents/00DRM00000067To/messages
- **requestId:** 19c056ab-d909-49df-b976-65e56b6ab214
- **error:** InactiveConfigException
- **message:** Config is not active
- **timestamp:** 1531245973799



## responses

### StatusResponse

- **description:** OK
#### content

##### application/json

###### schema

- **$ref:** #/components/schemas/Status




### ErrorResponse

- **description:** Something went wrong
#### content

##### application/json

###### schema

- **$ref:** #/components/schemas/Error



#### headers

##### X-Request-ID

- **description:** Request ID. A UUID in string format to help with request tracking.
- **example:** 36a73651-a46d-4d16-9a8a-fd436ed62e1a
###### schema

- **type:** string




### StartSessionResponse

- **description:** Response to a new session.
#### content

##### application/json

###### schema

- **$ref:** #/components/schemas/StartSessionSyncResponseMessage



#### headers

##### x-session-mode

- **description:** Agent session mode.
- **example:** default
###### schema

- **type:** string




### SendMessageSyncResponse

- **description:** Batched Response (Headless)
#### content

##### application/json

###### schema

- **$ref:** #/components/schemas/SendMessagesSyncResponseMessage




### StreamMessageResponse

- **description:** OK
#### content

##### text/event-stream

###### schema

- **$ref:** #/components/schemas/ServerSentEvent




### BadRequestError

- **description:** Bad Request
#### content

##### application/json

###### schema

- **$ref:** #/components/schemas/Error

###### example

- **status:** 400
- **path:** /v6/00DRM00000067To/sessions/HelloWorldBot/messages
- **requestId:** 19c056ab-d909-49df-b976-65e56b6ab214
- **error:** BadRequestError
- **message:** Bad Request
- **timestamp:** 1531245973799



#### headers

##### X-Request-ID

- **description:** Request ID. A UUID in string format to help with request tracking.
- **example:** 36a73651-a46d-4d16-9a8a-fd436ed62e1a
###### schema

- **type:** string




### UnauthorizedError

- **description:** Access bearer token is missing or invalid
#### content

##### application/json

###### schema

- **$ref:** #/components/schemas/Error

###### example

- **status:** 401
- **path:** /v1/00DRM00000067To/chatbots/HelloWorldBot/messages
- **requestId:** 19c056ab-d909-49df-b976-65e56b6ab214
- **error:** UnauthorizedError
- **message:** Access bearer token is missing or invalid
- **timestamp:** 1531245973799



#### headers

##### X-Request-ID

- **description:** Request ID. A UUID in string format to help with request tracking.
- **example:** 36a73651-a46d-4d16-9a8a-fd436ed62e1a
###### schema

- **type:** string




### ForbiddenError

- **description:** User forbidden from accessing the resource
#### content

##### application/json

###### schema

- **$ref:** #/components/schemas/Error

###### example

- **status:** 403
- **path:** /v1/00DRM00000067To/chatbots/HelloWorldBot/messages
- **requestId:** 19c056ab-d909-49df-b976-65e56b6ab214
- **error:** ForbiddenError
- **message:** User forbidden from accessing the resource
- **timestamp:** 1531245973799



#### headers

##### X-Request-ID

- **description:** Request ID. A UUID in string format to help with request tracking.
- **example:** 36a73651-a46d-4d16-9a8a-fd436ed62e1a
###### schema

- **type:** string




### NotFoundError

- **description:** Resource not found
#### content

##### application/json

###### schema

- **$ref:** #/components/schemas/Error

###### example

- **status:** 404
- **path:** /v1/00DRM00000067To/chatbots/HelloWorldBot/messages
- **requestId:** 19c056ab-d909-49df-b976-65e56b6ab214
- **error:** NotFoundError
- **message:** Resource not found
- **timestamp:** 1531245973799



#### headers

##### X-Request-ID

- **description:** Request ID. A UUID in string format to help with request tracking.
- **example:** 36a73651-a46d-4d16-9a8a-fd436ed62e1a
###### schema

- **type:** string




### NotAvailableError

- **description:** Resource not available at the time of the request
#### content

##### application/json

###### schema

- **$ref:** #/components/schemas/Error

###### example

- **status:** 410
- **path:** /v1/00DRM00000067To/chatbots/HelloWorldBot/messages
- **requestId:** 19c056ab-d909-49df-b976-65e56b6ab214
- **error:** NotAvailableError
- **message:** Resource not available at the time of the request
- **timestamp:** 1531245973799



#### headers

##### X-Request-ID

- **description:** Request ID. A UUID in string format to help with request tracking.
- **example:** 36a73651-a46d-4d16-9a8a-fd436ed62e1a
###### schema

- **type:** string




### RequestProcessingException

- **description:** Any exception that occurred during the request execution
#### content

##### application/json

###### schema

- **$ref:** #/components/schemas/Error

###### example

- **status:** 422
- **path:** v4.0.0/messages
- **requestId:** 19c056ab-d909-49df-b976-65e56b6ab214
- **error:** RequestProcessingException
- **message:** Cannot determine the active version for the agent
- **timestamp:** 1531245973799



#### headers

##### X-Request-ID

- **description:** Request ID. A UUID in string format to help with request tracking.
- **example:** 36a73651-a46d-4d16-9a8a-fd436ed62e1a
###### schema

- **type:** string




### ServerBusyError

- **description:** Server is busy and cannot process the request at this time
#### content

##### application/json

###### schema

- **$ref:** #/components/schemas/Error

###### example

- **status:** 423
- **path:** /v1/00DRM00000067To/chatbots/HelloWorldBot/messages
- **requestId:** 19c056ab-d909-49df-b976-65e56b6ab214
- **error:** ServerBusyError
- **message:** Server is busy and cannot process the request at this time
- **timestamp:** 1531245973799



#### headers

##### X-Request-ID

- **description:** Request ID. A UUID in string format to help with request tracking.
- **example:** 36a73651-a46d-4d16-9a8a-fd436ed62e1a
###### schema

- **type:** string




### TooManyRequestsError

- **description:** Too many requests for the server to handle
#### content

##### application/json

###### schema

- **$ref:** #/components/schemas/Error

###### example

- **status:** 429
- **path:** /v1/00DRM00000067To/chatbots/HelloWorldBot/messages
- **requestId:** 19c056ab-d909-49df-b976-65e56b6ab214
- **error:** TooManyRequestsError
- **message:** Too many requests for the server to handle
- **timestamp:** 1531245973799



#### headers

##### X-Request-ID

- **description:** Request ID. A UUID in string format to help with request tracking.
- **example:** 36a73651-a46d-4d16-9a8a-fd436ed62e1a
###### schema

- **type:** string




### ServiceUnavailable

- **description:** Service is unavailable possibly because Apex or Flow calls timed out
#### content

##### application/json

###### schema

- **$ref:** #/components/schemas/Error

###### example

- **status:** 503
- **path:** /v1/00DRM00000067To/chatbots/HelloWorldBot/messages
- **requestId:** 19c056ab-d909-49df-b976-65e56b6ab214
- **error:** ServiceUnavailable
- **message:** Service is unavailable possibly because Apex/Flow calls timed out
- **timestamp:** 1531245973799



#### headers

##### X-Request-ID

- **description:** Request ID. A UUID in string format to help with request tracking.
- **example:** 36a73651-a46d-4d16-9a8a-fd436ed62e1a
###### schema

- **type:** string
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjg3OTk0MDE5XX0=
-->