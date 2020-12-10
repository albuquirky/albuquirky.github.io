# AlbuQuirky Endpoints

(work in progress)

## Global

### Server Context Path

```/albuquirky/api```

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

### `GET` `/profiles/{profileId}`

### Description

Return a specific `Profile`.

### path Parameters

* long id

### Query parameters

(None)

### Response Body

`Profile`

### Response Status

* `200 OK`
* `404 Not Found`

### `GET` `/profiles/me/username`

### Description

Retrieves username of current profile (companion to `PUT`).

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

### `GET` `/profiles/me/image`

### Description

Retrieves profile image reference of current profile (companion to `PUT`).

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

### `PUT` `/profiles/me/image`

### Description

Replaces profile image reference of current profile.

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

### `GET` `/profiles/me/address`

### Description

Retrieves address of current profile (companion to `PUT`).

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

### `GET` `/orders/user-orders`

### Description

Return all instances of `Order` placed by the User.

### path Parameters

(None)

### Query parameters

* long userId

### Response Body

`Order[]`

### Response Status

* `200 OK`

### `GET` `/orders/user-sold-orders`

### Description

Return all instances of `Order` that the User is responsible for fulfilling.

### path Parameters

(None)

### Query parameters

* long userId

### Response Body

`Order[]`

### Response Status

* `200 OK`

### `POST` `/orders`

### Description

Creates a new `Order`.

### Path Parameters

(None)

### Query Parameters

* (None)

### Response Body

`Order`

### Response Status

* `200 OK`

### `GET` `/orders/{orderId}`

### Description

Return a specific `Order`.

### path Parameters

* long id

### Query parameters

(None)

### Response Body

`Order`

### Response Status

* `200 OK`
* `404 Not Found`

### `GET` `/commissions/seller`

### Description

Return all instances of `Commission` where the User is the seller.

### path Parameters

(None)

### Query parameters

* long sellerId

### Response Body

`Commission[]`

### Response Status

* `200 OK`

### `GET` `/commissions/commissioner`

### Description

Return all instances of `Commission` where the User is the commissioner.

### path Parameters

(None)

### Query parameters

* long commissionerId

### Response Body

`Commission[]`

### Response Status

* `200 OK`

### `POST` `/commissions`

### Description

Creates a new `Commission`.

### Path Parameters

(None)

### Query Parameters

* (None)

### Response Body

`Commission`

### Response Status

* `200 OK`

### `GET` `/commissions/{commissionId}`

### Description

Return a specific `Commission`.

### Path Parameters

* long id

### Query parameters

(None)

### Response Body

`Commission`

### Response Status

* `200 OK`
* `404 Not Found`

### `DELETE` `/commissions/{commissionId}`

Deletes a `Commission` from the database.

### Path Parameters

* long commissionId

### Query Parameters

(None)

### Response Body

(None)

### Response Status

* `200 OK`
* `404 Not Found`

### `GET` `/commissions/{commissionId}/commission_request`

### Description

Retrieves commission request of a specific commission (companion to `PUT`).

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

### `PUT` `/commissions/{commissionId}/commission_request`

### Description

Replaces commission request of a specific commission.

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

### `GET` `/products/{keyword}`

### Description

Return all instances of `Product` that matches a keyword.

### path Parameters

(None)

### Query parameters

* String keyword

### Response Body

`Product[]`

### Response Status

* `200 OK`

### `GET` `/products/{userId}`

### Description

Return all instances of `Product` created by the User.

### path Parameters

(None)

### Query parameters

* long userId

### Response Body

`Product[]`

### Response Status

* `200 OK`

### `POST` `/products`

### Description

Creates a new `Product`.

### Path Parameters

(None)

### Query Parameters

* (None)

### Response Body

`Product`

### Response Status

* `200 OK`

### `GET` `/products/{productId}`

### Description

Return a specific `Product`.

### path Parameters

* long id

### Query parameters

(None)

### Response Body

`Product`

### Response Status

* `200 OK`
* `404 Not Found`

### `GET` `/products/{productId}/product_name`

### Description

Retrieves product name of a specific product (companion to `PUT`).

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

### `PUT` `/products/{productId}/product_name`

### Description

Replaces product name of a specific product.

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

### `GET` `/products/{productId}/description`

### Description

Retrieves description of a specific product (companion to `PUT`).

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

### `PUT` `/products/{productId}/description`

### Description

Replaces description of a specific product.

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

### `GET` `/products/{productId}/price`

### Description

Retrieves price of a specific product (companion to `PUT`).

### Path parameters

(None)

### Query Parameters

(None)

### Request body

(None)

### Response body

`int` (`Content-type: text/plain`)

### Response status

* `200 OK`

### `PUT` `/products/{productId}/price`

### Description

Replaces price of a specific product.

### Path parameters

(None)

### Query parameters

(None)

### Request body

`int` (`Content-type: text/plain`)

### Response body

`int` (`Content-type: text/plain`)

### Response status

*  `200 OK`
*  `400 Bad Request`
Empty request body.

### `GET` `/products/{productId}/stock`

### Description

Retrieves stock of a specific product (companion to `PUT`).

### Path parameters

(None)

### Query Parameters

(None)

### Request body

(None)

### Response body

`int` (`Content-type: text/plain`)

### Response status

* `200 OK`

### `PUT` `/products/{productId}/stock`

### Description

Replaces stock of a specific product.

### Path parameters

(None)

### Query parameters

(None)

### Request body

`int` (`Content-type: text/plain`)

### Response body

`int` (`Content-type: text/plain`)

### Response status

*  `200 OK`
*  `400 Bad Request`
Empty request body.

### `GET` `/images/{productId}`

### Description

Return all instances of `Image` associated with a particular `Product`.

### path Parameters

(None)

### Query parameters

long productId

### Response Body

`Image[]`

### Response Status

* `200 OK`

### `POST` `/images`

### Description

Creates a new `Image`.

### Path Parameters

(None)

### Query Parameters

* (None)

### Response Body

`Image`

### Response Status

* `200 OK`

### `GET` `/images/{imageId}`

### Description

Return a specific `Image`.

### path Parameters

* long id

### Query parameters

(None)

### Response Body

`Image`

### Response Status

* `200 OK`
* `404 Not Found`

### `DELETE` `/images/{imageId}`

Deletes an `Image` from the database.

### Path Parameters

* long commissionId

### Query Parameters

* `Image`
* `Profile`

### Response Body

(None)

### Response Status

* `200 OK`
* `404 Not Found`

### `GET` `/images/{imageId}/description`

### Description

Retrieves description of a specific image (companion to `PUT`).

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

### `PUT` `/images/{imageId}/description`

### Description

Replaces description of a specific image.

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
