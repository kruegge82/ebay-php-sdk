# # RefundItem

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**refundAmount** | [**\kruegge82\ebay\Fulfillment\Model\SimpleAmount**](SimpleAmount.md) |  | [optional]
**lineItemId** | **string** | The unique identifier of an order line item. This identifier is created once a buyer purchases a &#39;Buy It Now&#39; item or if an auction listing ends with a winning bidder.&lt;br&gt;&lt;br&gt;Either this field or the &lt;b&gt;legacyReference&lt;/b&gt; container is needed to identify an individual order line item that will receive a refund.&lt;br&gt;&lt;br&gt; This value is returned using the &lt;a href&#x3D;\&quot;/api-docs/sell/fulfillment/resources/order/methods/getOrders\&quot; target&#x3D;\&quot;_blank \&quot;&gt;getOrders&lt;/a&gt; method. | [optional]
**legacyReference** | [**\kruegge82\ebay\Fulfillment\Model\LegacyReference**](LegacyReference.md) |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
