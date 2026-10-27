# kruegge82\ebay\Account\PaymentsProgramApi

All URIs are relative to https://api.ebay.com/sell/account/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getPaymentsProgram()**](PaymentsProgramApi.md#getPaymentsProgram) | **GET** /payments_program/{marketplace_id}/{payments_program_type} |  |


## `getPaymentsProgram()`

```php
getPaymentsProgram($marketplaceId, $paymentsProgramType): \kruegge82\ebay\Account\Model\PaymentsProgramResponse
```



<span class=\"tablenote\"><b>Note:</b> This method is no longer applicable, as all seller accounts globally have been enabled for the new eBay payment and checkout flow.</span><br>This method returns whether or not the user is opted-in to the specified payments program. Sellers opt-in to payments programs by marketplace and you use the <b>marketplace_id</b> path parameter to specify the marketplace of the status flag you want returned.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = kruegge82\ebay\Account\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new kruegge82\ebay\Account\Api\PaymentsProgramApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$marketplaceId = 'marketplaceId_example'; // string | This path parameter specifies the eBay marketplace of the payments program for which you want to retrieve the seller's status.
$paymentsProgramType = 'paymentsProgramType_example'; // string | This path parameter specifies the payments program whose status is returned by the call.

try {
    $result = $apiInstance->getPaymentsProgram($marketplaceId, $paymentsProgramType);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PaymentsProgramApi->getPaymentsProgram: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **marketplaceId** | **string**| This path parameter specifies the eBay marketplace of the payments program for which you want to retrieve the seller&#39;s status. | |
| **paymentsProgramType** | **string**| This path parameter specifies the payments program whose status is returned by the call. | |

### Return type

[**\kruegge82\ebay\Account\Model\PaymentsProgramResponse**](../Model/PaymentsProgramResponse.md)

### Authorization

[api_auth](../../README.md#api_auth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
