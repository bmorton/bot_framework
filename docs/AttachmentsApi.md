# BotFramework::AttachmentsApi

All URIs are relative to *https://api.botframework.com/*

Method | HTTP request | Description
------------- | ------------- | -------------
[**attachments_get_attachment**](AttachmentsApi.md#attachments_get_attachment) | **GET** /v3/attachments/{attachmentId}/views/{viewId} | GetAttachment
[**attachments_get_attachment_info**](AttachmentsApi.md#attachments_get_attachment_info) | **GET** /v3/attachments/{attachmentId} | GetAttachmentInfo

# **attachments_get_attachment**
> String attachments_get_attachment(attachment_id, view_id)

GetAttachment

Get the named view as binary content

### Example
```ruby
# load the gem
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
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **attachment_id** | **String**| attachment id | 
 **view_id** | **String**| View id from attachmentInfo | 

### Return type

**String**

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, text/json, application/xml, text/xml



# **attachments_get_attachment_info**
> AttachmentInfo attachments_get_attachment_info(attachment_id)

GetAttachmentInfo

Get AttachmentInfo structure describing the attachment views

### Example
```ruby
# load the gem
require 'bot_framework'

api_instance = BotFramework::AttachmentsApi.new
attachment_id = 'attachment_id_example' # String | attachment id


begin
  #GetAttachmentInfo
  result = api_instance.attachments_get_attachment_info(attachment_id)
  p result
rescue BotFramework::ApiError => e
  puts "Exception when calling AttachmentsApi->attachments_get_attachment_info: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **attachment_id** | **String**| attachment id | 

### Return type

[**AttachmentInfo**](AttachmentInfo.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, text/json, application/xml, text/xml



