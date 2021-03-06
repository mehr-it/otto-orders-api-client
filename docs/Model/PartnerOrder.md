# PartnerOrder

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**sales_order_id** | **string** | The id of the corresponding sales order. For one partner the sales order id is unique | 
**order_number** | **string** | The order number. An unique human readable 10 character(alphanumeric) identifier referring to this order | 
**order_date** | [**\DateTime**](\DateTime.md) | The date, when this order has been placed | 
**last_modified_date** | [**\DateTime**](\DateTime.md) | Last order update date | [optional] 
**position_items** | [**\MehrIt\OttoOrdersApiClient\Model\PositionItem[]**](PositionItem.md) | The physical position items of this order. Multiple position item can refer to the same product | 
**order_lifecycle_information** | [**\MehrIt\OttoOrdersApiClient\Model\OrderLifecycleInformation**](OrderLifecycleInformation.md) |  | 
**initial_service_fees** | [**\MehrIt\OttoOrdersApiClient\Model\InitialServiceFee[]**](InitialServiceFee.md) | The initial Service Fees on customer checkout | [optional] 
**delivery_address** | [**\MehrIt\OttoOrdersApiClient\Model\Address**](Address.md) |  | 
**invoice_address** | [**\MehrIt\OttoOrdersApiClient\Model\Address**](Address.md) |  | 
**links** | [**\MehrIt\OttoOrdersApiClient\Model\Link[]**](Link.md) | Order related links like the link to fetch the single partner order | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

