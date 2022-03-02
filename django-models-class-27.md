# Using models
* Models are Python objects that define the structure of stored data that is used by Django web applications.
* It is better to have a separate models for every related group of information.
* Models are better options for things like drop-down options/lists instead of hardcoding it.
* Django allows to define the relationships between models as:
    *  one to one
    *  one to many
    *  many to many.

### Model definition
Below is how to define a model:
```
from django.db import models

class MyModelName(models.Model):
    """A typical class defining a model, derived from the Model class."""

    # Fields
    my_field_name = models.CharField(max_length=20, help_text='Enter field documentation')
    ...

    # Metadata
    class Meta:
        ordering = ['-my_field_name']

    # Methods
    def get_absolute_url(self):
        """Returns the url to access a particular instance of MyModelName."""
        return reverse('model-detail-view', args=[str(self.id)])

    def __str__(self):
        """String for representing the MyModelName object (in Admin site etc.)."""
        return self.my_field_name
```
* Models can have any number of fields of any data type. These fields represent column to store database. As in the below code our field will store strings of characters and numbers.
`my_field_name = models.CharField(max_length=20, help_text='Enter field documentation')`
* Field names are used for reference when queries and templates.

### Common field arguments:

* help_text: Provides a text label for HTML forms.
* verbose_name: A human-readable name for the field used in field labels. 
* default: The default value for the field. 
* null: If True, Django will store blank values as NULL in the database for fields where this is appropriate.
* blank: If True, the field is allowed to be blank in your forms. 
* choices: A group of choices for this field. If this is provided, the default corresponding form widget will be a select box with these choices instead of the standard text field.
* primary_key: If True, sets the current field as the primary key for the model (A primary key is a special database column designated to uniquely identify all the different table records). If no field is specified as the primary key then Django will automatically add a field for this purpose.

### Common field types:

* CharField is used to define short-to-mid sized fixed-length strings. You must specify the max_length of the data to be stored.
* TextField is used for large arbitrary-length strings. You may specify a max_length for the field, but this is used only when the field is displayed in forms (it is not enforced at the database level).
* IntegerField is a field for storing integer (whole number) values, and for validating entered values as integers in forms.
* DateField and DateTimeField are used for storing/representing dates and date/time information (as Python datetime.date in and datetime.datetime objects, respectively).
* EmailField is used to store and validate email addresses.
* FileField and ImageField are used to upload files and images respectively (the ImageField adds additional validation that the uploaded file is an image).
* AutoField is a special type of IntegerField that automatically increments.
* ForeignKey is used to specify a one-to-many relationship to another database model (e.g. a car has one manufacturer, but a manufacturer can make many cars).
* ManyToManyField is used to specify a many-to-many relationship (e.g. a book can have several genres, and each genre can contain several books).



## Django admin site

* The Django admin application can use models to automatically build a site area that you can use to create, view, update, and delete records.
* The admin application can also be useful for managing data in production, depending on the type of website.
* Models must be registered to the admin application.

### Registering models
```
from .models import Author, Genre, Book, BookInstance

admin.site.register(Book)
admin.site.register(Author)
admin.site.register(Genre)
admin.site.register(BookInstance)
```

### Creating a superuser

* In order to log into the admin site, we need a user account with Staff status enabled and have the permissions to manage all data.
* Super user account has full access to the site. Super user can be created using;
` python3 manage.py createsuperuser`

<br />

## References

[Django Tutorial Part 3: Using models](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Models)

[Django Tutorial Part 4: Django admin site](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Admin_site)
<br />

## [<-- Back](README.md)
