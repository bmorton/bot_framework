# BotFramework::ConversationParameters

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**is_group** | **BOOLEAN** | IsGroup | [optional] 
**bot** | [**ChannelAccount**](ChannelAccount.md) |  | [optional] 
**members** | [**Array&lt;ChannelAccount&gt;**](ChannelAccount.md) | Members to add to the conversation | [optional] 
**topic_name** | **String** | (Optional) Topic of the conversation (if supported by the channel) | [optional] 
**tenant_id** | **String** | (Optional) The tenant ID in which the conversation should be created | [optional] 
**activity** | [**Activity**](Activity.md) |  | [optional] 
**channel_data** | **Object** | Channel specific payload for creating the conversation | [optional] 

