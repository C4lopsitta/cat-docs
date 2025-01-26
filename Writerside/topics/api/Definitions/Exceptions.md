# Exception Definitions
All definitions for responses that are not in the 200 HTTP Status Code range. (400 range and 500 range)

## 400
<api-schema openapi-path="../../../../cat-php-api_openapi.json" name="ExceptionBadRequest" />

## 401
<api-schema openapi-path="../../../../cat-php-api_openapi.json" name="ExceptionUnauthorized" />

## 402
los TODO

## 403
<api-schema openapi-path="../../../../cat-php-api_openapi.json" name="ExceptionUserNotVerified" />

## 404
<api-schema openapi-path="../../../../cat-php-api_openapi.json" name="ExceptionNotFound" />

## 405
> Almost every endpoint can return this, even if it is not defined in the endpoint definitions, as it's assumed that you 
> are going to use the correct Method to make the request as per definition. Nevertheless, what follows is the schema of the 
> Method Not Allowed 405 error.

<api-schema openapi-path="../../../../cat-php-api_openapi.json" name="ExceptionMethodNotAllowed" />


## 500
<api-schema openapi-path="../../../../cat-php-api_openapi.json" name="ExceptionServerError" />



