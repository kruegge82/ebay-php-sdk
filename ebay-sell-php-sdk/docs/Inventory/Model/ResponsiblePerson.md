# # ResponsiblePerson

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**addressLine1** | **string** | The first line of the Responsible Person&#39;s street address.&lt;br&gt;&lt;br&gt;&lt;b&gt;Max length&lt;/b&gt;: 180 characters | [optional]
**addressLine2** | **string** | The second line of the Responsible Person&#39;s address. This field is not always used, but can be used for secondary address information such as &#39;Suite Number&#39; or &#39;Apt Number&#39;.&lt;br&gt;&lt;br&gt;&lt;b&gt;Max length&lt;/b&gt;: 180 characters | [optional]
**city** | **string** | The city of the Responsible Person&#39;s street address.&lt;br&gt;&lt;br&gt;&lt;b&gt;Max length&lt;/b&gt;: 64 characters | [optional]
**companyName** | **string** | The name of the Responsible Person or entity.&lt;br&gt;&lt;br&gt;&lt;b&gt;Max length&lt;/b&gt;: 100 characters | [optional]
**contactUrl** | **string** | The contact URL of the Responsible Person or entity.&lt;br&gt;&lt;br&gt;&lt;b&gt;Max length&lt;/b&gt;: 250 characters | [optional]
**country** | **string** | This defines the list of valid country codes, adapted from http://www.iso.org/iso/country_codes, ISO 3166-1 country code. List elements take the following form to identify a two-letter code with a short name in English, a three-digit code, and a three-letter code: For example, the entry for Japan includes Japan, 392, JPN. Short codes provide uniform recognition, avoiding language-dependent country names. The number code is helpful where Latin script may be problematic. Not all listed codes are universally recognized as countries, for example: code AQ is Antarctica, 010, ATA For implementation help, refer to &lt;a href&#x3D;&#39;https://developer.ebay.com/api-docs/sell/inventory/types/ba:CountryCodeEnum&#39;&gt;eBay API documentation&lt;/a&gt; | [optional]
**email** | **string** | The Responsible Person&#39;s email address.&lt;br&gt;&lt;br&gt;&lt;b&gt;Max length&lt;/b&gt;: 180 characters | [optional]
**phone** | **string** | The Responsible Person&#39;s business phone number.&lt;br&gt;&lt;br&gt;&lt;b&gt;Max length&lt;/b&gt;: 64 characters | [optional]
**postalCode** | **string** | The postal code of the Responsible Person&#39;s street address.&lt;br&gt;&lt;br&gt;&lt;b&gt;Max length&lt;/b&gt;: 9 characters | [optional]
**stateOrProvince** | **string** | The state of province of the Responsible Person&#39;s street address.&lt;br&gt;&lt;br&gt;&lt;b&gt;Max length&lt;/b&gt;: 64 characters | [optional]
**types** | **string[]** | The type(s) associated with the Responsible Person or entity.&lt;br&gt;&lt;br&gt;&lt;span class&#x3D;\&quot;tablenote\&quot;&gt;&lt;b&gt;Note:&lt;/b&gt; Currently, the only supported value is &lt;code&gt;EUResponsiblePerson&lt;/code&gt;.&lt;/span&gt; | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
