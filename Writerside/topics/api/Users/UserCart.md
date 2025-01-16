# User Cart

These endpoints manage the user's cart. Three methods are available on this endpoint
- `GET`
- `PUT` (requires authentication and account ownership)
- `DELETE` (requires authentication and account ownership)

> [The endpoint `./cart/checkout` is also available.](CheckoutCart.md)

GET
---
<api-endpoint openapi-path="../../../../cat-php-api_openapi.json" method="GET" endpoint="/api/v1/users/{uid}/cart"/>

PUT
---
<api-endpoint openapi-path="../../../../cat-php-api_openapi.json" method="PUT" endpoint="/api/v1/users/{uid}/cart"/>

DELETE
---
<api-endpoint openapi-path="../../../../cat-php-api_openapi.json" method="DELETE" endpoint="/api/v1/users/{uid}/cart"/>


