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

[comment]: <>(Repeat for other entities linked to profile)
### `Get` `/profiles/me/orders`

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

[comment]: <>(Duplicate for all other valid attributes accross other entities)
### `PUT` `/profiles/me/name`
    
### Description
    Replaces display name of current profile.
    
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

[comment]: <>(replicate for other valid entities)
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

[comment]: <>(Endpoint to reterieve details of a single entry for each entity)
### `GET` `/products/{productId}`
[comment]: <>(Endpoint to retrieve all instances of dependant entity)
### `GET` `/products/{productId}/images`
[comment]: <>(endpoint to retrieve single instance of entity dependant on another entity)
### `GET` `/products/{productId}/images/{imageId}`



    

