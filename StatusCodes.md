# HTTP Status Codes
## Complete list of Status Codes
A full list of HTTP Status Codes with explanation and related RFC specs can be found on [Wikipedia](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes).

## Common used codes within Digipolis
This is a list of common used status codes that should be handled correctly by clients consuming services approved by the Digipolis REST API Guidelines Working Group.

Each API method should preferably document the status codes that can be returned in the Swagger documentation.

### 2xx (Successful)
The request was successfully received, understood, and accepted.

| Code | Status     | When to use
|------|------------|--------------
| 200  | OK         | Standard response for successful HTTP requests.
| 201  | Created    | The request resulted in the creation of a new resource.
| 202  | Accepted   | The request has been accepted for processing (long running job).
| 204  | No Content | The server successfully processed the request and is not returning any content.

### 3xx (Redirection)
Further action needs to be taken in order to complete the request.

| Code | Status            | When to use
|------|-------------------|--------------
| 301  | Moved Permanently | This and all future requests should be directed to the given URI.
| 307  | Temporary Redirect | In this case, the request should be repeated with another URI; however, future requests should still use the original URI.

### 4xx (Client Error)
The request contains bad syntax or cannot be fulfilled. This range should be used for user/client errors.

| Code | Status                | When to use
|------|-----------------------|--------------
| 400  | Bad request           | The server cannot or will not process the request due to an apparent client error.
| 401  | Unauthorized          | Similar to 403 Forbidden, but specifically for use when authentication is required and has failed or has not yet been provided.
| 403  | Forbidden             | The request was valid, but the server is refusing action. The user might not have the necessary permissions for a resource.
| 404  | Not Found             | The requested resource could not be found but may be available in the future.
| 405  | Method Not Allowed    | A request method is not supported for the requested resource (e.g. GET instead of PUT).

### 5xx (Server Error):
The server failed to fulfill an apparently valid request. This range should be used for server errors of exceptional state, which are not triggered due to bad input from the client.

| Code | Status                | When to use
|------|-----------------------|--------------
| 500  | Internal Server Error | A generic error message, given when an unexpected condition was encountered and no more specific message is suitable.
| 502  | Bad Gateway           | The server was acting as a gateway or proxy and received an invalid response from the upstream server.
| 503  | Service Unavailable   | The server is currently unavailable. Generally, this is a temporary state.
| 504  | Gateway Timeout       | The server was acting as a gateway or proxy and did not receive a timely response from the upstream server.
