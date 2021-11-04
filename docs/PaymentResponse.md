# BotFramework::PaymentResponse

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**method_name** | **String** | The payment method identifier for the payment method that the user selected to fulfil the transaction | [optional] 
**details** | **Object** | A JSON-serializable object that provides a payment method specific message used by the merchant to process the transaction and determine successful fund transfer | [optional] 
**shipping_address** | [**PaymentAddress**](PaymentAddress.md) |  | [optional] 
**shipping_option** | **String** | If the requestShipping flag was set to true in the PaymentOptions passed to the PaymentRequest constructor, then shippingOption will be the id attribute of the selected shipping option | [optional] 
**payer_email** | **String** | If the requestPayerEmail flag was set to true in the PaymentOptions passed to the PaymentRequest constructor, then payerEmail will be the email address chosen by the user | [optional] 
**payer_phone** | **String** | If the requestPayerPhone flag was set to true in the PaymentOptions passed to the PaymentRequest constructor, then payerPhone will be the phone number chosen by the user | [optional] 

