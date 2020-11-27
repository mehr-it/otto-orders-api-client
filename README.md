# .
This API documentation describes all endpoints for orders - version 3

This PHP package is automatically generated by the [Swagger Codegen](https://github.com/swagger-api/swagger-codegen) project:

- API version: v3
- Build package: io.swagger.codegen.v3.generators.php.PhpClientCodegen

## Requirements

PHP 5.5 and later

## Installation & Usage
### Composer

To install the bindings via [Composer](http://getcomposer.org/), add the following to `composer.json`:

```
{
  "repositories": [
    {
      "type": "git",
      "url": "https://github.com/mehr-it/otto-orders-api-client.git"
    }
  ],
  "require": {
    "mehr-it/otto-orders-api-client": "*@dev"
  }
}
```

Then run `composer install`

### Manual Installation

Download the files and include `autoload.php`:

```php
    require_once('/path/to/./vendor/autoload.php');
```

## Tests

To run the unit tests:

```
composer install
./vendor/bin/phpunit
```

## Getting Started

Please follow the [installation procedure](#installation--usage) and then run the following:

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new MehrIt\OttoOrdersApiClient\Api\ALLApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$sales_order_id = "sales_order_id_example"; // string | The Sales Order Id of the order to cancel
$position_item_id = array("position_item_id_example"); // string[] | The ids of the PositionItems to cancel

try {
    $apiInstance->cancelPartnerOrderPositionItems($sales_order_id, $position_item_id);
} catch (Exception $e) {
    echo 'Exception when calling ALLApi->cancelPartnerOrderPositionItems: ', $e->getMessage(), PHP_EOL;
}

$apiInstance = new MehrIt\OttoOrdersApiClient\Api\ALLApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$sales_order_id = array("sales_order_id_example"); // string[] | The Sales Order Id of the order to cancel

try {
    $apiInstance->cancelPartnerOrders($sales_order_id);
} catch (Exception $e) {
    echo 'Exception when calling ALLApi->cancelPartnerOrders: ', $e->getMessage(), PHP_EOL;
}

$apiInstance = new MehrIt\OttoOrdersApiClient\Api\ALLApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$from_date = "from_date_example"; // string | Defines, which minimum change date the returned order should have. In ISO 8601 format.
$from_order_date = "from_order_date_example"; // string | Lower boundary of filter by order date: Only orders newer than the date specified will be returned. In ISO 8601 format.
$to_order_date = "to_order_date_example"; // string | Upper boundary of filter by order date: Only orders older than the date specified will be returned. In ISO 8601 format.
$fulfillment_status = "fulfillment_status_example"; // string | Defines, which minimum state the returned orders should have.<br>If ANNOUNCED is given, all orders, which have at least one PositionItem in ANNOUNCED state are returned.<br>If PROCESSABLE is given, all orders, which have at least one PositionItem in PROCESSABLE state and none in ANNOUNCED state are returned.<br>If SENT is given, all orders, which have at least one PositionItem in SENT state and none in either ANNOUNCED or PROCESSABLE state are returned.<br>If RETURNED is given, all orders, which have at least one PositionItem in RETURNED state and none in either ANNOUNCED or PROCESSABLE or SENT state are returned.<br>If CANCELLED_BY_PARTNER is given, all orders, which have at least one PositionItem in CANCELLED_BY_PARTNER state are returned.<br>If CANCELLED_BY_MARKETPLACE is given, all orders, which have at least one PositionItem in CANCELLED_BY_MARKETPLACE state are returned.<br>If none is provided, all status will be returned.<br>Several values can be passed via request param array, when multiple values passed, search result will be combination of multiple fulfillmentStatuses - no duplicates will appear.<br>Example: ?fulfillmentStatus=PROCESSABLE&fulfillmentStatus=CANCELLED_BY_MARKETPLACE - will return orders in these 3 fulfillmentStatuses.<br>Alternatively, mode can be passed for a different search type. BUCKET/AT_LEAST_ONE, where BUCKET is default behaviour explained above and AT_LEAST_ONE checks if there is at least 1 PositionItem with passed fulfillmentStatus/fulfillmentStatuses.
$limit = 128; // int | The maximum amount of returned orders
$order_direction = "ASC"; // string | 
$order_column_type = "ORDER_LIFECYCLE_DATE"; // string | 
$mode = "BUCKET"; // string | The search mode. Default search mode is bucket search
$nextcursor = "nextcursor_example"; // string | For paging request this cursor is required. If a next cursor is provided, the only other request parameter being considered is 'limit'.<br>Only the cursor string is required, not the whole link to the cursor.<br>Example: nextcursor=eyJmZiI6MTU5NDg5NDQ3MTA1OCwicGlmIjoiNDcxM...
$search_term = "search_term_example"; // string | The search term for partial text search.

try {
    $result = $apiInstance->findPartnerOrders($from_date, $from_order_date, $to_order_date, $fulfillment_status, $limit, $order_direction, $order_column_type, $mode, $nextcursor, $search_term);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ALLApi->findPartnerOrders: ', $e->getMessage(), PHP_EOL;
}

$apiInstance = new MehrIt\OttoOrdersApiClient\Api\ALLApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$order_number = "order_number_example"; // string | The Order Number used for searching

try {
    $result = $apiInstance->getPartnerOrderByOrderNumber($order_number);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ALLApi->getPartnerOrderByOrderNumber: ', $e->getMessage(), PHP_EOL;
}

$apiInstance = new MehrIt\OttoOrdersApiClient\Api\ALLApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$sales_order_id = "sales_order_id_example"; // string | The Sales Order Id used for searching

try {
    $result = $apiInstance->getPartnerOrderBySalesOrderId($sales_order_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ALLApi->getPartnerOrderBySalesOrderId: ', $e->getMessage(), PHP_EOL;
}
?>
```

## Documentation for API Endpoints

All URIs are relative to *https://live.api.otto.market*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*ALLApi* | [**cancelPartnerOrderPositionItems**](docs/Api/ALLApi.md#cancelpartnerorderpositionitems) | **POST** /v3/orders/{salesOrderId}/positionItems/{positionItemId}/cancellation | Cancels PositionItems of an order by ids
*ALLApi* | [**cancelPartnerOrders**](docs/Api/ALLApi.md#cancelpartnerorders) | **POST** /v3/orders/{salesOrderId}/cancellation | Cancel all PositionItems of an order
*ALLApi* | [**findPartnerOrders**](docs/Api/ALLApi.md#findpartnerorders) | **GET** /v3/orders | Get a list of orders which can be filtered on fulfillmentStatus.
*ALLApi* | [**getPartnerOrderByOrderNumber**](docs/Api/ALLApi.md#getpartnerorderbyordernumber) | **GET** /v3/orders/{orderNumber} | Get a single order via Order Number
*ALLApi* | [**getPartnerOrderBySalesOrderId**](docs/Api/ALLApi.md#getpartnerorderbysalesorderid) | **GET** /v3/orders/{salesOrderId} | Get a single order via Sales Order Id
*OrdersApi* | [**cancelPartnerOrders**](docs/Api/OrdersApi.md#cancelpartnerorders) | **POST** /v3/orders/{salesOrderId}/cancellation | Cancel all PositionItems of an order
*OrdersApi* | [**findPartnerOrders**](docs/Api/OrdersApi.md#findpartnerorders) | **GET** /v3/orders | Get a list of orders which can be filtered on fulfillmentStatus.
*OrdersApi* | [**getPartnerOrderByOrderNumber**](docs/Api/OrdersApi.md#getpartnerorderbyordernumber) | **GET** /v3/orders/{orderNumber} | Get a single order via Order Number
*OrdersApi* | [**getPartnerOrderBySalesOrderId**](docs/Api/OrdersApi.md#getpartnerorderbysalesorderid) | **GET** /v3/orders/{salesOrderId} | Get a single order via Sales Order Id
*PositionItemsApi* | [**cancelPartnerOrderPositionItems**](docs/Api/PositionItemsApi.md#cancelpartnerorderpositionitems) | **POST** /v3/orders/{salesOrderId}/positionItems/{positionItemId}/cancellation | Cancels PositionItems of an order by ids

## Documentation For Models

 - [Address](docs/Model/Address.md)
 - [Amount](docs/Model/Amount.md)
 - [InitialServiceFee](docs/Model/InitialServiceFee.md)
 - [Link](docs/Model/Link.md)
 - [OrderLifecycleInformation](docs/Model/OrderLifecycleInformation.md)
 - [PartnerOrder](docs/Model/PartnerOrder.md)
 - [PartnerOrderList](docs/Model/PartnerOrderList.md)
 - [PositionItem](docs/Model/PositionItem.md)
 - [Product](docs/Model/Product.md)
 - [TrackingInfo](docs/Model/TrackingInfo.md)

## Documentation For Authorization

 All endpoints do not require authorization.


## Author



