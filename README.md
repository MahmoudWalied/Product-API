# Product API using Laravel Passport
This API allows CRUD operations on products. It uses Laravel Passport for authentication and authorization.

### Endpoints

#### Auth
- POST /api/register - Register a new user
- POST /api/login - Login user
- GET /api/userinfo - Get user info


#### Products
- GET /api/products - Get list of products
- POST /api/products - Create a new product
- GET /api/products/{id} - Show a product by ID
- PUT /api/products/{id} - Update a product by ID
- DELETE /api/products/{id} - Delete a product by ID
### Authentication
This API uses Laravel Passport for OAuth2 authentication.
To authenticate, make a POST request to /oauth/token with your client ID, client secret, email and password. This will return an access token to use in subsequent requests.
Pass this access token in the Authorization header as follows:
```
Authorization: Bearer {access_token}
```
### Authorization
The /api/products endpoints require a valid authenticated user token.
The /api/register endpoint allows registration of new users.
### Models
The main model is Product which contains:
- name
- detail

### Example Requests
#### Register a new user
```
POST /api/register
{
    "name": "John Doe",
    "email": "john@example.com",
    "password": "password"
}
```
#### Create a product
```
POST /api/products
Authorization: Bearer {access_token}

{
    "name": "Product 1",
    "detail": "This is product 1", 
}
```
