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