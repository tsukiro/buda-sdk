# Tsukiro\Client\BudaApi

All URIs are relative to *https://www.buda.com*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*BudaApi* | [**getBalances**](docs/Api/BudaApi.md#getBalances) | **GET** /api/v2/balances | 
*BudaApi* | [**getMarkets**](docs/Api/BudaApi.md#getMarkets) | **GET** /api/v2/markets | 
*BudaApi* | [**getTicker**](docs/Api/BudaApi.md#getTicker) | **GET** /api/v2/markets/{market_id}/ticker | 

# **getBalances**
> getBalances($x_sbtc_apikey, $x_sbtc_nonce, $x_sbtc_signature)



Muestra los balances de tu cuenta, en cada moneda.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Tsukiro\Client\Api\BudaApi();

try {
    $apiInstance->setApiKey("YOUR_APIKEY");
    $apiInstance->setSecret("YOUR_SECRET");
    $response =  $apiInstance->getBalance();
    list($body, $statusCode, $headers) = $response;
} catch (Exception $e) {
    echo 'Exception when calling BudaApi->getBalances: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Return Body Example

```
{
  "balances": [
    {
      "id": "BTC",
      "amount": [
        "0.00097227",
        "BTC"
      ],
      "available_amount": [
        "0.00097227",
        "BTC"
      ],
      "frozen_amount": [
        "0.0",
        "BTC"
      ],
      "pending_withdraw_amount": [
        "0.0",
        "BTC"
      ],
      "account_id": 244479
    },
    {
      "id": "CLP",
      "amount": [
        "0.0",
        "CLP"
      ],
      "available_amount": [
        "0.0",
        "CLP"
      ],
      "frozen_amount": [
        "0.0",
        "CLP"
      ],
      "pending_withdraw_amount": [
        "0.0",
        "CLP"
      ],
      "account_id": 244479
    },
    {
      "id": "ETH",
      "amount": [
        "0.074392188",
        "ETH"
      ],
      "available_amount": [
        "0.074392188",
        "ETH"
      ],
      "frozen_amount": [
        "0.0",
        "ETH"
      ],
      "pending_withdraw_amount": [
        "0.0",
        "ETH"
      ],
      "account_id": 244479
    }
  ]
}
```


### Authorization

Recuerda haber seteado los parámetros : 

```
    $apiInstance->setApiKey("YOUR_APIKEY");
    $apiInstance->setSecret("YOUR_SECRET");
```

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

# **getMarkets**
> getMarkets()


Un mercado permite separar las compras y ventas por moneda. En un mercado se compra y vende un tipo de moneda (base_currency) y se usa otro tipo de moneda para pagar por estas compras y ventas (quote_currency). Por lo tanto, un mercado está identificado por las siglas que representa a este par de monedas. Por ejemplo: el nombre del mercado en el cual se transan ethers (ETH) contra bitcoins (BTC) es: eth-btc.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Tsukiro\Client\Api\BudaApi();

try {
    $response = $apiInstance->getMarkets();
    list($markets, $statusCode, $headers) = $response;
} catch (Exception $e) {
    echo 'Exception when calling BudaApi->getMarkets: ', $e->getMessage(), PHP_EOL;
}
?>
```
### Return Body Example
```
{
  "markets": [
    {
      "id": "BTC-CLP",
      "name": "btc-clp",
      "base_currency": "BTC",
      "quote_currency": "CLP",
      "minimum_order_amount": [
        "0.00002",
        "BTC"
      ],
      "disabled": false,
      "illiquid": false,
      "rpo_disabled": null
    },
    {
      "id": "BTC-COP",
      "name": "btc-cop",
      "base_currency": "BTC",
      "quote_currency": "COP",
      "minimum_order_amount": [
        "0.00002",
        "BTC"
      ],
      "disabled": false,
      "illiquid": false,
      "rpo_disabled": null
    },
    {
      "id": "ETH-CLP",
      "name": "eth-clp",
      "base_currency": "ETH",
      "quote_currency": "CLP",
      "minimum_order_amount": [
        "0.001",
        "ETH"
      ],
      "disabled": false,
      "illiquid": false,
      "rpo_disabled": null
    },
    {
      "id": "ETH-BTC",
      "name": "eth-btc",
      "base_currency": "ETH",
      "quote_currency": "BTC",
      "minimum_order_amount": [
        "0.001",
        "ETH"
      ],
      "disabled": false,
      "illiquid": false,
      "rpo_disabled": null
    },
    {
      "id": "BTC-PEN",
      "name": "btc-pen",
      "base_currency": "BTC",
      "quote_currency": "PEN",
      "minimum_order_amount": [
        "0.00002",
        "BTC"
      ],
      "disabled": false,
      "illiquid": false,
      "rpo_disabled": null
    },
    {
      "id": "ETH-PEN",
      "name": "eth-pen",
      "base_currency": "ETH",
      "quote_currency": "PEN",
      "minimum_order_amount": [
        "0.001",
        "ETH"
      ],
      "disabled": false,
      "illiquid": false,
      "rpo_disabled": false
    },
    {
      "id": "ETH-COP",
      "name": "eth-cop",
      "base_currency": "ETH",
      "quote_currency": "COP",
      "minimum_order_amount": [
        "0.001",
        "ETH"
      ],
      "disabled": false,
      "illiquid": false,
      "rpo_disabled": null
    },
    {
      "id": "BCH-BTC",
      "name": "bch-btc",
      "base_currency": "BCH",
      "quote_currency": "BTC",
      "minimum_order_amount": [
        "0.001",
        "BCH"
      ],
      "disabled": false,
      "illiquid": false,
      "rpo_disabled": null
    },
    {
      "id": "BCH-CLP",
      "name": "bch-clp",
      "base_currency": "BCH",
      "quote_currency": "CLP",
      "minimum_order_amount": [
        "0.001",
        "BCH"
      ],
      "disabled": false,
      "illiquid": false,
      "rpo_disabled": null
    },
    {
      "id": "BCH-COP",
      "name": "bch-cop",
      "base_currency": "BCH",
      "quote_currency": "COP",
      "minimum_order_amount": [
        "0.001",
        "BCH"
      ],
      "disabled": false,
      "illiquid": true,
      "rpo_disabled": null
    },
    {
      "id": "BCH-PEN",
      "name": "bch-pen",
      "base_currency": "BCH",
      "quote_currency": "PEN",
      "minimum_order_amount": [
        "0.001",
        "BCH"
      ],
      "disabled": false,
      "illiquid": false,
      "rpo_disabled": null
    },
    {
      "id": "BTC-ARS",
      "name": "btc-ars",
      "base_currency": "BTC",
      "quote_currency": "ARS",
      "minimum_order_amount": [
        "0.00002",
        "BTC"
      ],
      "disabled": false,
      "illiquid": false,
      "rpo_disabled": true
    },
    {
      "id": "ETH-ARS",
      "name": "eth-ars",
      "base_currency": "ETH",
      "quote_currency": "ARS",
      "minimum_order_amount": [
        "0.001",
        "ETH"
      ],
      "disabled": false,
      "illiquid": true,
      "rpo_disabled": false
    },
    {
      "id": "BCH-ARS",
      "name": "bch-ars",
      "base_currency": "BCH",
      "quote_currency": "ARS",
      "minimum_order_amount": [
        "0.001",
        "BCH"
      ],
      "disabled": false,
      "illiquid": true,
      "rpo_disabled": true
    },
    {
      "id": "LTC-BTC",
      "name": "ltc-btc",
      "base_currency": "LTC",
      "quote_currency": "BTC",
      "minimum_order_amount": [
        "0.003",
        "LTC"
      ],
      "disabled": false,
      "illiquid": false,
      "rpo_disabled": null
    },
    {
      "id": "LTC-CLP",
      "name": "ltc-clp",
      "base_currency": "LTC",
      "quote_currency": "CLP",
      "minimum_order_amount": [
        "0.003",
        "LTC"
      ],
      "disabled": false,
      "illiquid": false,
      "rpo_disabled": null
    },
    {
      "id": "LTC-COP",
      "name": "ltc-cop",
      "base_currency": "LTC",
      "quote_currency": "COP",
      "minimum_order_amount": [
        "0.003",
        "LTC"
      ],
      "disabled": false,
      "illiquid": true,
      "rpo_disabled": null
    },
    {
      "id": "LTC-PEN",
      "name": "ltc-pen",
      "base_currency": "LTC",
      "quote_currency": "PEN",
      "minimum_order_amount": [
        "0.003",
        "LTC"
      ],
      "disabled": false,
      "illiquid": false,
      "rpo_disabled": null
    },
    {
      "id": "LTC-ARS",
      "name": "ltc-ars",
      "base_currency": "LTC",
      "quote_currency": "ARS",
      "minimum_order_amount": [
        "0.003",
        "LTC"
      ],
      "disabled": false,
      "illiquid": true,
      "rpo_disabled": true
    }
  ]
}
```

### Authorization

No necesita autorización

# **getTicker**
> getTicker($market_id)

El ticker permite ver el estado actual de un determinado mercado. La respuesta a esta llamada entrega las mejores ofertas de compra y venta (bid y ask), asi como el precio de la ultima transacción (last_price) para el mercado solicitado. También incluye información como el volumen diario y cuanto ha cambiado el precio en las últimas 24 hrs.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Tsukiro\Client\Api\BudaApi();
$market_id = "btc-clp"; // string | Market ID

try {
    $response = $apiInstance->getTicker($market_id);
    list($ticker, $statusCode, $headers) = $response;
} catch (Exception $e) {
    echo 'Exception when calling BudaApi->getTicker: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **market_id** | **string**| Market ID | Valor obtenido desde el método de markets

### Return Body Example
```
{
  "ticker": {
    "market_id": "BTC-CLP",
    "last_price": [
      "26993379.0",
      "CLP"
    ],
    "min_ask": [
      "27000000.0",
      "CLP"
    ],
    "max_bid": [
      "26993732.0",
      "CLP"
    ],
    "volume": [
      "103.12341041",
      "BTC"
    ],
    "price_variation_24h": "-0.072",
    "price_variation_7d": "-0.224"
  }
}
```

### Authorization

No necesita autenticación
