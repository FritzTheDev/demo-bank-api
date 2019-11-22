# demo-bank-api
Bank-style API built to demonstrate Django and DRF skills

## Example Endpoint
### `/path/to/endpoint`
- GET retuns EXAMPLE DATA | **permission-group**

## Endpoints
### `/token`
- POST accepts a username & password, and returns a pair of JWTs, one access token to access the other endpoints & one refresh token to get new access tokens | **none**
### `/admin` 
- GET is the login screen for the django admin console | **admin**
### `/refresh`
- POST accepts the refresh token and returns a new access token. This route exists because the refresh token is valid longer than an access token | **none**

### `/accounts`
- GET returns all accounts | **admin**
- POST adds an account then returns that account's details | **admin**

### `/accounts/<account_id>`
- GET returns a single account's details based on its primary key | **owner** OR **admin**
- PATCH partially changes the account's details | **admin**

### `/accounts/<account_id>/transactions`
- GET returns all transactions associated with an account | **owner** OR **admin**
- POST adds a new transaction to a user account | **admin**

### `/accounts/<account_id>/transactions/<transaction_id>`
- GET returns a specific transaction's details | **owner** OR **admin**
- PATCH partially changes a specific transaction's details | **admin**
- DELETE deletes a transaction and returns a 204 No Content | **admin**

### `/accounts/<account_id>/transactions/<transaction_id>/comments`
- GET returns all the comments on a specific transaction | **owner** OR **admin**
- POST adds a new comment to the transaction | **owner** OR **admin**

### `/accounts/<account_id>/transactions/<transaction_id>/comments/<comment_id>`
- GET returns a specific comment's details | **owner** OR **admin**
- DELETE deletes a comment and returns a 204 no content | **owner** OR **admin**
