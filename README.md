# docker-django

Create your project
```
docker-compose run web django-admin.py startproject yourprojectname .
```

Configure in setting.py for your MySql
```
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'django',
        'USER': 'root',
        'PASSWORD': 'root',
        'HOST': '192.168.0.10',
        'PORT': 3306,
    }
}
```

Build your docker
```
docker-compose build
```

Run docker
```
docker-compose up
```

Run docker in background
```
docker-compose up -d
```

Migrate the database
```
python3 manage.py migrate
```


If you get allowed hosts error when opening the page change settings.py line 28
from
```
ALLOWED_HOSTS = []
```
to
```
ALLOWED_HOSTS = ['*']
```

If you need to install any packages in Django, include them in ./requirements.txt, and rebuild your docker again with docker-compose build.
