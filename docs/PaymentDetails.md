# BotFramework::PaymentDetails

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**total** | [**PaymentItem**](PaymentItem.md) |  | [optional] 
**display_items** | [**Array&lt;PaymentItem&gt;**](PaymentItem.md) | Contains line items for the payment request that the user agent may display | [optional] 
**shipping_options** | [**Array&lt;PaymentShippingOption&gt;**](PaymentShippingOption.md) | A sequence containing the different shipping options for the user to choose from | [optional] 
**modifiers** | [**Array&lt;PaymentDetailsModifier&gt;**](PaymentDetailsModifier.md) | Contains modifiers for particular payment method identifiers | [optional] 
**error** | **String** | Error description | [optional] 

