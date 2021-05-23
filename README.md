<!-- PROJECT SHIELDS -->
<!--
*** I'm using markdown "reference style" links for readability.
*** Reference links are enclosed in brackets [ ] instead of parentheses ( ).
*** See the bottom of this document for the declaration of the reference variables
*** for contributors-url, forks-url, etc. This is an optional, concise syntax you may use.
*** https://www.markdownguide.org/basic-syntax/#reference-style-links
-->
[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![MIT License][license-shield]][license-url]

# Description
Este proyecto tiene como finalidad generar un SDK en PHP para utilizar los endpoints del sitio Buda.com
Por ahora el proyecto está generado con el Codegen de Tsukiro que podrá ser cambiado en un futuro Release.

## Requirements

PHP 5.5 and later

## Installation & Usage
### Composer

Puedes instalar el proyecto utilizando composer (v2)

Puedes añadir la siguiente linea de comandos a  tu `composer.json`:

```
{
  "require": {
    "tsukiro/buda-sdk": "*@dev"
  }
}
```

Luego ejecuta `composer install`
## Tests

To run the unit tests:

```
composer install
./vendor/bin/phpunit
```

## Getting Started

Luego de haber seguido los pasos del [procedimiento de instalación](#installation--usage) puedes hacer lo suguiente:

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
    echo 'Exception when calling BudaApi->apiV2BalancesGet: ', $e->getMessage(), PHP_EOL;
}

$apiInstance = new Tsukiro\Client\Api\BudaApi();

try {
    $response = $apiInstance->getMarkets();
    list($markets, $statusCode, $headers) = $response;
} catch (Exception $e) {
    echo 'Exception when calling BudaApi->getMarkets: ', $e->getMessage(), PHP_EOL;
}

$apiInstance = new Tsukiro\Client\Api\BudaApi();
$market_id = "market_id_example"; // string | Market ID obtenido desde le metodo getMarkets o desde tu base de datos

try {
    $response = $apiInstance->getTicker($market_id);
    list($ticker, $statusCode, $headers) = $response;
} catch (Exception $e) {
    echo 'Exception when calling BudaApi->apiV2MarketsMarketIdTickerGet: ', $e->getMessage(), PHP_EOL;
}
?>
```

## Documentation for API Endpoints

All URIs are relative to *https://www.buda.com*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*BudaApi* | [**getBalances**](docs/Api/BudaApi.md#getBalances) | **GET** /api/v2/balances | 
*BudaApi* | [**getMarkets**](docs/Api/BudaApi.md#getMarkets) | **GET** /api/v2/markets | 
*BudaApi* | [**getTicker**](docs/Api/BudaApi.md#getTicker) | **GET** /api/v2/markets/{market_id}/ticker | 


## Documentation For Authorization

 Para las rutas que requieran autenticación como lo es getBalances debes setear tu apikey y tu secret, las funciones que se hayan desarrollado automáticamente generarán el nonce y signature necesarios para comunicarse con los endpoints de buda

```
    $apiInstance->setApiKey("YOUR_APIKEY");
    $apiInstance->setSecret("YOUR_SECRET");
```


<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/tsukiro/repo.svg?style=for-the-badge
[contributors-url]: https://github.com/tsukiro/repo/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/tsukiro/repo.svg?style=for-the-badge
[forks-url]: https://github.com/tsukiro/repo/network/members
[stars-shield]: https://img.shields.io/github/stars/tsukiro/repo.svg?style=for-the-badge
[stars-url]: https://github.com/tsukiro/repo/stargazers
[issues-shield]: https://img.shields.io/github/issues/tsukiro/repo.svg?style=for-the-badge
[issues-url]: https://github.com/tsukiro/repo/issues
[license-shield]: https://img.shields.io/github/license/tsukiro/repo.svg?style=for-the-badge
[license-url]: https://github.com/tsukiro/repo/blob/master/LICENSE.txt
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/in/tsukiro
