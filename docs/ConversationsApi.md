# BotFramework::ConversationsApi

All URIs are relative to *https://api.botframework.com/*

Method | HTTP request | Description
------------- | ------------- | -------------
[**conversations_create_conversation**](ConversationsApi.md#conversations_create_conversation) | **POST** /v3/conversations | CreateConversation
[**conversations_create_conversation**](ConversationsApi.md#conversations_create_conversation) | **POST** /v3/conversations | CreateConversation
[**conversations_delete_activity**](ConversationsApi.md#conversations_delete_activity) | **DELETE** /v3/conversations/{conversationId}/activities/{activityId} | DeleteActivity
[**conversations_delete_conversation_member**](ConversationsApi.md#conversations_delete_conversation_member) | **DELETE** /v3/conversations/{conversationId}/members/{memberId} | DeleteConversationMember
[**conversations_get_activity_members**](ConversationsApi.md#conversations_get_activity_members) | **GET** /v3/conversations/{conversationId}/activities/{activityId}/members | GetActivityMembers
[**conversations_get_conversation_members**](ConversationsApi.md#conversations_get_conversation_members) | **GET** /v3/conversations/{conversationId}/members | GetConversationMembers
[**conversations_get_conversation_paged_members**](ConversationsApi.md#conversations_get_conversation_paged_members) | **GET** /v3/conversations/{conversationId}/pagedmembers | GetConversationPagedMembers
[**conversations_get_conversations**](ConversationsApi.md#conversations_get_conversations) | **GET** /v3/conversations | GetConversations
[**conversations_reply_to_activity**](ConversationsApi.md#conversations_reply_to_activity) | **POST** /v3/conversations/{conversationId}/activities/{activityId} | ReplyToActivity
[**conversations_reply_to_activity**](ConversationsApi.md#conversations_reply_to_activity) | **POST** /v3/conversations/{conversationId}/activities/{activityId} | ReplyToActivity
[**conversations_send_conversation_history**](ConversationsApi.md#conversations_send_conversation_history) | **POST** /v3/conversations/{conversationId}/activities/history | SendConversationHistory
[**conversations_send_conversation_history**](ConversationsApi.md#conversations_send_conversation_history) | **POST** /v3/conversations/{conversationId}/activities/history | SendConversationHistory
[**conversations_send_to_conversation**](ConversationsApi.md#conversations_send_to_conversation) | **POST** /v3/conversations/{conversationId}/activities | SendToConversation
[**conversations_send_to_conversation**](ConversationsApi.md#conversations_send_to_conversation) | **POST** /v3/conversations/{conversationId}/activities | SendToConversation
[**conversations_update_activity**](ConversationsApi.md#conversations_update_activity) | **PUT** /v3/conversations/{conversationId}/activities/{activityId} | UpdateActivity
[**conversations_update_activity**](ConversationsApi.md#conversations_update_activity) | **PUT** /v3/conversations/{conversationId}/activities/{activityId} | UpdateActivity
[**conversations_upload_attachment**](ConversationsApi.md#conversations_upload_attachment) | **POST** /v3/conversations/{conversationId}/attachments | UploadAttachment
[**conversations_upload_attachment**](ConversationsApi.md#conversations_upload_attachment) | **POST** /v3/conversations/{conversationId}/attachments | UploadAttachment

# **conversations_create_conversation**
> ConversationResourceResponse conversations_create_conversation(body)

CreateConversation

Create a new Conversation.    POST to this method with a  * Bot being the bot creating the conversation  * IsGroup set to true if this is not a direct message (default is false)  * Array containing the members to include in the conversation    The return value is a ResourceResponse which contains a conversation id which is suitable for use  in the message payload and REST API uris.    Most channels only support the semantics of bots initiating a direct message conversation.  An example of how to do that would be:    ```  var resource = await connector.conversations.CreateConversation(new ConversationParameters(){ Bot = bot, members = new ChannelAccount[] { new ChannelAccount(\"user1\") } );  await connect.Conversations.SendToConversationAsync(resource.Id, new Activity() ... ) ;    ```

### Example
```ruby
# load the gem
require 'bot_framework'

api_instance = BotFramework::ConversationsApi.new
body = BotFramework::ConversationParameters.new # ConversationParameters | Parameters to create the conversation from


begin
  #CreateConversation
  result = api_instance.conversations_create_conversation(body)
  p result
rescue BotFramework::ApiError => e
  puts "Exception when calling ConversationsApi->conversations_create_conversation: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**ConversationParameters**](ConversationParameters.md)| Parameters to create the conversation from | 

### Return type

[**ConversationResourceResponse**](ConversationResourceResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, text/json, application/xml, text/xml, application/x-www-form-urlencoded
 - **Accept**: application/json, text/json, application/xml, text/xml



# **conversations_create_conversation**
> ConversationResourceResponse conversations_create_conversation(is_groupbotmemberstopic_nametenant_idactivitychannel_data)

CreateConversation

Create a new Conversation.    POST to this method with a  * Bot being the bot creating the conversation  * IsGroup set to true if this is not a direct message (default is false)  * Array containing the members to include in the conversation    The return value is a ResourceResponse which contains a conversation id which is suitable for use  in the message payload and REST API uris.    Most channels only support the semantics of bots initiating a direct message conversation.  An example of how to do that would be:    ```  var resource = await connector.conversations.CreateConversation(new ConversationParameters(){ Bot = bot, members = new ChannelAccount[] { new ChannelAccount(\"user1\") } );  await connect.Conversations.SendToConversationAsync(resource.Id, new Activity() ... ) ;    ```

### Example
```ruby
# load the gem
require 'bot_framework'

api_instance = BotFramework::ConversationsApi.new
is_group = true # BOOLEAN | 
bot = BotFramework::ChannelAccount.new # ChannelAccount | 
members = [BotFramework::ChannelAccount.new] # Array<ChannelAccount> | 
topic_name = 'topic_name_example' # String | 
tenant_id = 'tenant_id_example' # String | 
activity = BotFramework::Activity.new # Activity | 
channel_data = nil # Object | 


begin
  #CreateConversation
  result = api_instance.conversations_create_conversation(is_groupbotmemberstopic_nametenant_idactivitychannel_data)
  p result
rescue BotFramework::ApiError => e
  puts "Exception when calling ConversationsApi->conversations_create_conversation: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **is_group** | **BOOLEAN**|  | 
 **bot** | [**ChannelAccount**](.md)|  | 
 **members** | [**Array&lt;ChannelAccount&gt;**](ChannelAccount.md)|  | 
 **topic_name** | **String**|  | 
 **tenant_id** | **String**|  | 
 **activity** | [**Activity**](.md)|  | 
 **channel_data** | [**Object**](.md)|  | 

### Return type

[**ConversationResourceResponse**](ConversationResourceResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, text/json, application/xml, text/xml, application/x-www-form-urlencoded
 - **Accept**: application/json, text/json, application/xml, text/xml



# **conversations_delete_activity**
> conversations_delete_activity(conversation_id, activity_id)

DeleteActivity

Delete an existing activity.    Some channels allow you to delete an existing activity, and if successful this method will remove the specified activity.

### Example
```ruby
# load the gem
require 'bot_framework'

api_instance = BotFramework::ConversationsApi.new
conversation_id = 'conversation_id_example' # String | Conversation ID
activity_id = 'activity_id_example' # String | activityId to delete


begin
  #DeleteActivity
  api_instance.conversations_delete_activity(conversation_id, activity_id)
rescue BotFramework::ApiError => e
  puts "Exception when calling ConversationsApi->conversations_delete_activity: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **conversation_id** | **String**| Conversation ID | 
 **activity_id** | **String**| activityId to delete | 

### Return type

nil (empty response body)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, text/json, application/xml, text/xml



# **conversations_delete_conversation_member**
> conversations_delete_conversation_member(conversation_id, member_id)

DeleteConversationMember

Deletes a member from a conversation.     This REST API takes a ConversationId and a memberId (of type string) and removes that member from the conversation. If that member was the last member  of the conversation, the conversation will also be deleted.

### Example
```ruby
# load the gem
require 'bot_framework'

api_instance = BotFramework::ConversationsApi.new
conversation_id = 'conversation_id_example' # String | Conversation ID
member_id = 'member_id_example' # String | ID of the member to delete from this conversation


begin
  #DeleteConversationMember
  api_instance.conversations_delete_conversation_member(conversation_id, member_id)
rescue BotFramework::ApiError => e
  puts "Exception when calling ConversationsApi->conversations_delete_conversation_member: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **conversation_id** | **String**| Conversation ID | 
 **member_id** | **String**| ID of the member to delete from this conversation | 

### Return type

nil (empty response body)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, text/json, application/xml, text/xml



# **conversations_get_activity_members**
> Array&lt;ChannelAccount&gt; conversations_get_activity_members(conversation_id, activity_id)

GetActivityMembers

Enumerate the members of an activity.     This REST API takes a ConversationId and a ActivityId, returning an array of ChannelAccount objects representing the members of the particular activity in the conversation.

### Example
```ruby
# load the gem
require 'bot_framework'

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
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **conversation_id** | **String**| Conversation ID | 
 **activity_id** | **String**| Activity ID | 

### Return type

[**Array&lt;ChannelAccount&gt;**](ChannelAccount.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, text/json, application/xml, text/xml



# **conversations_get_conversation_members**
> Array&lt;ChannelAccount&gt; conversations_get_conversation_members(conversation_id)

GetConversationMembers

Enumerate the members of a conversation.     This REST API takes a ConversationId and returns an array of ChannelAccount objects representing the members of the conversation.

### Example
```ruby
# load the gem
require 'bot_framework'

api_instance = BotFramework::ConversationsApi.new
conversation_id = 'conversation_id_example' # String | Conversation ID


begin
  #GetConversationMembers
  result = api_instance.conversations_get_conversation_members(conversation_id)
  p result
rescue BotFramework::ApiError => e
  puts "Exception when calling ConversationsApi->conversations_get_conversation_members: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **conversation_id** | **String**| Conversation ID | 

### Return type

[**Array&lt;ChannelAccount&gt;**](ChannelAccount.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, text/json, application/xml, text/xml



# **conversations_get_conversation_paged_members**
> PagedMembersResult conversations_get_conversation_paged_members(conversation_id, opts)

GetConversationPagedMembers

Enumerate the members of a conversation one page at a time.    This REST API takes a ConversationId. Optionally a pageSize and/or continuationToken can be provided. It returns a PagedMembersResult, which contains an array  of ChannelAccounts representing the members of the conversation and a continuation token that can be used to get more values.    One page of ChannelAccounts records are returned with each call. The number of records in a page may vary between channels and calls. The pageSize parameter can be used as   a suggestion. If there are no additional results the response will not contain a continuation token. If there are no members in the conversation the Members will be empty or not present in the response.    A response to a request that has a continuation token from a prior request may rarely return members from a previous request.

### Example
```ruby
# load the gem
require 'bot_framework'

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
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **conversation_id** | **String**| Conversation ID | 
 **page_size** | **Integer**| Suggested page size | [optional] 
 **continuation_token** | **String**| Continuation Token | [optional] 

### Return type

[**PagedMembersResult**](PagedMembersResult.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, text/json, application/xml, text/xml



# **conversations_get_conversations**
> ConversationsResult conversations_get_conversations(opts)

GetConversations

List the Conversations in which this bot has participated.    GET from this method with a skip token    The return value is a ConversationsResult, which contains an array of ConversationMembers and a skip token.  If the skip token is not empty, then   there are further values to be returned. Call this method again with the returned token to get more values.    Each ConversationMembers object contains the ID of the conversation and an array of ChannelAccounts that describe the members of the conversation.

### Example
```ruby
# load the gem
require 'bot_framework'

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
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **continuation_token** | **String**| skip or continuation token | [optional] 

### Return type

[**ConversationsResult**](ConversationsResult.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, text/json, application/xml, text/xml



# **conversations_reply_to_activity**
> ResourceResponse conversations_reply_to_activity(bodyconversation_idactivity_id)

ReplyToActivity

This method allows you to reply to an activity.    This is slightly different from SendToConversation().  * SendToConversation(conversationId) - will append the activity to the end of the conversation according to the timestamp or semantics of the channel.  * ReplyToActivity(conversationId,ActivityId) - adds the activity as a reply to another activity, if the channel supports it. If the channel does not support nested replies, ReplyToActivity falls back to SendToConversation.    Use ReplyToActivity when replying to a specific activity in the conversation.    Use SendToConversation in all other cases.

### Example
```ruby
# load the gem
require 'bot_framework'

api_instance = BotFramework::ConversationsApi.new
body = BotFramework::Activity.new # Activity | Activity to send
conversation_id = 'conversation_id_example' # String | Conversation ID
activity_id = 'activity_id_example' # String | activityId the reply is to (OPTIONAL)


begin
  #ReplyToActivity
  result = api_instance.conversations_reply_to_activity(bodyconversation_idactivity_id)
  p result
rescue BotFramework::ApiError => e
  puts "Exception when calling ConversationsApi->conversations_reply_to_activity: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**Activity**](Activity.md)| Activity to send | 
 **conversation_id** | **String**| Conversation ID | 
 **activity_id** | **String**| activityId the reply is to (OPTIONAL) | 

### Return type

[**ResourceResponse**](ResourceResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, text/json, application/xml, text/xml, application/x-www-form-urlencoded
 - **Accept**: application/json, text/json



# **conversations_reply_to_activity**
> ResourceResponse conversations_reply_to_activity(typeidtimestamplocal_timestamplocal_timezonecaller_idservice_urlchannel_idfromconversationrecipienttext_formatattachment_layoutmembers_addedmembers_removedreactions_addedreactions_removedtopic_namehistory_disclosedlocaletextspeakinput_hintsummarysuggested_actionsattachmentsentitieschannel_dataactionreply_to_idlabelvalue_typevaluenamerelates_tocodeexpirationimportancedelivery_modelisten_fortext_highlightssemantic_actionconversation_idactivity_id)

ReplyToActivity

This method allows you to reply to an activity.    This is slightly different from SendToConversation().  * SendToConversation(conversationId) - will append the activity to the end of the conversation according to the timestamp or semantics of the channel.  * ReplyToActivity(conversationId,ActivityId) - adds the activity as a reply to another activity, if the channel supports it. If the channel does not support nested replies, ReplyToActivity falls back to SendToConversation.    Use ReplyToActivity when replying to a specific activity in the conversation.    Use SendToConversation in all other cases.

### Example
```ruby
# load the gem
require 'bot_framework'

api_instance = BotFramework::ConversationsApi.new
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
  result = api_instance.conversations_reply_to_activity(typeidtimestamplocal_timestamplocal_timezonecaller_idservice_urlchannel_idfromconversationrecipienttext_formatattachment_layoutmembers_addedmembers_removedreactions_addedreactions_removedtopic_namehistory_disclosedlocaletextspeakinput_hintsummarysuggested_actionsattachmentsentitieschannel_dataactionreply_to_idlabelvalue_typevaluenamerelates_tocodeexpirationimportancedelivery_modelisten_fortext_highlightssemantic_actionconversation_idactivity_id)
  p result
rescue BotFramework::ApiError => e
  puts "Exception when calling ConversationsApi->conversations_reply_to_activity: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **type** | [**ActivityTypes**](.md)|  | 
 **id** | **String**|  | 
 **timestamp** | **DateTime**|  | 
 **local_timestamp** | **DateTime**|  | 
 **local_timezone** | **String**|  | 
 **caller_id** | **String**|  | 
 **service_url** | **String**|  | 
 **channel_id** | **String**|  | 
 **from** | [**ChannelAccount**](.md)|  | 
 **conversation** | [**ConversationAccount**](.md)|  | 
 **recipient** | [**ChannelAccount**](.md)|  | 
 **text_format** | [**TextFormatTypes**](.md)|  | 
 **attachment_layout** | [**AttachmentLayoutTypes**](.md)|  | 
 **members_added** | [**Array&lt;ChannelAccount&gt;**](ChannelAccount.md)|  | 
 **members_removed** | [**Array&lt;ChannelAccount&gt;**](ChannelAccount.md)|  | 
 **reactions_added** | [**Array&lt;MessageReaction&gt;**](MessageReaction.md)|  | 
 **reactions_removed** | [**Array&lt;MessageReaction&gt;**](MessageReaction.md)|  | 
 **topic_name** | **String**|  | 
 **history_disclosed** | **BOOLEAN**|  | 
 **locale** | **String**|  | 
 **text** | **String**|  | 
 **speak** | **String**|  | 
 **input_hint** | [**InputHints**](.md)|  | 
 **summary** | **String**|  | 
 **suggested_actions** | [**SuggestedActions**](.md)|  | 
 **attachments** | [**Array&lt;Attachment&gt;**](Attachment.md)|  | 
 **entities** | [**Array&lt;Entity&gt;**](Entity.md)|  | 
 **channel_data** | [**Object**](.md)|  | 
 **action** | **String**|  | 
 **reply_to_id** | **String**|  | 
 **label** | **String**|  | 
 **value_type** | **String**|  | 
 **value** | [**Object**](.md)|  | 
 **name** | **String**|  | 
 **relates_to** | [**ConversationReference**](.md)|  | 
 **code** | [**EndOfConversationCodes**](.md)|  | 
 **expiration** | **DateTime**|  | 
 **importance** | [**ActivityImportance**](.md)|  | 
 **delivery_mode** | [**DeliveryModes**](.md)|  | 
 **listen_for** | [**Array&lt;String&gt;**](String.md)|  | 
 **text_highlights** | [**Array&lt;TextHighlight&gt;**](TextHighlight.md)|  | 
 **semantic_action** | [**SemanticAction**](.md)|  | 
 **conversation_id** | **String**| Conversation ID | 
 **activity_id** | **String**| activityId the reply is to (OPTIONAL) | 

### Return type

[**ResourceResponse**](ResourceResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, text/json, application/xml, text/xml, application/x-www-form-urlencoded
 - **Accept**: application/json, text/json



# **conversations_send_conversation_history**
> ResourceResponse conversations_send_conversation_history(bodyconversation_id)

SendConversationHistory

This method allows you to upload the historic activities to the conversation.    Sender must ensure that the historic activities have unique ids and appropriate timestamps. The ids are used by the client to deal with duplicate activities and the timestamps are used by the client to render the activities in the right order.

### Example
```ruby
# load the gem
require 'bot_framework'

api_instance = BotFramework::ConversationsApi.new
body = BotFramework::Transcript.new # Transcript | Historic activities
conversation_id = 'conversation_id_example' # String | Conversation ID


begin
  #SendConversationHistory
  result = api_instance.conversations_send_conversation_history(bodyconversation_id)
  p result
rescue BotFramework::ApiError => e
  puts "Exception when calling ConversationsApi->conversations_send_conversation_history: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**Transcript**](Transcript.md)| Historic activities | 
 **conversation_id** | **String**| Conversation ID | 

### Return type

[**ResourceResponse**](ResourceResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, text/json, application/xml, text/xml, application/x-www-form-urlencoded
 - **Accept**: application/json, text/json



# **conversations_send_conversation_history**
> ResourceResponse conversations_send_conversation_history(activitiesconversation_id)

SendConversationHistory

This method allows you to upload the historic activities to the conversation.    Sender must ensure that the historic activities have unique ids and appropriate timestamps. The ids are used by the client to deal with duplicate activities and the timestamps are used by the client to render the activities in the right order.

### Example
```ruby
# load the gem
require 'bot_framework'

api_instance = BotFramework::ConversationsApi.new
activities = [BotFramework::Activity.new] # Array<Activity> | 
conversation_id = 'conversation_id_example' # String | Conversation ID


begin
  #SendConversationHistory
  result = api_instance.conversations_send_conversation_history(activitiesconversation_id)
  p result
rescue BotFramework::ApiError => e
  puts "Exception when calling ConversationsApi->conversations_send_conversation_history: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **activities** | [**Array&lt;Activity&gt;**](Activity.md)|  | 
 **conversation_id** | **String**| Conversation ID | 

### Return type

[**ResourceResponse**](ResourceResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, text/json, application/xml, text/xml, application/x-www-form-urlencoded
 - **Accept**: application/json, text/json



# **conversations_send_to_conversation**
> ResourceResponse conversations_send_to_conversation(bodyconversation_id)

SendToConversation

This method allows you to send an activity to the end of a conversation.    This is slightly different from ReplyToActivity().  * SendToConversation(conversationId) - will append the activity to the end of the conversation according to the timestamp or semantics of the channel.  * ReplyToActivity(conversationId,ActivityId) - adds the activity as a reply to another activity, if the channel supports it. If the channel does not support nested replies, ReplyToActivity falls back to SendToConversation.    Use ReplyToActivity when replying to a specific activity in the conversation.    Use SendToConversation in all other cases.

### Example
```ruby
# load the gem
require 'bot_framework'

api_instance = BotFramework::ConversationsApi.new
body = BotFramework::Activity.new # Activity | Activity to send
conversation_id = 'conversation_id_example' # String | Conversation ID


begin
  #SendToConversation
  result = api_instance.conversations_send_to_conversation(bodyconversation_id)
  p result
rescue BotFramework::ApiError => e
  puts "Exception when calling ConversationsApi->conversations_send_to_conversation: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**Activity**](Activity.md)| Activity to send | 
 **conversation_id** | **String**| Conversation ID | 

### Return type

[**ResourceResponse**](ResourceResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, text/json, application/xml, text/xml, application/x-www-form-urlencoded
 - **Accept**: application/json, text/json



# **conversations_send_to_conversation**
> ResourceResponse conversations_send_to_conversation(typeidtimestamplocal_timestamplocal_timezonecaller_idservice_urlchannel_idfromconversationrecipienttext_formatattachment_layoutmembers_addedmembers_removedreactions_addedreactions_removedtopic_namehistory_disclosedlocaletextspeakinput_hintsummarysuggested_actionsattachmentsentitieschannel_dataactionreply_to_idlabelvalue_typevaluenamerelates_tocodeexpirationimportancedelivery_modelisten_fortext_highlightssemantic_actionconversation_id)

SendToConversation

This method allows you to send an activity to the end of a conversation.    This is slightly different from ReplyToActivity().  * SendToConversation(conversationId) - will append the activity to the end of the conversation according to the timestamp or semantics of the channel.  * ReplyToActivity(conversationId,ActivityId) - adds the activity as a reply to another activity, if the channel supports it. If the channel does not support nested replies, ReplyToActivity falls back to SendToConversation.    Use ReplyToActivity when replying to a specific activity in the conversation.    Use SendToConversation in all other cases.

### Example
```ruby
# load the gem
require 'bot_framework'

api_instance = BotFramework::ConversationsApi.new
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
  result = api_instance.conversations_send_to_conversation(typeidtimestamplocal_timestamplocal_timezonecaller_idservice_urlchannel_idfromconversationrecipienttext_formatattachment_layoutmembers_addedmembers_removedreactions_addedreactions_removedtopic_namehistory_disclosedlocaletextspeakinput_hintsummarysuggested_actionsattachmentsentitieschannel_dataactionreply_to_idlabelvalue_typevaluenamerelates_tocodeexpirationimportancedelivery_modelisten_fortext_highlightssemantic_actionconversation_id)
  p result
rescue BotFramework::ApiError => e
  puts "Exception when calling ConversationsApi->conversations_send_to_conversation: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **type** | [**ActivityTypes**](.md)|  | 
 **id** | **String**|  | 
 **timestamp** | **DateTime**|  | 
 **local_timestamp** | **DateTime**|  | 
 **local_timezone** | **String**|  | 
 **caller_id** | **String**|  | 
 **service_url** | **String**|  | 
 **channel_id** | **String**|  | 
 **from** | [**ChannelAccount**](.md)|  | 
 **conversation** | [**ConversationAccount**](.md)|  | 
 **recipient** | [**ChannelAccount**](.md)|  | 
 **text_format** | [**TextFormatTypes**](.md)|  | 
 **attachment_layout** | [**AttachmentLayoutTypes**](.md)|  | 
 **members_added** | [**Array&lt;ChannelAccount&gt;**](ChannelAccount.md)|  | 
 **members_removed** | [**Array&lt;ChannelAccount&gt;**](ChannelAccount.md)|  | 
 **reactions_added** | [**Array&lt;MessageReaction&gt;**](MessageReaction.md)|  | 
 **reactions_removed** | [**Array&lt;MessageReaction&gt;**](MessageReaction.md)|  | 
 **topic_name** | **String**|  | 
 **history_disclosed** | **BOOLEAN**|  | 
 **locale** | **String**|  | 
 **text** | **String**|  | 
 **speak** | **String**|  | 
 **input_hint** | [**InputHints**](.md)|  | 
 **summary** | **String**|  | 
 **suggested_actions** | [**SuggestedActions**](.md)|  | 
 **attachments** | [**Array&lt;Attachment&gt;**](Attachment.md)|  | 
 **entities** | [**Array&lt;Entity&gt;**](Entity.md)|  | 
 **channel_data** | [**Object**](.md)|  | 
 **action** | **String**|  | 
 **reply_to_id** | **String**|  | 
 **label** | **String**|  | 
 **value_type** | **String**|  | 
 **value** | [**Object**](.md)|  | 
 **name** | **String**|  | 
 **relates_to** | [**ConversationReference**](.md)|  | 
 **code** | [**EndOfConversationCodes**](.md)|  | 
 **expiration** | **DateTime**|  | 
 **importance** | [**ActivityImportance**](.md)|  | 
 **delivery_mode** | [**DeliveryModes**](.md)|  | 
 **listen_for** | [**Array&lt;String&gt;**](String.md)|  | 
 **text_highlights** | [**Array&lt;TextHighlight&gt;**](TextHighlight.md)|  | 
 **semantic_action** | [**SemanticAction**](.md)|  | 
 **conversation_id** | **String**| Conversation ID | 

### Return type

[**ResourceResponse**](ResourceResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, text/json, application/xml, text/xml, application/x-www-form-urlencoded
 - **Accept**: application/json, text/json



# **conversations_update_activity**
> ResourceResponse conversations_update_activity(bodyconversation_idactivity_id)

UpdateActivity

Edit an existing activity.    Some channels allow you to edit an existing activity to reflect the new state of a bot conversation.    For example, you can remove buttons after someone has clicked \"Approve\" button.

### Example
```ruby
# load the gem
require 'bot_framework'

api_instance = BotFramework::ConversationsApi.new
body = BotFramework::Activity.new # Activity | replacement Activity
conversation_id = 'conversation_id_example' # String | Conversation ID
activity_id = 'activity_id_example' # String | activityId to update


begin
  #UpdateActivity
  result = api_instance.conversations_update_activity(bodyconversation_idactivity_id)
  p result
rescue BotFramework::ApiError => e
  puts "Exception when calling ConversationsApi->conversations_update_activity: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**Activity**](Activity.md)| replacement Activity | 
 **conversation_id** | **String**| Conversation ID | 
 **activity_id** | **String**| activityId to update | 

### Return type

[**ResourceResponse**](ResourceResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, text/json, application/xml, text/xml, application/x-www-form-urlencoded
 - **Accept**: application/json, text/json



# **conversations_update_activity**
> ResourceResponse conversations_update_activity(typeidtimestamplocal_timestamplocal_timezonecaller_idservice_urlchannel_idfromconversationrecipienttext_formatattachment_layoutmembers_addedmembers_removedreactions_addedreactions_removedtopic_namehistory_disclosedlocaletextspeakinput_hintsummarysuggested_actionsattachmentsentitieschannel_dataactionreply_to_idlabelvalue_typevaluenamerelates_tocodeexpirationimportancedelivery_modelisten_fortext_highlightssemantic_actionconversation_idactivity_id)

UpdateActivity

Edit an existing activity.    Some channels allow you to edit an existing activity to reflect the new state of a bot conversation.    For example, you can remove buttons after someone has clicked \"Approve\" button.

### Example
```ruby
# load the gem
require 'bot_framework'

api_instance = BotFramework::ConversationsApi.new
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
  result = api_instance.conversations_update_activity(typeidtimestamplocal_timestamplocal_timezonecaller_idservice_urlchannel_idfromconversationrecipienttext_formatattachment_layoutmembers_addedmembers_removedreactions_addedreactions_removedtopic_namehistory_disclosedlocaletextspeakinput_hintsummarysuggested_actionsattachmentsentitieschannel_dataactionreply_to_idlabelvalue_typevaluenamerelates_tocodeexpirationimportancedelivery_modelisten_fortext_highlightssemantic_actionconversation_idactivity_id)
  p result
rescue BotFramework::ApiError => e
  puts "Exception when calling ConversationsApi->conversations_update_activity: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **type** | [**ActivityTypes**](.md)|  | 
 **id** | **String**|  | 
 **timestamp** | **DateTime**|  | 
 **local_timestamp** | **DateTime**|  | 
 **local_timezone** | **String**|  | 
 **caller_id** | **String**|  | 
 **service_url** | **String**|  | 
 **channel_id** | **String**|  | 
 **from** | [**ChannelAccount**](.md)|  | 
 **conversation** | [**ConversationAccount**](.md)|  | 
 **recipient** | [**ChannelAccount**](.md)|  | 
 **text_format** | [**TextFormatTypes**](.md)|  | 
 **attachment_layout** | [**AttachmentLayoutTypes**](.md)|  | 
 **members_added** | [**Array&lt;ChannelAccount&gt;**](ChannelAccount.md)|  | 
 **members_removed** | [**Array&lt;ChannelAccount&gt;**](ChannelAccount.md)|  | 
 **reactions_added** | [**Array&lt;MessageReaction&gt;**](MessageReaction.md)|  | 
 **reactions_removed** | [**Array&lt;MessageReaction&gt;**](MessageReaction.md)|  | 
 **topic_name** | **String**|  | 
 **history_disclosed** | **BOOLEAN**|  | 
 **locale** | **String**|  | 
 **text** | **String**|  | 
 **speak** | **String**|  | 
 **input_hint** | [**InputHints**](.md)|  | 
 **summary** | **String**|  | 
 **suggested_actions** | [**SuggestedActions**](.md)|  | 
 **attachments** | [**Array&lt;Attachment&gt;**](Attachment.md)|  | 
 **entities** | [**Array&lt;Entity&gt;**](Entity.md)|  | 
 **channel_data** | [**Object**](.md)|  | 
 **action** | **String**|  | 
 **reply_to_id** | **String**|  | 
 **label** | **String**|  | 
 **value_type** | **String**|  | 
 **value** | [**Object**](.md)|  | 
 **name** | **String**|  | 
 **relates_to** | [**ConversationReference**](.md)|  | 
 **code** | [**EndOfConversationCodes**](.md)|  | 
 **expiration** | **DateTime**|  | 
 **importance** | [**ActivityImportance**](.md)|  | 
 **delivery_mode** | [**DeliveryModes**](.md)|  | 
 **listen_for** | [**Array&lt;String&gt;**](String.md)|  | 
 **text_highlights** | [**Array&lt;TextHighlight&gt;**](TextHighlight.md)|  | 
 **semantic_action** | [**SemanticAction**](.md)|  | 
 **conversation_id** | **String**| Conversation ID | 
 **activity_id** | **String**| activityId to update | 

### Return type

[**ResourceResponse**](ResourceResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, text/json, application/xml, text/xml, application/x-www-form-urlencoded
 - **Accept**: application/json, text/json



# **conversations_upload_attachment**
> ResourceResponse conversations_upload_attachment(bodyconversation_id)

UploadAttachment

Upload an attachment directly into a channel's blob storage.    This is useful because it allows you to store data in a compliant store when dealing with enterprises.    The response is a ResourceResponse which contains an AttachmentId which is suitable for using with the attachments API.

### Example
```ruby
# load the gem
require 'bot_framework'

api_instance = BotFramework::ConversationsApi.new
body = BotFramework::AttachmentData.new # AttachmentData | Attachment data
conversation_id = 'conversation_id_example' # String | Conversation ID


begin
  #UploadAttachment
  result = api_instance.conversations_upload_attachment(bodyconversation_id)
  p result
rescue BotFramework::ApiError => e
  puts "Exception when calling ConversationsApi->conversations_upload_attachment: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**AttachmentData**](AttachmentData.md)| Attachment data | 
 **conversation_id** | **String**| Conversation ID | 

### Return type

[**ResourceResponse**](ResourceResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, text/json, application/xml, text/xml, application/x-www-form-urlencoded
 - **Accept**: application/json, text/json



# **conversations_upload_attachment**
> ResourceResponse conversations_upload_attachment(typenameoriginal_base64thumbnail_base64conversation_id)

UploadAttachment

Upload an attachment directly into a channel's blob storage.    This is useful because it allows you to store data in a compliant store when dealing with enterprises.    The response is a ResourceResponse which contains an AttachmentId which is suitable for using with the attachments API.

### Example
```ruby
# load the gem
require 'bot_framework'

api_instance = BotFramework::ConversationsApi.new
type = 'type_example' # String | 
name = 'name_example' # String | 
original_base64 = 'B' # String | 
thumbnail_base64 = 'B' # String | 
conversation_id = 'conversation_id_example' # String | Conversation ID


begin
  #UploadAttachment
  result = api_instance.conversations_upload_attachment(typenameoriginal_base64thumbnail_base64conversation_id)
  p result
rescue BotFramework::ApiError => e
  puts "Exception when calling ConversationsApi->conversations_upload_attachment: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **type** | **String**|  | 
 **name** | **String**|  | 
 **original_base64** | **String**|  | 
 **thumbnail_base64** | **String**|  | 
 **conversation_id** | **String**| Conversation ID | 

### Return type

[**ResourceResponse**](ResourceResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, text/json, application/xml, text/xml, application/x-www-form-urlencoded
 - **Accept**: application/json, text/json



