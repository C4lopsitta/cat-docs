# API Reference

> All endpoints start from `/api/v1`
## Endpoints
All the endpoints marked with *authenticated* require a valid user authentication token to be accessed.
Refer to the [authentication](#authentication) paragraph to understand how it works.
- /
    - [GET](GET.md)
    - [POST](POST.md)
    - [PUT](PUT.md)
    - [DELETE](DELETE.md)
- [`/users`](API-Users.md)
- 
## Authentication
Authentication is handled with an *email address*, a valid *password* and an optional 2FA verification code if the 
account has *two-factor authentication required*.
### Authenticating
Considering a dummy account `bob` with credentials `bob@foo.bar` and password `boblovesalice`, you can get a token by calling 
the [`/api/v1/users/authenticate`](#authenticating) endpoint. What follows is an example request:
```json
{
  "email": "bob@foo.bar",
  "password": "boblovesalice",
  "tokenUseCase": "API"
}
```
With this you'll get an API Bearer token that will have to be attached with an `authentication` header. Note that tokens 
have an expiration date and will have to be renewed once expired.
