# API Deployment

### Django Best Practices

* There is no built-in universal way to configure Django settings without hardcoding them.
* Django contains things like SECRET_KEY, DB passwords tokens for APIs etc these data needs a way of sharing it with team members in a way that eliminates human error when working with settings.

### Recommendations and approaches to hard code the setting:
### settings_local.py

  * The basic idea of this method is to extend all environment-specific settings in the settings_local.py file, which is ignored by VCS. Here’s an example:

```
  ALLOWED_HOSTS = ['localhost']
DEBUG = True
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'local_db',
        'HOST': '127.0.0.1',
        'PORT': '5432',
    }
}
```

* Pros: Secrets not in VCS.
* Cons:
    * settings_local.py is not in VCS, so you can lose some of your Django environment settings.
    * The Django settings file is a Python code, so settings_local.py can have some non-obvious logic
    * You need to have settings_local.example (in VCS) to share the default configurations for developers.

### Separate settings file for each environment

* Allows you to keep all configurations in VCS and to share default settings between developers.

* Make a package as below:
```
settings/
   ├── __init__.py
   ├── base.py
   ├── ci.py
   ├── local.py
   ├── staging.py
   ├── production.py
   └── qa.py

   from .base import *


ALLOWED_HOSTS = ['localhost']
DEBUG = True
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'local_db',
        'HOST': '127.0.0.1',
        'PORT': '5432',
    }
}
```
Pros:

* All environments are in VCS
* It’s easy to share settings between developers.

Cons:
* You need to find a way to handle secret passwords and tokens.
* “Inheritance” of settings can be hard to trace and maintain.

### Environment variables
Environment variables can solve the issue of sensitive data as below using custom wrapper:
```
mport os

from django.core.exceptions import ImproperlyConfigured


def get_env_value(env_variable):
    try:
       return os.environ[env_variable]
    except KeyError:
        error_msg = 'Set the {} environment variable'.format(var_name)
        raise ImproperlyConfigured(error_msg)


SECRET_KEY = get_env_value('SECRET_KEY')
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': get_env_value('DATABASE_NAME'),
        'HOST': get_env_value('DATABASE_HOST'),
        'PORT': int(get_env_value('DATABASE_PORT')),
    }
}
```

Pros:

* Configuration is separated from code.
* Environment parity – you have the same code for all environments.
* No inheritance in settings, and cleaner and more consistent code.
* There is a theoretical grounding for using environment variables – 12 Factors.

Cons:
* You need to handle sharing default config between developers.

### 12 Factors
This recommendation collection consists of 12 factors and was created by Heroku:

1. Codebase
2. Dependencies
3. Config
4. Backing services
5. Build, release, run
6. Processes
7. Port binding
8. Concurrency
9. Disposability
10. Dev/prod parity
11. Logs
12. Admin processes

It is better to use django environ instead of os.environ as on the settings.py below:

```
import environ


root = environ.Path(__file__) - 3  # get root of the project
env = environ.Env()
environ.Env.read_env()  # reading .env file

SITE_ROOT = root()

DEBUG = env.bool('DEBUG', default=False)
TEMPLATE_DEBUG = DEBUG

DATABASES = {'default': env.db('DATABASE_URL')}

public_root = root.path('public/')
MEDIA_ROOT = public_root('media')
MEDIA_URL = env.str('MEDIA_URL', default='media/')
STATIC_ROOT = public_root('static')
STATIC_URL = env.str('STATIC_URL', default='static/')

SECRET_KEY = env.str('SECRET_KEY')

CACHES = {'default': env.cache('REDIS_CACHE_URL')}
```

### Naming Conventions
* Give meaningful names.
* Use prefix with project name
* Write descriptions for settings.
Example of good practice:
```
# Run job for getting new tweets.
# Accept string in crontab format. By default: every 30 minutes.
MYAWESOMEPROJECT_TWEETS_API_SYNC_CRONTAB = env.str(
    'MYAWESOMEPROJECT_TWEETS_API_SYNC_CRONTAB', default='30 * * * *'
)
```
### How Does SSH Work

* SSH operates on TCP port 22 by default.
* SSH allows users to access, control, and modify their remote servers over the internet.
* SSH uses 3 different encryption technologies:
  * Symmetrical encryption
    * secret key is used for both encryption and decryption of a message by both the client and the host.
    * client and the server derive the secret key using an agreed method, and the resultant key is never disclosed to any third party.
  * Asymmetrical encryption
    * uses two separate keys `public key and the private key.` for encryption and decryption.
  * Hashing
    * differs from the above two forms of encryption in the sense that they are never meant to be decrypted.
    * if a client holds the correct input, they can generate the cryptographic hash and compare its value to verify whether they possess the correct input.
    * SSH uses hashes to verify the authenticity of messages.

Passowrds are used to authenticae users before allowing them access.


<br />

## References

[Configuring Django Settings: Best Practices](https://canvas.instructure.com/courses/3826570/discussion_topics/13181460)

[How Does SSH Work](https://www.hostinger.com/tutorials/ssh-tutorial-how-does-ssh-work)

<br />

## [<-- Back](README.md)
