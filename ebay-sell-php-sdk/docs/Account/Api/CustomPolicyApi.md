# kruegge82\ebay\Account\CustomPolicyApi

All URIs are relative to https://api.ebay.com/sell/account/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createCustomPolicy()**](CustomPolicyApi.md#createCustomPolicy) | **POST** /custom_policy/ |  |
| [**getCustomPolicies()**](CustomPolicyApi.md#getCustomPolicies) | **GET** /custom_policy/ |  |
| [**getCustomPolicy()**](CustomPolicyApi.md#getCustomPolicy) | **GET** /custom_policy/{custom_policy_id} |  |
| [**updateCustomPolicy()**](CustomPolicyApi.md#updateCustomPolicy) | **PUT** /custom_policy/{custom_policy_id} |  |


## `createCustomPolicy()`

```php
createCustomPolicy($customPolicyCreateRequest): object
```



This method creates a new custom policy that specifies the seller's terms for complying with local governmental regulations. Each Custom Policy targets a <b>policyType</b>. Multiple policies may be created as using the following custom policy types:<ul><li>PRODUCT_COMPLIANCE: Product Compliance policies disclose product information as required for regulatory compliance. <br/><br/><span class=\"tablenote\"><strong>Note:</strong> A maximum of 60 Product Compliance policies per seller may be created.</span></li><li>TAKE_BACK: Takeback policies describe the seller's legal obligation to take back a previously purchased item when the buyer purchases a new one. <br/><br/><span class=\"tablenote\"><strong>Note:</strong> A maximum of 18 Takeback policies per seller may be created.</span></li></ul>A successful create policy call returns an HTTP status code of <b>201 Created</b> with the system-generated policy ID included in the Location response header.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = kruegge82\ebay\Account\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new kruegge82\ebay\Account\Api\CustomPolicyApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$customPolicyCreateRequest = new \kruegge82\ebay\Account\Model\CustomPolicyCreateRequest(); // \kruegge82\ebay\Account\Model\CustomPolicyCreateRequest | Request to create a new Custom Policy.

try {
    $result = $apiInstance->createCustomPolicy($customPolicyCreateRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CustomPolicyApi->createCustomPolicy: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **customPolicyCreateRequest** | [**\kruegge82\ebay\Account\Model\CustomPolicyCreateRequest**](../Model/CustomPolicyCreateRequest.md)| Request to create a new Custom Policy. | |

### Return type

**object**

### Authorization

[api_auth](../../README.md#api_auth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getCustomPolicies()`

```php
getCustomPolicies($policyTypes): \kruegge82\ebay\Account\Model\CustomPolicyResponse
```



This method retrieves the list of custom policies defined for a seller's account. To limit the returned custom policies, specify the <b>policy_types</b> query parameter.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = kruegge82\ebay\Account\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new kruegge82\ebay\Account\Api\CustomPolicyApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$policyTypes = 'policyTypes_example'; // string | This query parameter specifies the type of custom policies to be returned.<br><br>Multiple policy types may be requested in a single call by providing a comma-delimited set of all policy types to be returned.<br><br><span class=\"tablenote\"><strong>Note:</strong> Omitting this query parameter from a request will also return policies of all policy types.</span><br> See the <a href=\"/api-docs/sell/account/types/api:CustomPolicyTypeEnum\" target=\"_blank \">CustomPolicyTypeEnum</a> type for a list of supported values.

try {
    $result = $apiInstance->getCustomPolicies($policyTypes);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CustomPolicyApi->getCustomPolicies: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **policyTypes** | **string**| This query parameter specifies the type of custom policies to be returned.&lt;br&gt;&lt;br&gt;Multiple policy types may be requested in a single call by providing a comma-delimited set of all policy types to be returned.&lt;br&gt;&lt;br&gt;&lt;span class&#x3D;\&quot;tablenote\&quot;&gt;&lt;strong&gt;Note:&lt;/strong&gt; Omitting this query parameter from a request will also return policies of all policy types.&lt;/span&gt;&lt;br&gt; See the &lt;a href&#x3D;\&quot;/api-docs/sell/account/types/api:CustomPolicyTypeEnum\&quot; target&#x3D;\&quot;_blank \&quot;&gt;CustomPolicyTypeEnum&lt;/a&gt; type for a list of supported values. | [optional] |

### Return type

[**\kruegge82\ebay\Account\Model\CustomPolicyResponse**](../Model/CustomPolicyResponse.md)

### Authorization

[api_auth](../../README.md#api_auth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getCustomPolicy()`

```php
getCustomPolicy($customPolicyId): \kruegge82\ebay\Account\Model\CustomPolicy
```



This method retrieves the custom policy specified by the <b>custom_policy_id</b> path parameter.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = kruegge82\ebay\Account\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new kruegge82\ebay\Account\Api\CustomPolicyApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$customPolicyId = 'customPolicyId_example'; // string | This path parameter is the unique identifier of the custom policy to retrieve.<br><br> This ID can be retrieved for a custom policy by using the <a href=\"/api-docs/sell/account/resources/custom_policy/methods/getCustomPolicies\" target=\"_blank \">getCustomPolicies</a> method.

try {
    $result = $apiInstance->getCustomPolicy($customPolicyId);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CustomPolicyApi->getCustomPolicy: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **customPolicyId** | **string**| This path parameter is the unique identifier of the custom policy to retrieve.&lt;br&gt;&lt;br&gt; This ID can be retrieved for a custom policy by using the &lt;a href&#x3D;\&quot;/api-docs/sell/account/resources/custom_policy/methods/getCustomPolicies\&quot; target&#x3D;\&quot;_blank \&quot;&gt;getCustomPolicies&lt;/a&gt; method. | |

### Return type

[**\kruegge82\ebay\Account\Model\CustomPolicy**](../Model/CustomPolicy.md)

### Authorization

[api_auth](../../README.md#api_auth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateCustomPolicy()`

```php
updateCustomPolicy($customPolicyId, $customPolicyRequest)
```



This method updates an existing custom policy specified by the <b>custom_policy_id</b> path parameter. Since this method overwrites the policy's <b>name</b>, <b>label</b>, and <b>description</b> fields, always include the complete and current text of all three policy fields in the request payload, even if they are not being updated.<br/> <br/>For example, the value for the <b>label</b> field is to be updated, but the <b>name</b> and <b>description</b> values will remain unchanged. The existing <b>name</b> and <b>description</b> values, as they are defined in the current policy, must also be passed in. <br/><br/>A successful policy update call returns an HTTP status code of <b>204 No Content</b>.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = kruegge82\ebay\Account\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new kruegge82\ebay\Account\Api\CustomPolicyApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$customPolicyId = 'customPolicyId_example'; // string | This path parameter is the unique identifier of the custom policy to update.<br><br><span class=\"tablenote\"><b>Note:</b> A list of custom policies defined for a seller's account that includes this ID can be retrieved by calling the <a href=\"/api-docs/sell/account/resources/custom_policy/methods/getCustomPolicies\" target=\"_blank \">getCustomPolicies</a> method.</span>
$customPolicyRequest = new \kruegge82\ebay\Account\Model\CustomPolicyRequest(); // \kruegge82\ebay\Account\Model\CustomPolicyRequest | Request to update a current custom policy.

try {
    $apiInstance->updateCustomPolicy($customPolicyId, $customPolicyRequest);
} catch (Exception $e) {
    echo 'Exception when calling CustomPolicyApi->updateCustomPolicy: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **customPolicyId** | **string**| This path parameter is the unique identifier of the custom policy to update.&lt;br&gt;&lt;br&gt;&lt;span class&#x3D;\&quot;tablenote\&quot;&gt;&lt;b&gt;Note:&lt;/b&gt; A list of custom policies defined for a seller&#39;s account that includes this ID can be retrieved by calling the &lt;a href&#x3D;\&quot;/api-docs/sell/account/resources/custom_policy/methods/getCustomPolicies\&quot; target&#x3D;\&quot;_blank \&quot;&gt;getCustomPolicies&lt;/a&gt; method.&lt;/span&gt; | |
| **customPolicyRequest** | [**\kruegge82\ebay\Account\Model\CustomPolicyRequest**](../Model/CustomPolicyRequest.md)| Request to update a current custom policy. | |

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
