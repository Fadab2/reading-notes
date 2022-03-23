# Authentication

### JSON Web Token
* JWT is a way of secure information transmission as a JSON object.
* Whenever the user wants to access a protected route or resource, the user agent should send the JWT, typically in the Authorization header using the Bearer schema.
* JWT information is digitally signed using HMAC algorithm or public/private key.
* JWT are useful in `authorization` and `information exchange`.
* JWT consist of `header.payload.signature` separated by dots.
* The Header consist of token type and the signing algorithm:
```
{
  "alg": "HS256",
  "typ": "JWT"
}
```
* The Payload contains registered, public, and private claims:

```
{
  "sub": "1234567890",
  "name": "John Doe",
  "admin": true
}
```
* The Signature is created using header, encoded payload, a secret, the algorithm:
```
HMACSHA256(
  base64UrlEncode(header) + "." +
  base64UrlEncode(payload),
  secret)
```

### Using JWT Authentication with Django REST Framework

* Install JWT: `pip install djangorestframework_simplejwt`

* Edit `settings.py` to look like below:
```
REST_FRAMEWORK = {
    'DEFAULT_AUTHENTICATION_CLASSES': [
        'rest_framework_simplejwt.authentication.JWTAuthentication',
    ],
}
```
* Edit `urls.py` with the below code:
```
from django.urls import path
from rest_framework_simplejwt import views as jwt_views

urlpatterns = [
    # Your URLs...
    path('api/token/', jwt_views.TokenObtainPairView.as_view(), name='token_obtain_pair'),
    path('api/token/refresh/', jwt_views.TokenRefreshView.as_view(), name='token_refresh'),
]
```
* Modify `views.py` to include the type of authentications:
```
class HelloView(APIView):
    permission_classes = (IsAuthenticated,)
```
* To obtain token use the url as:
`http post <http://127.0.0.1:8000/api/token/> username=vitor password=123`

<br />

## References

[JSON Web Token](https://jwt.io/introduction/)

[How to Use JWT Authentication with Django REST Framework](https://simpleisbetterthancomplex.com/tutorial/2018/12/19/how-to-use-jwt-authentication-with-django-rest-framework.html)

<br />

## [<-- Back](README.md)
