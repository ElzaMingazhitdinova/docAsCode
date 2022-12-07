#  API for P2P in KH [d] 
## API reference
_link to the API and another useful documentation_

## Integration flow
_describe the sequence of requests and user steps_

## Status model

| Provider |   Exness   |
|----------|:----------:|
|          | Processing |
|          |  Accepted  |
|          |   Failed   |

## Credentials
>_merchant_api: <br/>
merchant_key:_ 

#### Merchant area
_link to the provider's merchant area_
#### Sandbox
_all data for the test environment (url, credentials and so on)_


### Signature
_describe the signature for the requests_


## Description of requests
#### List of constants
> _place here constants_

## Request 'Create a new deposit/withdrawal'
##### Description of request

| **URL**      | **** |
|--------------|:----:|
| HTTP Method  |      |
| Content-Type |      |
| Header       |      |

| **Parameter** | **Type** | **Description** |
|---------------|:--------:|-----------------|
|               |          |                 |
|               |          |                 |
|               |          |                 |

### Example of request
>place here example

 #### Description of response
| **Parameter** | **Type** | **Description** |
|---------------|:--------:|-----------------|
|               |          |                 |
|               |          |                 |
|               |          |                 |

### Example of response
Successfull response
> _place here example_

Unsuccessfull response
> _place here example_

## Callback
### Callback signature
_description of callback signature_

### Description of a callback
| **Parameter** | **Type** | **Description** |
|---------------|:--------:|-----------------|
|               |          |                 |
|               |          |                 |
|               |          |                 |

### Example callback
Successful callback
>  {
   "amount":1000,
   "currency":"USD",
   "livemode":false
}


Unsuccessful callback
>  {
   "amount":1000,
   "currency":"USD",
   "livemode":false
}

### Description of response to callback
| **Parameter** | **Type** | **Description** |
|---------------|:--------:|-----------------|
|               |          |                 |
|               |          |                 |
|               |          |                 |

Example response
>  {
   "amount":1000,
   "currency":"USD",
   "livemode":false
}
## Request 'Get status'
### Description of request
| **URL**      | **** |
|--------------|:----:|
| HTTP Method  |      |
| Content-Type |      |
| Header       |      |

| **Parameter** | **Type** | **Description** |
|---------------|:--------:|-----------------|
|               |          |                 |
|               |          |                 |
|               |          |                 |

### Example of request
> place here the example

### Description of response

| **Parameter** | **Type** | **Description** |
|---------------|:--------:|-----------------|
|               |          |                 |
|               |          |                 |
|               |          |                 |

### Example response
Successful response
>  {
   "amount":1000,
   "currency":"USD",
   "livemode":false
}

Unsuccessful response
>  {
   "amount":1000,
   "currency":"USD",
   "livemode":false
}