# BotFramework::PaymentDetailsModifier

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**supported_methods** | **Array&lt;String&gt;** | Contains a sequence of payment method identifiers | [optional] 
**total** | [**PaymentItem**](PaymentItem.md) |  | [optional] 
**additional_display_items** | [**Array&lt;PaymentItem&gt;**](PaymentItem.md) | Provides additional display items that are appended to the displayItems field in the PaymentDetails dictionary for the payment method identifiers in the supportedMethods field | [optional] 
**data** | **Object** | A JSON-serializable object that provides optional information that might be needed by the supported payment methods | [optional] 

