# kruegge82\ebay\Account\SubscriptionApi

All URIs are relative to https://api.ebay.com/sell/account/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getSubscription()**](SubscriptionApi.md#getSubscription) | **GET** /subscription |  |


## `getSubscription()`

```php
getSubscription($limit, $continuationToken): \kruegge82\ebay\Account\Model\SubscriptionResponse
```



This method retrieves a list of subscriptions associated with the seller account.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = kruegge82\ebay\Account\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new kruegge82\ebay\Account\Api\SubscriptionApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$limit = 'limit_example'; // string | This field is for future use.
$continuationToken = 'continuationToken_example'; // string | This field is for future use.

try {
    $result = $apiInstance->getSubscription($limit, $continuationToken);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SubscriptionApi->getSubscription: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **limit** | **string**| This field is for future use. | [optional] |
| **continuationToken** | **string**| This field is for future use. | [optional] |

### Return type

[**\kruegge82\ebay\Account\Model\SubscriptionResponse**](../Model/SubscriptionResponse.md)

### Authorization

[api_auth](../../README.md#api_auth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
