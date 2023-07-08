# API Deployment

## What are the key principles to follow when organizing and configuring Django settings for a project, according to the “Django Settings Best Practices” reading?

There is no built-in universal way to configure Django settings without hardcoding them. But books, open-source and work projects provide a lot of recommendations and approaches on how to do it best. Let’s take a brief look at the most popular ones to examine their weaknesses and strengths.

The basic idea of the following method is to extend all environment-specific settings in the settings_local.py file, which is ignored by VCS. Here’s an example:

settings.py file:

```
ALLOWED_HOSTS = ['example.com']
DEBUG = False
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'production_db',
        'USER': 'user',
        'PASSWORD': 'password',
        'HOST': 'db.example.com',
        'PORT': '5432',
        'OPTIONS': {
            'sslmode': 'require'
        }
    }
}

...

from .settings_local import *
```

settings_local.py file:

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

## How does the White Noise library contribute to the efficient serving of static files in a Django application, and what are the steps to integrate it into a project?

The WhiteNoise library is a useful tool for serving static files efficiently in a Django application, especially in production environments. It integrates seamlessly with Django and provides a lightweight middleware that can serve static files directly from the application itself, without relying on a separate web server like Nginx or Apache. This can help simplify the deployment process and improve performance.

## What is the purpose of Cross-Origin Resource Sharing (CORS) in web applications, and how can it be implemented and configured in a Django project to control access to resources?

Cross-origin resource sharing (CORS) is a mechanism that allows restricted resources on a web page to be accessed from another domain outside the domain from which the first resource was served.

For HTTP requests made from JavaScript that can't be made by using a <form> tag pointing to another domain or containing non-safelisted headers, the specification mandates that browsers "preflight" the request, soliciting supported methods from the server with an HTTP OPTIONS request method, and then, upon "approval" from the server, sending the actual request with the actual HTTP request method. Servers can also notify clients whether "credentials" (including Cookies and HTTP Authentication data) should be sent with requests.[6]

Simple request example

Suppose a user visits http://www.example.com and the page attempts a cross-origin request to fetch data from http://service.example.com. A CORS-compatible browser will attempt to make a cross-origin request to service.example.com as follows.

1. The browser sends the GET request with an extra Origin HTTP header to service.example.com containing the domain that served the parent page:

```
Origin: http://www.example.com
```

2. The server at service.example.com sends one of these three responses:

- The requested data along with an Access-Control-Allow-Origin (ACAO) header in its response indicating the requests from the origin are allowed. For example in this case it should be:

```
Access-Control-Allow-Origin: http://www.example.com
```

- The requested data along with an Access-Control-Allow-Origin (ACAO) header with a wildcard indicating that the requests from all domains are allowed:

```
Access-Control-Allow-Origin: *
```

- An error page if the server does not allow a cross-origin request[7]