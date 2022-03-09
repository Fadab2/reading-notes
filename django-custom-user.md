# Django Custom User
* Django comes with a built-in user model for authenticating users.
* It is recommended to use a custom user model for real world projects.
* Custom user model provide more flexibility along the road.

### Setting up a custom user model:
There are two modern ways to create a custom user model in Django: AbstractUser and AbstractBaseUser.
* AbstractUser provides more default configuration.
Creating our initial custom user model requires four steps:

* update the settings.py by adding `'accounts',` to installed apps.
* At the very end of the setting.py file add `AUTH_USER_MODEL = 'accounts.CustomUser'`
* create a new CustomUser model:
    * On the app level create a new user model `CustomUser` that extends `AbstractUser`
    * add __str__ function that returns the username.
* create new UserCreation
    * On the app level create `forms.py` file to work with users and that extends `UserCreationForm`
* Create UserChangeForm that extends `UserChangeForm`
```
from django import forms
from django.contrib.auth.forms import UserCreationForm, UserChangeForm
from .models import CustomUser

class CustomUserCreationForm(UserCreationForm):

    class Meta:
        model = CustomUser
        fields = ('username', 'email')

class CustomUserChangeForm(UserChangeForm):

    class Meta:
        model = CustomUser
        fields = ('username', 'email')
```
* update the admin
  * Finally update the admin file as below:
```
  # accounts/admin.py

from django.contrib import admin
from django.contrib.auth.admin import UserAdmin

from .forms import CustomUserCreationForm, CustomUserChangeForm
from .models import CustomUser

class CustomUserAdmin(UserAdmin):
    add_form = CustomUserCreationForm
    form = CustomUserChangeForm
    model = CustomUser
    list_display = ['email', 'username',]

admin.site.register(CustomUser, CustomUserAdmin)
```
And finally we run `python manage.py makemigrations appname`
and `python manage.py migrate`

### More to add to the `setting.py` file:

* Under Templates add ` 'DIRS': [str(BASE_DIR.joinpath('templates'))]`
* Add `LOGIN_REDIRECT_URL = 'home'`
* and `LOGOUT_REDIRECT_URL = 'home'` to the bottom of the file
`
### Templates:
At the app level:
* Create `templates/registration/login.html`
* Create `templates/registration/signup.html`
* Update the base.html and other files with the required information.
### App level Urls add:
```
from django.urls import path
from .views import SignUpView

urlpatterns = [
    path('signup/', SignUpView.as_view(), name='signup'),
]
```
### Views add:
```
class SignUpView(CreateView):
    form_class = CustomUserCreationForm
    success_url = reverse_lazy('login')
    template_name = 'registration/signup.htm
```


<br />

## References

[Django Custom User](https://learndjango.com/tutorials/django-custom-user-model)

<br />

## [<-- Back](README.md)
