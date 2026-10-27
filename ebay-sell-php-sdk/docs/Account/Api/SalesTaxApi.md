# kruegge82\ebay\Account\SalesTaxApi

All URIs are relative to https://api.ebay.com/sell/account/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**bulkCreateOrReplaceSalesTax()**](SalesTaxApi.md#bulkCreateOrReplaceSalesTax) | **POST** /bulk_create_or_replace_sales_tax |  |
| [**createOrReplaceSalesTax()**](SalesTaxApi.md#createOrReplaceSalesTax) | **PUT** /sales_tax/{countryCode}/{jurisdictionId} |  |
| [**deleteSalesTax()**](SalesTaxApi.md#deleteSalesTax) | **DELETE** /sales_tax/{countryCode}/{jurisdictionId} |  |
| [**getSalesTax()**](SalesTaxApi.md#getSalesTax) | **GET** /sales_tax/{countryCode}/{jurisdictionId} |  |
| [**getSalesTaxes()**](SalesTaxApi.md#getSalesTaxes) | **GET** /sales_tax |  |


## `bulkCreateOrReplaceSalesTax()`

```php
bulkCreateOrReplaceSalesTax($bulkSalesTaxInput): \kruegge82\ebay\Account\Model\UpdatedSalesTaxResponse
```



This method creates or updates multiple sales-tax table entries.<br><br><i>Sales-tax tables</i> can be set up for countries that support different <i>tax jurisdictions</i>.<br><br><span class=\"tablenote\"><b>Note:</b> Sales-tax tables are only available for the US (EBAY_US) and Canada (EBAY_CA) marketplaces.</span><br>Each sales-tax table entry comprises the following parameters:<ul><li><code>countryCode</code></li><li><code>jurisdictionId</code></li><li><code>salesTaxPercentage</code></li><li><code>shippingAndHandlingTaxed</code></li></ul><br>Valid jurisdiction IDs are retrieved using <b><a href=\"/api-docs/sell/metadata/resources/country/methods/getSalesTaxJurisdictions\" target=\"_blank\">getSalesTaxJurisdictions</a></b> in the Metadata API.<br><br>For details about using this call, refer to <a href=\"/api-docs/sell/static/seller-accounts/tax-tables.html\">Establishing sales-tax tables</a>.<br><br><div class=\"msgbox_important\"><p class=\"msgbox_importantInDiv\" data-mc-autonum=\"&lt;b&gt;&lt;span style=&quot;color: #dd1e31;&quot; class=&quot;mcFormatColor&quot;&gt;Important! &lt;/span&gt;&lt;/b&gt;\"><span class=\"autonumber\"><span><b><span style=\"color: #dd1e31;\" class=\"mcFormatColor\">Important!</span></b></span></span> In the US, eBay now calculates, collects, and remits sales tax to the proper taxing authorities in all 50 states and Washington, DC. Sellers can no longer specify sales-tax rates for these jurisdictions using a tax table.<br><br>However, sellers may continue to use a sales-tax table to set rates for the following US territories:<ul><li>American Samoa (AS)</li><li>Guam (GU)</li><li>Northern Mariana Islands (MP)</li><li>Palau (PW)</li><li>US Virgin Islands (VI)</li></ul>For additional information, refer to <a href=\"https://www.ebay.com/help/selling/fees-credits-invoices/taxes-import-charges?id=4121 \" target=\"_blank\">Taxes and import charges</a>.</p></div>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = kruegge82\ebay\Account\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new kruegge82\ebay\Account\Api\SalesTaxApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$bulkSalesTaxInput = new \kruegge82\ebay\Account\Model\BulkSalesTaxInput(); // \kruegge82\ebay\Account\Model\BulkSalesTaxInput | List of sales taxes to be updated

try {
    $result = $apiInstance->bulkCreateOrReplaceSalesTax($bulkSalesTaxInput);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SalesTaxApi->bulkCreateOrReplaceSalesTax: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **bulkSalesTaxInput** | [**\kruegge82\ebay\Account\Model\BulkSalesTaxInput**](../Model/BulkSalesTaxInput.md)| List of sales taxes to be updated | |

### Return type

[**\kruegge82\ebay\Account\Model\UpdatedSalesTaxResponse**](../Model/UpdatedSalesTaxResponse.md)

### Authorization

[api_auth](../../README.md#api_auth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createOrReplaceSalesTax()`

```php
createOrReplaceSalesTax($countryCode, $jurisdictionId, $salesTaxBase)
```



This method creates or updates a sales-tax table entry for a jurisdiction. Specify the tax table entry you want to configure using the two path parameters: <b>countryCode</b> and <b>jurisdictionId</b>.  <br><br>A tax table entry for a jurisdiction is comprised of two fields: one for the jurisdiction's sales-tax rate and another that's a boolean value indicating whether or not shipping and handling are taxed in the jurisdiction.<br><br>You can set up <i>sales-tax tables</i> for countries that support different <i>tax jurisdictions</i>.<br><br><span class=\"tablenote\"><b>Note:</b> Sales-tax tables are only available for the US (EBAY_US) and Canada (EBAY_CA) marketplaces.</span><br>Retrieve valid jurisdiction IDs using <b><a href=\"/api-docs/sell/metadata/resources/country/methods/getSalesTaxJurisdictions\" target=\"_blank\">getSalesTaxJurisdictions</a></b> in the Metadata API.<br><br>For details about using this call, refer to <a href=\"/api-docs/sell/static/seller-accounts/tax-tables.html\">Establishing sales-tax tables</a>.<br><br><div class=\"msgbox_important\"><p class=\"msgbox_importantInDiv\" data-mc-autonum=\"&lt;b&gt;&lt;span style=&quot;color: #dd1e31;&quot; class=&quot;mcFormatColor&quot;&gt;Important! &lt;/span&gt;&lt;/b&gt;\"><span class=\"autonumber\"><span><b><span style=\"color: #dd1e31;\" class=\"mcFormatColor\">Important!</span></b></span></span> In the US, eBay now calculates, collects, and remits sales tax to the proper taxing authorities in all 50 states and Washington, DC. Sellers can no longer specify sales-tax rates for these jurisdictions using a tax table.<br><br>However, sellers may continue to use a sales-tax table to set rates for the following US territories:<ul><li>American Samoa (AS)</li><li>Guam (GU)</li><li>Northern Mariana Islands (MP)</li><li>Palau (PW)</li><li>US Virgin Islands (VI)</li></ul>For additional information, refer to <a href=\"https://www.ebay.com/help/selling/fees-credits-invoices/taxes-import-charges?id=4121 \" target=\"_blank\">Taxes and import charges</a>.</p></div>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = kruegge82\ebay\Account\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new kruegge82\ebay\Account\Api\SalesTaxApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$countryCode = 'countryCode_example'; // string | This path parameter specifies the two-letter <a href=\"https://www.iso.org/iso-3166-country-codes.html \" title=\"https://www.iso.org \" target=\"_blank\">ISO 3166</a> code for the country for which you want to create a sales tax table entry.<br><br><span class=\"tablenote\"><b>Note:</b> Sales-tax tables are available only for the US and Canada marketplaces. Therefore, the only supported values are:<ul><li><code>US</code></li><li><code>CA</code></li></ul></span>
$jurisdictionId = 'jurisdictionId_example'; // string | This path parameter specifies the ID of the tax jurisdiction for the table entry to be created.<br><br>Valid jurisdiction IDs can be retrieved using the <a href=\"/api-docs/sell/metadata/resources/country/methods/getSalesTaxJurisdictions\" target=\"_blank \">getSalesTaxJurisdiction</a> method of the Metadata API.<br><br><span class=\"tablenote\"><b>Note:</b> When <code>countryCode</code> is set to <code>US</code>, the only supported values for <code>jurisdictionId</code> are:<ul><li><code>AS</code> (American Samoa)</li><li><code>GU</code> (Guam)</li><li><code>MP</code> (Northern Mariana Islands)</li><li><code>PW</code> (Palau)</li><li><code>VI</code> (US Virgin Islands)</li></ul></span>
$salesTaxBase = new \kruegge82\ebay\Account\Model\SalesTaxBase(); // \kruegge82\ebay\Account\Model\SalesTaxBase | A container that describes the how the sales tax is calculated.

try {
    $apiInstance->createOrReplaceSalesTax($countryCode, $jurisdictionId, $salesTaxBase);
} catch (Exception $e) {
    echo 'Exception when calling SalesTaxApi->createOrReplaceSalesTax: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **countryCode** | **string**| This path parameter specifies the two-letter &lt;a href&#x3D;\&quot;https://www.iso.org/iso-3166-country-codes.html \&quot; title&#x3D;\&quot;https://www.iso.org \&quot; target&#x3D;\&quot;_blank\&quot;&gt;ISO 3166&lt;/a&gt; code for the country for which you want to create a sales tax table entry.&lt;br&gt;&lt;br&gt;&lt;span class&#x3D;\&quot;tablenote\&quot;&gt;&lt;b&gt;Note:&lt;/b&gt; Sales-tax tables are available only for the US and Canada marketplaces. Therefore, the only supported values are:&lt;ul&gt;&lt;li&gt;&lt;code&gt;US&lt;/code&gt;&lt;/li&gt;&lt;li&gt;&lt;code&gt;CA&lt;/code&gt;&lt;/li&gt;&lt;/ul&gt;&lt;/span&gt; | |
| **jurisdictionId** | **string**| This path parameter specifies the ID of the tax jurisdiction for the table entry to be created.&lt;br&gt;&lt;br&gt;Valid jurisdiction IDs can be retrieved using the &lt;a href&#x3D;\&quot;/api-docs/sell/metadata/resources/country/methods/getSalesTaxJurisdictions\&quot; target&#x3D;\&quot;_blank \&quot;&gt;getSalesTaxJurisdiction&lt;/a&gt; method of the Metadata API.&lt;br&gt;&lt;br&gt;&lt;span class&#x3D;\&quot;tablenote\&quot;&gt;&lt;b&gt;Note:&lt;/b&gt; When &lt;code&gt;countryCode&lt;/code&gt; is set to &lt;code&gt;US&lt;/code&gt;, the only supported values for &lt;code&gt;jurisdictionId&lt;/code&gt; are:&lt;ul&gt;&lt;li&gt;&lt;code&gt;AS&lt;/code&gt; (American Samoa)&lt;/li&gt;&lt;li&gt;&lt;code&gt;GU&lt;/code&gt; (Guam)&lt;/li&gt;&lt;li&gt;&lt;code&gt;MP&lt;/code&gt; (Northern Mariana Islands)&lt;/li&gt;&lt;li&gt;&lt;code&gt;PW&lt;/code&gt; (Palau)&lt;/li&gt;&lt;li&gt;&lt;code&gt;VI&lt;/code&gt; (US Virgin Islands)&lt;/li&gt;&lt;/ul&gt;&lt;/span&gt; | |
| **salesTaxBase** | [**\kruegge82\ebay\Account\Model\SalesTaxBase**](../Model/SalesTaxBase.md)| A container that describes the how the sales tax is calculated. | |

### Return type

void (empty response body)

### Authorization

[api_auth](../../README.md#api_auth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteSalesTax()`

```php
deleteSalesTax($countryCode, $jurisdictionId)
```



This call deletes a sales-tax table entry for a jurisdiction. Specify the jurisdiction to delete using the <b>countryCode</b> and <b>jurisdictionId</b> path parameters.<br><br><span class=\"tablenote\"><b>Note:</b> Sales-tax tables are only available for the US (EBAY_US) and Canada (EBAY_CA) marketplaces.</span>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = kruegge82\ebay\Account\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new kruegge82\ebay\Account\Api\SalesTaxApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$countryCode = 'countryCode_example'; // string | This path parameter specifies the two-letter <a href=\"https://www.iso.org/iso-3166-country-codes.html \" title=\"https://www.iso.org \" target=\"_blank\">ISO 3166</a> code for the country whose sales tax table entry you want to delete.<br><br><span class=\"tablenote\"><b>Note:</b> Sales-tax tables are available only for the US and Canada marketplaces. Therefore, the only supported values are:<ul><li><code>US</code></li><li><code>CA</code></li></ul></span>
$jurisdictionId = 'jurisdictionId_example'; // string | This path parameter specifies the ID of the sales tax jurisdiction whose table entry you want to delete.<br><br>Valid jurisdiction IDs can be retrieved using the <a href=\"/api-docs/sell/metadata/resources/country/methods/getSalesTaxJurisdictions\" target=\"_blank \">getSalesTaxJurisdiction</a> method of the Metadata API.<br><br><span class=\"tablenote\"><b>Note:</b> When <code>countryCode</code> is set to <code>US</code>, the only supported values for <code>jurisdictionId</code> are:<ul><li><code>AS</code> (American Samoa)</li><li><code>GU</code> (Guam)</li><li><code>MP</code> (Northern Mariana Islands)</li><li><code>PW</code> (Palau)</li><li><code>VI</code> (US Virgin Islands)</li></ul></span>

try {
    $apiInstance->deleteSalesTax($countryCode, $jurisdictionId);
} catch (Exception $e) {
    echo 'Exception when calling SalesTaxApi->deleteSalesTax: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **countryCode** | **string**| This path parameter specifies the two-letter &lt;a href&#x3D;\&quot;https://www.iso.org/iso-3166-country-codes.html \&quot; title&#x3D;\&quot;https://www.iso.org \&quot; target&#x3D;\&quot;_blank\&quot;&gt;ISO 3166&lt;/a&gt; code for the country whose sales tax table entry you want to delete.&lt;br&gt;&lt;br&gt;&lt;span class&#x3D;\&quot;tablenote\&quot;&gt;&lt;b&gt;Note:&lt;/b&gt; Sales-tax tables are available only for the US and Canada marketplaces. Therefore, the only supported values are:&lt;ul&gt;&lt;li&gt;&lt;code&gt;US&lt;/code&gt;&lt;/li&gt;&lt;li&gt;&lt;code&gt;CA&lt;/code&gt;&lt;/li&gt;&lt;/ul&gt;&lt;/span&gt; | |
| **jurisdictionId** | **string**| This path parameter specifies the ID of the sales tax jurisdiction whose table entry you want to delete.&lt;br&gt;&lt;br&gt;Valid jurisdiction IDs can be retrieved using the &lt;a href&#x3D;\&quot;/api-docs/sell/metadata/resources/country/methods/getSalesTaxJurisdictions\&quot; target&#x3D;\&quot;_blank \&quot;&gt;getSalesTaxJurisdiction&lt;/a&gt; method of the Metadata API.&lt;br&gt;&lt;br&gt;&lt;span class&#x3D;\&quot;tablenote\&quot;&gt;&lt;b&gt;Note:&lt;/b&gt; When &lt;code&gt;countryCode&lt;/code&gt; is set to &lt;code&gt;US&lt;/code&gt;, the only supported values for &lt;code&gt;jurisdictionId&lt;/code&gt; are:&lt;ul&gt;&lt;li&gt;&lt;code&gt;AS&lt;/code&gt; (American Samoa)&lt;/li&gt;&lt;li&gt;&lt;code&gt;GU&lt;/code&gt; (Guam)&lt;/li&gt;&lt;li&gt;&lt;code&gt;MP&lt;/code&gt; (Northern Mariana Islands)&lt;/li&gt;&lt;li&gt;&lt;code&gt;PW&lt;/code&gt; (Palau)&lt;/li&gt;&lt;li&gt;&lt;code&gt;VI&lt;/code&gt; (US Virgin Islands)&lt;/li&gt;&lt;/ul&gt;&lt;/span&gt; | |

### Return type

void (empty response body)

### Authorization

[api_auth](../../README.md#api_auth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getSalesTax()`

```php
getSalesTax($countryCode, $jurisdictionId): \kruegge82\ebay\Account\Model\SalesTax
```



This call retrieves the current sales-tax table entry for a specific tax jurisdiction. Specify the jurisdiction to retrieve using the <b>countryCode</b> and <b>jurisdictionId</b> path parameters. All four response fields will be returned if a sales-tax entry exists for the tax jurisdiction. Otherwise, the response will be returned as empty.<br><br><span class=\"tablenote\"><b>Note:</b> Sales-tax tables are only available for the US (EBAY_US) and Canada (EBAY_CA) marketplaces.</span><br><div class=\"msgbox_important\"><p class=\"msgbox_importantInDiv\" data-mc-autonum=\"&lt;b&gt;&lt;span style=&quot;color: #dd1e31;&quot; class=&quot;mcFormatColor&quot;&gt;Important! &lt;/span&gt;&lt;/b&gt;\"><span class=\"autonumber\"><span><b><span style=\"color: #dd1e31;\" class=\"mcFormatColor\">Important!</span></b></span></span> In the US, eBay now calculates, collects, and remits sales tax to the proper taxing authorities in all 50 states and Washington, DC. Sellers can no longer specify sales-tax rates for these jurisdictions using a tax table.<br><br>However, sellers may continue to use a sales-tax table to set rates for the following US territories:<ul><li>American Samoa (AS)</li><li>Guam (GU)</li><li>Northern Mariana Islands (MP)</li><li>Palau (PW)</li><li>US Virgin Islands (VI)</li></ul>For additional information, refer to <a href=\"https://www.ebay.com/help/selling/fees-credits-invoices/taxes-import-charges?id=4121 \" target=\"_blank\">Taxes and import charges</a>.</p></div>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = kruegge82\ebay\Account\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new kruegge82\ebay\Account\Api\SalesTaxApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$countryCode = 'countryCode_example'; // string | This path parameter specifies the two-letter <a href=\"https://www.iso.org/iso-3166-country-codes.html \" title=\"https://www.iso.org \" target=\"_blank\">ISO 3166</a> code for the country whose sales tax table you want to retrieve.<br><br><span class=\"tablenote\"><b>Note:</b> Sales-tax tables are available only for the US and Canada marketplaces. Therefore, the only supported values are:<ul><li><code>US</code></li><li><code>CA</code></li></ul></span>
$jurisdictionId = 'jurisdictionId_example'; // string | This path parameter specifies the ID of the sales tax jurisdiction for the tax table entry to be retrieved.<br><br>Valid jurisdiction IDs can be retrieved using the <a href=\"/api-docs/sell/metadata/resources/country/methods/getSalesTaxJurisdictions\" target=\"_blank \">getSalesTaxJurisdiction</a> method of the Metadata API.<br><br><span class=\"tablenote\"><b>Note:</b> When <code>countryCode</code> is set to <code>US</code>, the only supported values for <code>jurisdictionId</code> are:<ul><li><code>AS</code> (American Samoa)</li><li><code>GU</code> (Guam</li><li><code>MP</code> Northern Mariana Islands</li><li><code>PW (Palau)</li><li><code>VI</code> (US Virgin Islands)</li></ul></span>

try {
    $result = $apiInstance->getSalesTax($countryCode, $jurisdictionId);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SalesTaxApi->getSalesTax: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **countryCode** | **string**| This path parameter specifies the two-letter &lt;a href&#x3D;\&quot;https://www.iso.org/iso-3166-country-codes.html \&quot; title&#x3D;\&quot;https://www.iso.org \&quot; target&#x3D;\&quot;_blank\&quot;&gt;ISO 3166&lt;/a&gt; code for the country whose sales tax table you want to retrieve.&lt;br&gt;&lt;br&gt;&lt;span class&#x3D;\&quot;tablenote\&quot;&gt;&lt;b&gt;Note:&lt;/b&gt; Sales-tax tables are available only for the US and Canada marketplaces. Therefore, the only supported values are:&lt;ul&gt;&lt;li&gt;&lt;code&gt;US&lt;/code&gt;&lt;/li&gt;&lt;li&gt;&lt;code&gt;CA&lt;/code&gt;&lt;/li&gt;&lt;/ul&gt;&lt;/span&gt; | |
| **jurisdictionId** | **string**| This path parameter specifies the ID of the sales tax jurisdiction for the tax table entry to be retrieved.&lt;br&gt;&lt;br&gt;Valid jurisdiction IDs can be retrieved using the &lt;a href&#x3D;\&quot;/api-docs/sell/metadata/resources/country/methods/getSalesTaxJurisdictions\&quot; target&#x3D;\&quot;_blank \&quot;&gt;getSalesTaxJurisdiction&lt;/a&gt; method of the Metadata API.&lt;br&gt;&lt;br&gt;&lt;span class&#x3D;\&quot;tablenote\&quot;&gt;&lt;b&gt;Note:&lt;/b&gt; When &lt;code&gt;countryCode&lt;/code&gt; is set to &lt;code&gt;US&lt;/code&gt;, the only supported values for &lt;code&gt;jurisdictionId&lt;/code&gt; are:&lt;ul&gt;&lt;li&gt;&lt;code&gt;AS&lt;/code&gt; (American Samoa)&lt;/li&gt;&lt;li&gt;&lt;code&gt;GU&lt;/code&gt; (Guam&lt;/li&gt;&lt;li&gt;&lt;code&gt;MP&lt;/code&gt; Northern Mariana Islands&lt;/li&gt;&lt;li&gt;&lt;code&gt;PW (Palau)&lt;/li&gt;&lt;li&gt;&lt;code&gt;VI&lt;/code&gt; (US Virgin Islands)&lt;/li&gt;&lt;/ul&gt;&lt;/span&gt; | |

### Return type

[**\kruegge82\ebay\Account\Model\SalesTax**](../Model/SalesTax.md)

### Authorization

[api_auth](../../README.md#api_auth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getSalesTaxes()`

```php
getSalesTaxes($countryCode): \kruegge82\ebay\Account\Model\SalesTaxes
```



Use this call to retrieve all sales tax table entries that the seller has defined for a specific country. All four response fields will be returned for each tax jurisdiction that matches the search criteria. If no sales tax rates are defined for the specified, a <code>204 No Content</code> status code is returned with no response payload.<br><br><span class=\"tablenote\"><b>Note:</b> Sales-tax tables are only available for the US (EBAY_US) and Canada (EBAY_CA) marketplaces.</span><br><div class=\"msgbox_important\"><p class=\"msgbox_importantInDiv\" data-mc-autonum=\"&lt;b&gt;&lt;span style=&quot;color: #dd1e31;&quot; class=&quot;mcFormatColor&quot;&gt;Important! &lt;/span&gt;&lt;/b&gt;\"><span class=\"autonumber\"><span><b><span style=\"color: #dd1e31;\" class=\"mcFormatColor\">Important!</span></b></span></span> In the US, eBay now calculates, collects, and remits sales tax to the proper taxing authorities in all 50 states and Washington, DC. Sellers can no longer specify sales-tax rates for these jurisdictions using a tax table.<br><br>However, sellers may continue to use a sales-tax table to set rates for the following US territories:<ul><li>American Samoa (AS)</li><li>Guam (GU)</li><li>Northern Mariana Islands (MP)</li><li>Palau (PW)</li><li>US Virgin Islands (VI)</li></ul>For additional information, refer to <a href=\"https://www.ebay.com/help/selling/fees-credits-invoices/taxes-import-charges?id=4121 \" target=\"_blank\">Taxes and import charges</a>.</p></div>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = kruegge82\ebay\Account\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new kruegge82\ebay\Account\Api\SalesTaxApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$countryCode = 'countryCode_example'; // string | This path parameter specifies the two-letter <a href=\"https://www.iso.org/iso-3166-country-codes.html \" title=\"https://www.iso.org \" target=\"_blank\">ISO 3166</a> code for the country whose tax table you want to retrieve.<br><br><span class=\"tablenote\"><b>Note:</b> Sales-tax tables are available only for the US and Canada marketplaces. Therefore, the only supported values are:<ul><li><code>US</code></li><li><code>CA</code></li></ul></span> For implementation help, refer to eBay API documentation at https://developer.ebay.com/api-docs/sell/account/types/ba:CountryCodeEnum

try {
    $result = $apiInstance->getSalesTaxes($countryCode);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SalesTaxApi->getSalesTaxes: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **countryCode** | **string**| This path parameter specifies the two-letter &lt;a href&#x3D;\&quot;https://www.iso.org/iso-3166-country-codes.html \&quot; title&#x3D;\&quot;https://www.iso.org \&quot; target&#x3D;\&quot;_blank\&quot;&gt;ISO 3166&lt;/a&gt; code for the country whose tax table you want to retrieve.&lt;br&gt;&lt;br&gt;&lt;span class&#x3D;\&quot;tablenote\&quot;&gt;&lt;b&gt;Note:&lt;/b&gt; Sales-tax tables are available only for the US and Canada marketplaces. Therefore, the only supported values are:&lt;ul&gt;&lt;li&gt;&lt;code&gt;US&lt;/code&gt;&lt;/li&gt;&lt;li&gt;&lt;code&gt;CA&lt;/code&gt;&lt;/li&gt;&lt;/ul&gt;&lt;/span&gt; For implementation help, refer to eBay API documentation at https://developer.ebay.com/api-docs/sell/account/types/ba:CountryCodeEnum | |

### Return type

[**\kruegge82\ebay\Account\Model\SalesTaxes**](../Model/SalesTaxes.md)

### Authorization

[api_auth](../../README.md#api_auth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
