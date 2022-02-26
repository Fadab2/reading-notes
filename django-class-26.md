# Introduction to Django
### Object-relational mapper
Deﬁne your data models entirely in Python. You get a rich, dynamic database-access API for free — but you can still write SQL if needed.

### Creating models
To define a model of a rock band:
```
class Band(models.Model):

    name = models.CharField(max_length=200)
    can_rock = models.BooleanField(default=True)
```

To define model of a rock band member:
```
class Member(models.Model):
  
    name = models.CharField("Member's name", max_length=200)
    instrument = models.CharField(choices=(
            ('g', "Guitar"),
            ('b', "Bass"),
            ('d', "Drums"),
        ),
        max_length=1
    )
    band = models.ForeignKey("Band")

 ```

To design URLs for an application, you create a Python module called a URLconf. Like a table of contents for your app, it contains a simple mapping between URL patterns and your views.

```
from django.urls import path

from . import views

urlpatterns = [
    path('bands/', views.band_listing, name='band-list'),
    path('bands/<int:band_id>/', views.band_detail, name='band-detail'),
    path('bands/search/', views.band_search, name='band-search'),
]
```
```
from django.shortcuts import render

def band_listing(request):
    """A view of all bands."""
    bands = models.Band.objects.all()
    return render(request, 'bands/band_listing.html', {'bands': bands})
```

### Templates
Django’s template language is designed to strike a balance between power and ease and to be easy for developers who work with HTML
```
<html>
  <head>
    <title>Band Listing</title>
  </head>
  <body>
    <h1>All Bands</h1>
    <ul>
    {% for band in bands %}
      <li>
        <h2><a href="{{ band.get_absolute_url }}">{{ band.name }}</a></h2>
        {% if band.can_rock %}<p>This band can rock!</p>{% endif %}
      </li>
    {% endfor %}
    </ul>
  </body>
</html>

```
### Forms
Django provides a powerful form library that handles rendering forms as HTML, validating user-submitted data, and converting that data to native Python types.

```
from django import forms

class BandContactForm(forms.Form):
    subject = forms.CharField(max_length=100)
    message = forms.CharField()
    sender = forms.EmailField()
    cc_myself = forms.BooleanField(required=False)
      
```
### Authentication
Django comes with a full-featured and secure authentication system that handles user accounts, groups, permissions and cookies.

```
from django.contrib.auth.decorators import login_required
from django.shortcuts import render

@login_required
def my_protected_view(request):
    """A view that can only be accessed by logged-in users"""
    return render(request, 'protected.html', {'current_user': request.user})
```
### Admin

Django comes with automatic admin interface

```
from django.contrib import admin
from bands.models import Band, Member

class MemberAdmin(admin.ModelAdmin):
    """Customize the look of the auto-generated admin for the Member model"""
    list_display = ('name', 'instrument')
    list_filter = ('band',)

admin.site.register(Band)  # Use the default options
admin.site.register(Member, MemberAdmin)  # Use the customized options
      
```

Django offers full support for translating text into different languages
```
from django.shortcuts import render
from django.utils.translation import gettext

def homepage(request):
    """
    Shows the homepage with a welcome message that is translated in the
    user's language.
    """
    message = gettext('Welcome to our site!')
    return render(request, 'homepage.html', {'message': message})

```
```
{% load i18n %}
<html>
  <head>
    <title>{% trans 'Homepage - Hall of Fame' %}</title>
  </head>
  <body>
    {# Translated in the view: #}
    <h1>{{ message }}</h1>
    <p>
      {% blocktrans count member_count=bands.count %}
      Here is the only band in the hall of fame:
      {% plural %}
      Here are all the {{ member_count }} bands in the hall of fame:
      {% endblocktrans %}
    </p>
    <ul>
    {% for band in bands %}
      <li>
        <h2><a href="{{ band.get_absolute_url }}">{{ band.name }}</a></h2>
        {% if band.can_rock %}<p>{% trans 'This band can rock!' %}</p>{% endif %}
      </li>
    {% endfor %}
    </ul>
  </body>
</html>
```
## How Django Works Behind the Scenes

* Django is a Python-based open source web framework and was originally developed at the Lawrence Journal-World newspaper by Adrian Holovaty, Simon Willison, and Jacob Kaplan-Moss.
* Because it is an open source it has issues of funding and control.
    * Even though developers contribute for free issues like legal, trademark issues, managing releases etc have financial needs. Funding can come from Corporate sponsor (a group of engineers within a company decide to make an open-source code), Solo (someone develops a code and makes it open sources and retains control.), and Non-profit (Django's 2008)

### Django Software Foundation
Django Software Foundation maintains Django.
The DSF is run by a Board of Directors, elected annually by the ~180 individual members appointed by the DSF in recognition of their service to the Django community
* The Fellows Program, which is paid contractors who triage tickets, manage releases, and generally perform the unsexy but necessary work needed to keep Django on track is the highest expense.

* The DSF also supports projects related to Django such as the Kickstarters for Django REST Framework 3, improved PostgreSQL support, among others.


<br />

## References

[Getting started with Django](https://www.djangoproject.com/start/)
[How Django Works Behind the Scenes](https://wsvincent.com/how-django-works-behind-the-scenes/)
<br />

## [<-- Back](README.md)
