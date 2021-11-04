# BotFramework::PaymentAddress

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**country** | **String** | This is the CLDR (Common Locale Data Repository) region code. For example, US, GB, CN, or JP | [optional] 
**address_line** | **Array&lt;String&gt;** | This is the most specific part of the address. It can include, for example, a street name, a house number, apartment number, a rural delivery route, descriptive instructions, or a post office box number. | [optional] 
**region** | **String** | This is the top level administrative subdivision of the country. For example, this can be a state, a province, an oblast, or a prefecture. | [optional] 
**city** | **String** | This is the city/town portion of the address. | [optional] 
**dependent_locality** | **String** | This is the dependent locality or sublocality within a city. For example, used for neighborhoods, boroughs, districts, or UK dependent localities. | [optional] 
**postal_code** | **String** | This is the postal code or ZIP code, also known as PIN code in India. | [optional] 
**sorting_code** | **String** | This is the sorting code as used in, for example, France. | [optional] 
**language_code** | **String** | This is the BCP-47 language code for the address. It&#x27;s used to determine the field separators and the order of fields when formatting the address for display. | [optional] 
**organization** | **String** | This is the organization, firm, company, or institution at this address. | [optional] 
**recipient** | **String** | This is the name of the recipient or contact person. | [optional] 
**phone** | **String** | This is the phone number of the recipient or contact person. | [optional] 

