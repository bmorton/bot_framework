# bot_framework

BotFramework - the Ruby gem for the Microsoft Bot Connector API - v3.0

The Bot Connector REST API allows your bot to send and receive messages to channels configured in the  [Bot Framework Developer Portal](https://dev.botframework.com). The Connector service uses industry-standard REST  and JSON over HTTPS.    Client libraries for this REST API are available. See below for a list.    Many bots will use both the Bot Connector REST API and the associated [Bot State REST API](/en-us/restapi/state). The  Bot State REST API allows a bot to store and retrieve state associated with users and conversations.    Authentication for both the Bot Connector and Bot State REST APIs is accomplished with JWT Bearer tokens, and is  described in detail in the [Connector Authentication](/en-us/restapi/authentication) document.    # Client Libraries for the Bot Connector REST API    * [Bot Builder for C#](/en-us/csharp/builder/sdkreference/)  * [Bot Builder for Node.js](/en-us/node/builder/overview/)  * Generate your own from the [Connector API Swagger file](https://raw.githubusercontent.com/Microsoft/BotBuilder/master/CSharp/Library/Microsoft.Bot.Connector.Shared/Swagger/ConnectorAPI.json)    © 2016 Microsoft

This SDK is automatically generated by the [Swagger Codegen](https://github.com/swagger-api/swagger-codegen) project:

- API version: v3
- Package version: 1.0.0
- Build package: io.swagger.codegen.v3.generators.ruby.RubyClientCodegen
For more information, please visit [https://botframework.com](https://botframework.com)

## Installation

### Build a gem

To build the Ruby code into a gem:

```shell
gem build bot_framework.gemspec
```

Then either install the gem locally:

```shell
gem install ./bot_framework-1.0.0.gem
```
(for development, run `gem install --dev ./bot_framework-1.0.0.gem` to install the development dependencies)

or publish the gem to a gem hosting service, e.g. [RubyGems](https://rubygems.org/).

Finally add this to the Gemfile:

    gem 'bot_framework', '~> 1.0.0'

### Install from Git

If the Ruby gem is hosted at a git repository: https://github.com/GIT_USER_ID/GIT_REPO_ID, then add the following in the Gemfile:

    gem 'bot_framework', :git => 'https://github.com/GIT_USER_ID/GIT_REPO_ID.git'

### Include the Ruby code directly

Include the Ruby code directly using `-I` as follows:

```shell
ruby -Ilib script.rb
```

## Getting Started

Please follow the [installation](#installation) procedure and then run the following code:
```ruby
# Load the gem
require 'bot_framework'

api_instance = BotFramework::AttachmentsApi.new
attachment_id = 'attachment_id_example' # String | attachment id
view_id = 'view_id_example' # String | View id from attachmentInfo


begin
  #GetAttachment
  result = api_instance.attachments_get_attachment(attachment_id, view_id)
  p result
rescue BotFramework::ApiError => e
  puts "Exception when calling AttachmentsApi->attachments_get_attachment: #{e}"
end

api_instance = BotFramework::AttachmentsApi.new
attachment_id = 'attachment_id_example' # String | attachment id


begin
  #GetAttachmentInfo
  result = api_instance.attachments_get_attachment_info(attachment_id)
  p result
rescue BotFramework::ApiError => e
  puts "Exception when calling AttachmentsApi->attachments_get_attachment_info: #{e}"
end

api_instance = BotFramework::ConversationsApi.new
body = BotFramework::ConversationParameters.new # ConversationParameters | Parameters to create the conversation from
is_group = true # BOOLEAN | 
bot = BotFramework::ChannelAccount.new # ChannelAccount | 
members = [BotFramework::ChannelAccount.new] # Array<ChannelAccount> | 
topic_name = 'topic_name_example' # String | 
tenant_id = 'tenant_id_example' # String | 
activity = BotFramework::Activity.new # Activity | 
channel_data = nil # Object | 


begin
  #CreateConversation
  result = api_instance.conversations_create_conversation(body, is_group, bot, members, topic_name, tenant_id, activity, channel_data)
  p result
rescue BotFramework::ApiError => e
  puts "Exception when calling ConversationsApi->conversations_create_conversation: #{e}"
end

api_instance = BotFramework::ConversationsApi.new
conversation_id = 'conversation_id_example' # String | Conversation ID
activity_id = 'activity_id_example' # String | activityId to delete


begin
  #DeleteActivity
  api_instance.conversations_delete_activity(conversation_id, activity_id)
rescue BotFramework::ApiError => e
  puts "Exception when calling ConversationsApi->conversations_delete_activity: #{e}"
end

api_instance = BotFramework::ConversationsApi.new
conversation_id = 'conversation_id_example' # String | Conversation ID
member_id = 'member_id_example' # String | ID of the member to delete from this conversation


begin
  #DeleteConversationMember
  api_instance.conversations_delete_conversation_member(conversation_id, member_id)
rescue BotFramework::ApiError => e
  puts "Exception when calling ConversationsApi->conversations_delete_conversation_member: #{e}"
end

api_instance = BotFramework::ConversationsApi.new
conversation_id = 'conversation_id_example' # String | Conversation ID
activity_id = 'activity_id_example' # String | Activity ID


begin
  #GetActivityMembers
  result = api_instance.conversations_get_activity_members(conversation_id, activity_id)
  p result
rescue BotFramework::ApiError => e
  puts "Exception when calling ConversationsApi->conversations_get_activity_members: #{e}"
end

api_instance = BotFramework::ConversationsApi.new
conversation_id = 'conversation_id_example' # String | Conversation ID


begin
  #GetConversationMembers
  result = api_instance.conversations_get_conversation_members(conversation_id)
  p result
rescue BotFramework::ApiError => e
  puts "Exception when calling ConversationsApi->conversations_get_conversation_members: #{e}"
end

api_instance = BotFramework::ConversationsApi.new
conversation_id = 'conversation_id_example' # String | Conversation ID
opts = { 
  page_size: 56, # Integer | Suggested page size
  continuation_token: 'continuation_token_example' # String | Continuation Token
}

begin
  #GetConversationPagedMembers
  result = api_instance.conversations_get_conversation_paged_members(conversation_id, opts)
  p result
rescue BotFramework::ApiError => e
  puts "Exception when calling ConversationsApi->conversations_get_conversation_paged_members: #{e}"
end

api_instance = BotFramework::ConversationsApi.new
opts = { 
  continuation_token: 'continuation_token_example' # String | skip or continuation token
}

begin
  #GetConversations
  result = api_instance.conversations_get_conversations(opts)
  p result
rescue BotFramework::ApiError => e
  puts "Exception when calling ConversationsApi->conversations_get_conversations: #{e}"
end

api_instance = BotFramework::ConversationsApi.new
body = BotFramework::Activity.new # Activity | Activity to send
type = BotFramework::ActivityTypes.new # ActivityTypes | 
id = 'id_example' # String | 
timestamp = DateTime.parse('2013-10-20T19:20:30+01:00') # DateTime | 
local_timestamp = DateTime.parse('2013-10-20T19:20:30+01:00') # DateTime | 
local_timezone = 'local_timezone_example' # String | 
caller_id = 'caller_id_example' # String | 
service_url = 'service_url_example' # String | 
channel_id = 'channel_id_example' # String | 
from = BotFramework::ChannelAccount.new # ChannelAccount | 
conversation = BotFramework::ConversationAccount.new # ConversationAccount | 
recipient = BotFramework::ChannelAccount.new # ChannelAccount | 
text_format = BotFramework::TextFormatTypes.new # TextFormatTypes | 
attachment_layout = BotFramework::AttachmentLayoutTypes.new # AttachmentLayoutTypes | 
members_added = [BotFramework::ChannelAccount.new] # Array<ChannelAccount> | 
members_removed = [BotFramework::ChannelAccount.new] # Array<ChannelAccount> | 
reactions_added = [BotFramework::MessageReaction.new] # Array<MessageReaction> | 
reactions_removed = [BotFramework::MessageReaction.new] # Array<MessageReaction> | 
topic_name = 'topic_name_example' # String | 
history_disclosed = true # BOOLEAN | 
locale = 'locale_example' # String | 
text = 'text_example' # String | 
speak = 'speak_example' # String | 
input_hint = BotFramework::InputHints.new # InputHints | 
summary = 'summary_example' # String | 
suggested_actions = BotFramework::SuggestedActions.new # SuggestedActions | 
attachments = [BotFramework::Attachment.new] # Array<Attachment> | 
entities = [BotFramework::Entity.new] # Array<Entity> | 
channel_data = nil # Object | 
action = 'action_example' # String | 
reply_to_id = 'reply_to_id_example' # String | 
label = 'label_example' # String | 
value_type = 'value_type_example' # String | 
value = nil # Object | 
name = 'name_example' # String | 
relates_to = BotFramework::ConversationReference.new # ConversationReference | 
code = BotFramework::EndOfConversationCodes.new # EndOfConversationCodes | 
expiration = DateTime.parse('2013-10-20T19:20:30+01:00') # DateTime | 
importance = BotFramework::ActivityImportance.new # ActivityImportance | 
delivery_mode = BotFramework::DeliveryModes.new # DeliveryModes | 
listen_for = ['listen_for_example'] # Array<String> | 
text_highlights = [BotFramework::TextHighlight.new] # Array<TextHighlight> | 
semantic_action = BotFramework::SemanticAction.new # SemanticAction | 
conversation_id = 'conversation_id_example' # String | Conversation ID
activity_id = 'activity_id_example' # String | activityId the reply is to (OPTIONAL)


begin
  #ReplyToActivity
  result = api_instance.conversations_reply_to_activity(body, type, id, timestamp, local_timestamp, local_timezone, caller_id, service_url, channel_id, from, conversation, recipient, text_format, attachment_layout, members_added, members_removed, reactions_added, reactions_removed, topic_name, history_disclosed, locale, text, speak, input_hint, summary, suggested_actions, attachments, entities, channel_data, action, reply_to_id, label, value_type, value, name, relates_to, code, expiration, importance, delivery_mode, listen_for, text_highlights, semantic_action, conversation_id, activity_id)
  p result
rescue BotFramework::ApiError => e
  puts "Exception when calling ConversationsApi->conversations_reply_to_activity: #{e}"
end

api_instance = BotFramework::ConversationsApi.new
body = BotFramework::Transcript.new # Transcript | Historic activities
activities = [BotFramework::Activity.new] # Array<Activity> | 
conversation_id = 'conversation_id_example' # String | Conversation ID


begin
  #SendConversationHistory
  result = api_instance.conversations_send_conversation_history(body, activities, conversation_id)
  p result
rescue BotFramework::ApiError => e
  puts "Exception when calling ConversationsApi->conversations_send_conversation_history: #{e}"
end

api_instance = BotFramework::ConversationsApi.new
body = BotFramework::Activity.new # Activity | Activity to send
type = BotFramework::ActivityTypes.new # ActivityTypes | 
id = 'id_example' # String | 
timestamp = DateTime.parse('2013-10-20T19:20:30+01:00') # DateTime | 
local_timestamp = DateTime.parse('2013-10-20T19:20:30+01:00') # DateTime | 
local_timezone = 'local_timezone_example' # String | 
caller_id = 'caller_id_example' # String | 
service_url = 'service_url_example' # String | 
channel_id = 'channel_id_example' # String | 
from = BotFramework::ChannelAccount.new # ChannelAccount | 
conversation = BotFramework::ConversationAccount.new # ConversationAccount | 
recipient = BotFramework::ChannelAccount.new # ChannelAccount | 
text_format = BotFramework::TextFormatTypes.new # TextFormatTypes | 
attachment_layout = BotFramework::AttachmentLayoutTypes.new # AttachmentLayoutTypes | 
members_added = [BotFramework::ChannelAccount.new] # Array<ChannelAccount> | 
members_removed = [BotFramework::ChannelAccount.new] # Array<ChannelAccount> | 
reactions_added = [BotFramework::MessageReaction.new] # Array<MessageReaction> | 
reactions_removed = [BotFramework::MessageReaction.new] # Array<MessageReaction> | 
topic_name = 'topic_name_example' # String | 
history_disclosed = true # BOOLEAN | 
locale = 'locale_example' # String | 
text = 'text_example' # String | 
speak = 'speak_example' # String | 
input_hint = BotFramework::InputHints.new # InputHints | 
summary = 'summary_example' # String | 
suggested_actions = BotFramework::SuggestedActions.new # SuggestedActions | 
attachments = [BotFramework::Attachment.new] # Array<Attachment> | 
entities = [BotFramework::Entity.new] # Array<Entity> | 
channel_data = nil # Object | 
action = 'action_example' # String | 
reply_to_id = 'reply_to_id_example' # String | 
label = 'label_example' # String | 
value_type = 'value_type_example' # String | 
value = nil # Object | 
name = 'name_example' # String | 
relates_to = BotFramework::ConversationReference.new # ConversationReference | 
code = BotFramework::EndOfConversationCodes.new # EndOfConversationCodes | 
expiration = DateTime.parse('2013-10-20T19:20:30+01:00') # DateTime | 
importance = BotFramework::ActivityImportance.new # ActivityImportance | 
delivery_mode = BotFramework::DeliveryModes.new # DeliveryModes | 
listen_for = ['listen_for_example'] # Array<String> | 
text_highlights = [BotFramework::TextHighlight.new] # Array<TextHighlight> | 
semantic_action = BotFramework::SemanticAction.new # SemanticAction | 
conversation_id = 'conversation_id_example' # String | Conversation ID


begin
  #SendToConversation
  result = api_instance.conversations_send_to_conversation(body, type, id, timestamp, local_timestamp, local_timezone, caller_id, service_url, channel_id, from, conversation, recipient, text_format, attachment_layout, members_added, members_removed, reactions_added, reactions_removed, topic_name, history_disclosed, locale, text, speak, input_hint, summary, suggested_actions, attachments, entities, channel_data, action, reply_to_id, label, value_type, value, name, relates_to, code, expiration, importance, delivery_mode, listen_for, text_highlights, semantic_action, conversation_id)
  p result
rescue BotFramework::ApiError => e
  puts "Exception when calling ConversationsApi->conversations_send_to_conversation: #{e}"
end

api_instance = BotFramework::ConversationsApi.new
body = BotFramework::Activity.new # Activity | replacement Activity
type = BotFramework::ActivityTypes.new # ActivityTypes | 
id = 'id_example' # String | 
timestamp = DateTime.parse('2013-10-20T19:20:30+01:00') # DateTime | 
local_timestamp = DateTime.parse('2013-10-20T19:20:30+01:00') # DateTime | 
local_timezone = 'local_timezone_example' # String | 
caller_id = 'caller_id_example' # String | 
service_url = 'service_url_example' # String | 
channel_id = 'channel_id_example' # String | 
from = BotFramework::ChannelAccount.new # ChannelAccount | 
conversation = BotFramework::ConversationAccount.new # ConversationAccount | 
recipient = BotFramework::ChannelAccount.new # ChannelAccount | 
text_format = BotFramework::TextFormatTypes.new # TextFormatTypes | 
attachment_layout = BotFramework::AttachmentLayoutTypes.new # AttachmentLayoutTypes | 
members_added = [BotFramework::ChannelAccount.new] # Array<ChannelAccount> | 
members_removed = [BotFramework::ChannelAccount.new] # Array<ChannelAccount> | 
reactions_added = [BotFramework::MessageReaction.new] # Array<MessageReaction> | 
reactions_removed = [BotFramework::MessageReaction.new] # Array<MessageReaction> | 
topic_name = 'topic_name_example' # String | 
history_disclosed = true # BOOLEAN | 
locale = 'locale_example' # String | 
text = 'text_example' # String | 
speak = 'speak_example' # String | 
input_hint = BotFramework::InputHints.new # InputHints | 
summary = 'summary_example' # String | 
suggested_actions = BotFramework::SuggestedActions.new # SuggestedActions | 
attachments = [BotFramework::Attachment.new] # Array<Attachment> | 
entities = [BotFramework::Entity.new] # Array<Entity> | 
channel_data = nil # Object | 
action = 'action_example' # String | 
reply_to_id = 'reply_to_id_example' # String | 
label = 'label_example' # String | 
value_type = 'value_type_example' # String | 
value = nil # Object | 
name = 'name_example' # String | 
relates_to = BotFramework::ConversationReference.new # ConversationReference | 
code = BotFramework::EndOfConversationCodes.new # EndOfConversationCodes | 
expiration = DateTime.parse('2013-10-20T19:20:30+01:00') # DateTime | 
importance = BotFramework::ActivityImportance.new # ActivityImportance | 
delivery_mode = BotFramework::DeliveryModes.new # DeliveryModes | 
listen_for = ['listen_for_example'] # Array<String> | 
text_highlights = [BotFramework::TextHighlight.new] # Array<TextHighlight> | 
semantic_action = BotFramework::SemanticAction.new # SemanticAction | 
conversation_id = 'conversation_id_example' # String | Conversation ID
activity_id = 'activity_id_example' # String | activityId to update


begin
  #UpdateActivity
  result = api_instance.conversations_update_activity(body, type, id, timestamp, local_timestamp, local_timezone, caller_id, service_url, channel_id, from, conversation, recipient, text_format, attachment_layout, members_added, members_removed, reactions_added, reactions_removed, topic_name, history_disclosed, locale, text, speak, input_hint, summary, suggested_actions, attachments, entities, channel_data, action, reply_to_id, label, value_type, value, name, relates_to, code, expiration, importance, delivery_mode, listen_for, text_highlights, semantic_action, conversation_id, activity_id)
  p result
rescue BotFramework::ApiError => e
  puts "Exception when calling ConversationsApi->conversations_update_activity: #{e}"
end

api_instance = BotFramework::ConversationsApi.new
body = BotFramework::AttachmentData.new # AttachmentData | Attachment data
type = 'type_example' # String | 
name = 'name_example' # String | 
original_base64 = 'B' # String | 
thumbnail_base64 = 'B' # String | 
conversation_id = 'conversation_id_example' # String | Conversation ID


begin
  #UploadAttachment
  result = api_instance.conversations_upload_attachment(body, type, name, original_base64, thumbnail_base64, conversation_id)
  p result
rescue BotFramework::ApiError => e
  puts "Exception when calling ConversationsApi->conversations_upload_attachment: #{e}"
end
```

## Documentation for API Endpoints

All URIs are relative to *https://api.botframework.com/*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*BotFramework::AttachmentsApi* | [**attachments_get_attachment**](docs/AttachmentsApi.md#attachments_get_attachment) | **GET** /v3/attachments/{attachmentId}/views/{viewId} | GetAttachment
*BotFramework::AttachmentsApi* | [**attachments_get_attachment_info**](docs/AttachmentsApi.md#attachments_get_attachment_info) | **GET** /v3/attachments/{attachmentId} | GetAttachmentInfo
*BotFramework::ConversationsApi* | [**conversations_create_conversation**](docs/ConversationsApi.md#conversations_create_conversation) | **POST** /v3/conversations | CreateConversation
*BotFramework::ConversationsApi* | [**conversations_delete_activity**](docs/ConversationsApi.md#conversations_delete_activity) | **DELETE** /v3/conversations/{conversationId}/activities/{activityId} | DeleteActivity
*BotFramework::ConversationsApi* | [**conversations_delete_conversation_member**](docs/ConversationsApi.md#conversations_delete_conversation_member) | **DELETE** /v3/conversations/{conversationId}/members/{memberId} | DeleteConversationMember
*BotFramework::ConversationsApi* | [**conversations_get_activity_members**](docs/ConversationsApi.md#conversations_get_activity_members) | **GET** /v3/conversations/{conversationId}/activities/{activityId}/members | GetActivityMembers
*BotFramework::ConversationsApi* | [**conversations_get_conversation_members**](docs/ConversationsApi.md#conversations_get_conversation_members) | **GET** /v3/conversations/{conversationId}/members | GetConversationMembers
*BotFramework::ConversationsApi* | [**conversations_get_conversation_paged_members**](docs/ConversationsApi.md#conversations_get_conversation_paged_members) | **GET** /v3/conversations/{conversationId}/pagedmembers | GetConversationPagedMembers
*BotFramework::ConversationsApi* | [**conversations_get_conversations**](docs/ConversationsApi.md#conversations_get_conversations) | **GET** /v3/conversations | GetConversations
*BotFramework::ConversationsApi* | [**conversations_reply_to_activity**](docs/ConversationsApi.md#conversations_reply_to_activity) | **POST** /v3/conversations/{conversationId}/activities/{activityId} | ReplyToActivity
*BotFramework::ConversationsApi* | [**conversations_send_conversation_history**](docs/ConversationsApi.md#conversations_send_conversation_history) | **POST** /v3/conversations/{conversationId}/activities/history | SendConversationHistory
*BotFramework::ConversationsApi* | [**conversations_send_to_conversation**](docs/ConversationsApi.md#conversations_send_to_conversation) | **POST** /v3/conversations/{conversationId}/activities | SendToConversation
*BotFramework::ConversationsApi* | [**conversations_update_activity**](docs/ConversationsApi.md#conversations_update_activity) | **PUT** /v3/conversations/{conversationId}/activities/{activityId} | UpdateActivity
*BotFramework::ConversationsApi* | [**conversations_upload_attachment**](docs/ConversationsApi.md#conversations_upload_attachment) | **POST** /v3/conversations/{conversationId}/attachments | UploadAttachment

## Documentation for Models

 - [BotFramework::ActionTypes](docs/ActionTypes.md)
 - [BotFramework::Activity](docs/Activity.md)
 - [BotFramework::ActivityImportance](docs/ActivityImportance.md)
 - [BotFramework::ActivityTypes](docs/ActivityTypes.md)
 - [BotFramework::AnimationCard](docs/AnimationCard.md)
 - [BotFramework::Attachment](docs/Attachment.md)
 - [BotFramework::AttachmentData](docs/AttachmentData.md)
 - [BotFramework::AttachmentInfo](docs/AttachmentInfo.md)
 - [BotFramework::AttachmentLayoutTypes](docs/AttachmentLayoutTypes.md)
 - [BotFramework::AttachmentView](docs/AttachmentView.md)
 - [BotFramework::AudioCard](docs/AudioCard.md)
 - [BotFramework::BasicCard](docs/BasicCard.md)
 - [BotFramework::CardAction](docs/CardAction.md)
 - [BotFramework::CardImage](docs/CardImage.md)
 - [BotFramework::ChannelAccount](docs/ChannelAccount.md)
 - [BotFramework::ContactRelationUpdateActionTypes](docs/ContactRelationUpdateActionTypes.md)
 - [BotFramework::ConversationAccount](docs/ConversationAccount.md)
 - [BotFramework::ConversationMembers](docs/ConversationMembers.md)
 - [BotFramework::ConversationParameters](docs/ConversationParameters.md)
 - [BotFramework::ConversationReference](docs/ConversationReference.md)
 - [BotFramework::ConversationResourceResponse](docs/ConversationResourceResponse.md)
 - [BotFramework::ConversationsResult](docs/ConversationsResult.md)
 - [BotFramework::DeliveryModes](docs/DeliveryModes.md)
 - [BotFramework::EndOfConversationCodes](docs/EndOfConversationCodes.md)
 - [BotFramework::Entity](docs/Entity.md)
 - [BotFramework::Error](docs/Error.md)
 - [BotFramework::ErrorResponse](docs/ErrorResponse.md)
 - [BotFramework::Fact](docs/Fact.md)
 - [BotFramework::GeoCoordinates](docs/GeoCoordinates.md)
 - [BotFramework::HeroCard](docs/HeroCard.md)
 - [BotFramework::InnerHttpError](docs/InnerHttpError.md)
 - [BotFramework::InputHints](docs/InputHints.md)
 - [BotFramework::InstallationUpdateActionTypes](docs/InstallationUpdateActionTypes.md)
 - [BotFramework::MediaCard](docs/MediaCard.md)
 - [BotFramework::MediaEventValue](docs/MediaEventValue.md)
 - [BotFramework::MediaUrl](docs/MediaUrl.md)
 - [BotFramework::Mention](docs/Mention.md)
 - [BotFramework::MessageReaction](docs/MessageReaction.md)
 - [BotFramework::MessageReactionTypes](docs/MessageReactionTypes.md)
 - [BotFramework::MicrosoftPayMethodData](docs/MicrosoftPayMethodData.md)
 - [BotFramework::OAuthCard](docs/OAuthCard.md)
 - [BotFramework::PagedMembersResult](docs/PagedMembersResult.md)
 - [BotFramework::PaymentAddress](docs/PaymentAddress.md)
 - [BotFramework::PaymentCurrencyAmount](docs/PaymentCurrencyAmount.md)
 - [BotFramework::PaymentDetails](docs/PaymentDetails.md)
 - [BotFramework::PaymentDetailsModifier](docs/PaymentDetailsModifier.md)
 - [BotFramework::PaymentItem](docs/PaymentItem.md)
 - [BotFramework::PaymentMethodData](docs/PaymentMethodData.md)
 - [BotFramework::PaymentOptions](docs/PaymentOptions.md)
 - [BotFramework::PaymentRequest](docs/PaymentRequest.md)
 - [BotFramework::PaymentRequestComplete](docs/PaymentRequestComplete.md)
 - [BotFramework::PaymentRequestCompleteResult](docs/PaymentRequestCompleteResult.md)
 - [BotFramework::PaymentRequestUpdate](docs/PaymentRequestUpdate.md)
 - [BotFramework::PaymentRequestUpdateResult](docs/PaymentRequestUpdateResult.md)
 - [BotFramework::PaymentResponse](docs/PaymentResponse.md)
 - [BotFramework::PaymentShippingOption](docs/PaymentShippingOption.md)
 - [BotFramework::Place](docs/Place.md)
 - [BotFramework::ReceiptCard](docs/ReceiptCard.md)
 - [BotFramework::ReceiptItem](docs/ReceiptItem.md)
 - [BotFramework::ResourceResponse](docs/ResourceResponse.md)
 - [BotFramework::RoleTypes](docs/RoleTypes.md)
 - [BotFramework::SemanticAction](docs/SemanticAction.md)
 - [BotFramework::SemanticActionStates](docs/SemanticActionStates.md)
 - [BotFramework::SigninCard](docs/SigninCard.md)
 - [BotFramework::SuggestedActions](docs/SuggestedActions.md)
 - [BotFramework::TextFormatTypes](docs/TextFormatTypes.md)
 - [BotFramework::TextHighlight](docs/TextHighlight.md)
 - [BotFramework::Thing](docs/Thing.md)
 - [BotFramework::ThumbnailCard](docs/ThumbnailCard.md)
 - [BotFramework::ThumbnailUrl](docs/ThumbnailUrl.md)
 - [BotFramework::TokenRequest](docs/TokenRequest.md)
 - [BotFramework::TokenResponse](docs/TokenResponse.md)
 - [BotFramework::Transcript](docs/Transcript.md)
 - [BotFramework::VideoCard](docs/VideoCard.md)

## Documentation for Authorization


### bearer_auth

- **Type**: API key
- **API key parameter name**: Authorization
- **Location**: HTTP header

