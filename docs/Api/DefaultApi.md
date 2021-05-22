# Swagger\Client\DefaultApi

All URIs are relative to *https://www.buda.com/*

Method | HTTP request | Description
------------- | ------------- | -------------
[**apiV2BalancesGet**](DefaultApi.md#apiv2balancesget) | **GET** /api/v2/balances | 
[**apiV2MarketsGet**](DefaultApi.md#apiv2marketsget) | **GET** /api/v2/markets | 
[**apiV2MarketsMarketIdTickerGet**](DefaultApi.md#apiv2marketsmarketidtickerget) | **GET** /api/v2/markets/{market_id}/ticker | 

# **apiV2BalancesGet**
> apiV2BalancesGet($x_sbtc_apikey, $x_sbtc_nonce, $x_sbtc_signature)



Muestra los balances de tu cuenta, en cada moneda.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\DefaultApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$x_sbtc_apikey = "x_sbtc_apikey_example"; // string | Market ID
$x_sbtc_nonce = "x_sbtc_nonce_example"; // string | 
$x_sbtc_signature = "x_sbtc_signature_example"; // string | 

try {
    $apiInstance->apiV2BalancesGet($x_sbtc_apikey, $x_sbtc_nonce, $x_sbtc_signature);
} catch (Exception $e) {
    echo 'Exception when calling DefaultApi->apiV2BalancesGet: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_sbtc_apikey** | **string**| Market ID |
 **x_sbtc_nonce** | **string**|  |
 **x_sbtc_signature** | **string**|  |

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **apiV2MarketsGet**
> apiV2MarketsGet()



Un mercado permite separar las compras y ventas por moneda. En un mercado se compra y vende un tipo de moneda (base_currency) y se usa otro tipo de moneda para pagar por estas compras y ventas (quote_currency). Por lo tanto, un mercado está identificado por las siglas que representa a este par de monedas. Por ejemplo: el nombre del mercado en el cual se transan ethers (ETH) contra bitcoins (BTC) es: eth-btc.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\DefaultApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $apiInstance->apiV2MarketsGet();
} catch (Exception $e) {
    echo 'Exception when calling DefaultApi->apiV2MarketsGet: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters
This endpoint does not need any parameter.

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **apiV2MarketsMarketIdTickerGet**
> apiV2MarketsMarketIdTickerGet($market_id)



El ticker permite ver el estado actual de un determinado mercado. La respuesta a esta llamada entrega las mejores ofertas de compra y venta (bid y ask), asi como el precio de la ultima transacción (last_price) para el mercado solicitado. También incluye información como el volumen diario y cuanto ha cambiado el precio en las últimas 24 hrs.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\DefaultApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$market_id = "market_id_example"; // string | Market ID

try {
    $apiInstance->apiV2MarketsMarketIdTickerGet($market_id);
} catch (Exception $e) {
    echo 'Exception when calling DefaultApi->apiV2MarketsMarketIdTickerGet: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **market_id** | **string**| Market ID |

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

