[comment]: <> (Change format & change entities to match AlbuQuirky entities)

# Albuquirky Endpoints

(work in progress)

## Global

### Server Context Path

```/albuquirky```

### Authentication

All endpoints are secured by OAuth 2.0. Any requests not including an ```Authorization``` header with a valid ```Bearer``` token will result in a ```401 Unauthorized``` status.

### Content Types

Except where noted, all endpoints produce and/or consume ```application/json```.

## Endpoints

### `GET` `/profiles/me`

### Description
Return the current `Profile`.

### path Parameters
(None)

### Query parameters
(None)

### Response Body
`Profile`

### Response Status
 * `200 OK`

### `GET` `/profiles/me/orders`

### Description
Returns all orders the user has placed.

### path Parameters
(None)

### Query parameters
* `role` 
    * `PROFILE`

### Request Body
 (None)

### Response Body
`Order[]`

### Response Status
 * `200 OK`

### `GET` `/profiles/me/products`

### Description
Returns all products the user has created.

### path Parameters
(None)

### Query parameters
* `role` 
    * `PROFILE`

### Request Body
 (None)

### Response Body
`Commissioner[]`

### Response Status
 * `200 OK`

### `GET` `/profiles/me/commissions`

### Description
Returns all commissions the user has created.

### path Parameters
* commissioner

### Query parameters
* `role` 
    * `PROFILE`

### Request Body
 (None)

### Response Body
`Product[]`

### Response Status
 * `200 OK`

  ### `GET` `/profiles/me/commissions`

### Description
Returns all commissions sent to the user.

### path Parameters
* seller

### Query parameters
* `role` 
    * `PROFILE`

### Request Body
 (None)

### Response Body
`Commissioner[]`

### Response Status
 * `200 OK`

### `GET` `/profiles/me/name`
    
### Description
    Retrieves display name of current profile (companion to `PUT`).
    
### Path parameters
    (None)
    
### Query Parameters
    (None)
    
### Request body
    (None)
    
### Response body 
    `String` (`Content-type: text/plain`)
    
### Response status
    
* `200 OK`

### `PUT` `/profiles/me/username`
    
### Description
    Replaces username of current profile.
    
### Path parameters
    (None)
    
### Query parameters
    (None)
    
### Request body
    `String` (`Content-type: text/plain`)
    
### Response body
    `String` (`Content-type: text/plain`)
    
### Response status
    
*  `200 OK`
*  `400 Bad Request`
    Empty request body.

### `PUT` `/profiles/me/password`
    
### Description
    Replaces password of current profile.
    
### Path parameters
    (None)
    
### Query parameters
    (None)
    
### Request body
    `String` (`Content-type: text/plain`)
    
### Response body
    `String` (`Content-type: text/plain`)
    
### Response status
    
*  `200 OK`
*  `400 Bad Request`
    Empty request body.

### `PUT` `/profiles/me/image`
    
### Description
    Replaces profile picture of current profile.
    
### Path parameters
    (None)
    
### Query parameters
    (None)
    
### Request body
    `String` (`Content-type: text/plain`)
    
### Response body
    `String` (`Content-type: text/plain`)
    
### Response status
    
*  `200 OK`
*  `400 Bad Request`
    Empty request body.

### `PUT` `/profiles/me/address`
    
### Description
    Replaces address of current profile.
    
### Path parameters
    (None)
    
### Query parameters
    (None)
    
### Request body
    `String` (`Content-type: text/plain`)
    
### Response body
    `String` (`Content-type: text/plain`)
    
### Response status
    
*  `200 OK`
*  `400 Bad Request`
    Empty request body.

### `PUT` `/commissions/{commissionId}/commissionRequest`
    
### Description
    Replaces the commission request for a commission.
    
### Path parameters
* commissioner
    
### Query parameters
    (None)
    
### Request body
    `String` (`Content-type: text/plain`)
    
### Response body
    `String` (`Content-type: text/plain`)
    
### Response status
    
*  `200 OK`
*  `400 Bad Request`
    Empty request body.

### `PUT` `/products/{productId}/name`
    
### Description
    Replaces name of a specific product.
    
### Path parameters
* productId
    
### Query parameters
    (None)
    
### Request body
    `String` (`Content-type: text/plain`)
    
### Response body
    `String` (`Content-type: text/plain`)
    
### Response status
    
*  `200 OK`
*  `400 Bad Request`
    Empty request body.

### `PUT` `/products/{productId}/description`
    
### Description
    Replaces description of specific product.
    
### Path parameters
* productId
    
### Query parameters
    (None)
    
### Request body
    `String` (`Content-type: text/plain`)
    
### Response body
    `String` (`Content-type: text/plain`)
    
### Response status
    
*  `200 OK`
*  `400 Bad Request`
    Empty request body.

### `PUT` `/products/{productId}/price`
    
### Description
    Replaces price of specific product.
    
### Path parameters
* productId
    
### Query parameters
    (None)
    
### Request body
    `String` (`Content-type: text/plain`)
    
### Response body
    `String` (`Content-type: text/plain`)
    
### Response status
    
*  `200 OK`
*  `400 Bad Request`
    Empty request body.


### `PUT` `/products/{productId}/stock`
    
### Description
    Replaces stock of specific product.
    
### Path parameters
* productId
    
### Query parameters
    (None)
    
### Request body
    `String` (`Content-type: text/plain`)
    
### Response body
    `String` (`Content-type: text/plain`)
    
### Response status
    
*  `200 OK`
*  `400 Bad Request`
    Empty request body.

### `POST` `/products`

### Descrition
Create a new product

###Path Parameters
(None)

### Query Parameters
(None)

### Request Body
`Product`

### Response body
`Product`

### Response Status
* `201 Created`
* `400 Bad Request`
One or more invalid `Product` properties -or an invalid combination of properties - in request.

### `POST` `/commission`

### Descrition
Create a new commission

###Path Parameters
(None)

### Query Parameters
(None)

### Request Body
`Commission`

### Response body
`Commission`

### Response Status
* `201 Created`
* `400 Bad Request`
One or more invalid `Commission` properties -or an invalid combination of properties - in request.

### `POST` `/images`

### Descrition
Create a new product

###Path Parameters
(None)

### Query Parameters
(None)

### Request Body
`Image`

### Response body
`Image`

### Response Status
* `201 Created`
* `400 Bad Request`
One or more invalid `Image` properties -or an invalid combination of properties - in request.

### `GET` `/products/{productId}`

### Description

Retrieves details of a specific product.

### Path Parameters

* `productId`
`Product` identifier

### Query Parameters

(None)

### Request Body

(None)


### Response Body

`Product`

### Reponse Status

* `200 OK`
* `404 Not Found`

### `GET` `/commissions/{commissionId}`

### Description

Retrieves details of a specific commission.

### Path Parameters

* `commissionId`
`Commission` identifier

### Query Parameters

(None)

### Request Body

(None)


### Response Body

`Commission`

### Reponse Status

* `200 OK`
* `404 Not Found`

### `GET` `/orders/{orderId}`

### Description

Retrieves details of a specific order.

### Path Parameters

* `orderId`
`Order` identifier

### Query Parameters

(None)

### Request Body

(None)


### Response Body

`Order`

### Reponse Status

* `200 OK`
* `404 Not Found`

### `GET` `/images/{imageId}`

### Description

Retrieves details of a specific image.

### Path Parameters

* `imageId`
`Image` identifier

### Query Parameters

(None)

### Request Body

(None)


### Response Body

`Image`

### Reponse Status

* `200 OK`
* `404 Not Found`

### `GET` `/productsonorder/{productOnOrderId}`

### Description

Retrieves details of a specific product.

### Path Parameters

* `productOnOrderId`
`ProductOnOrder` identifier

### Query Parameters

(None)

### Request Body

(None)


### Response Body

`ProductOnOrder`

### Reponse Status

* `200 OK`
* `404 Not Found`

### `GET` `/products/{productId}/images`

### Description

Retrieves a list of images for a specified product.

### Path Parameters

* `productId`
`Product` identifier

### Query Parameters

(None)

### Request Body

(None)

### Response Body

* `Image[]`

### Reponse Status

* `200 OK`
* `404 Not Found`

### `GET` `/orders/{orderId}/productsOnOrder`

### Description

Retrieves a list of products on an order for a specified order.

### Path Parameters

* `orderId`
`Order` identifier

### Query Parameters

(None)

### Request Body

(None)

### Response Body

* `ProductOnOrder[]`

### Reponse Status

* `200 OK`
* `404 Not Found`

### `GET` `/products/{productId}/images/{imageId}`

### Description

Retrieves a specific image for a specified product.

### Path Parameters

* `productId`
`Product` identifier
* `imageId`
`Image` identifier

### Query Parameters

(None)

### Request Body

(None)

### Response Body

* `Image`

### Reponse Status

* `200 OK`
* `404 Not Found`

### `GET` `/orders/{orderId}/productsOnOrder{productOnOrderId}`

### Description

Retrieves a specific product on an order for a specified order.

### Path Parameters

* `orderId`
`Order` identifier
* `productOnOrderId`
`ProductOnOrder` identifier

### Query Parameters

(None)

### Request Body

(None)

### Response Body

* `ProductOnOrder`

### Reponse Status

* `200 OK`
* `404 Not Found`

