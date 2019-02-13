# hello-world-django

## Install Django
```
pip installl django==1.11
```
### Create blank Project
```
django-admin.py startproject hello-world
```
### Create Django App
```
python manage.py startapp hello
```

#### Go in hello-world/settings.py

Installed_apps is basically the apps that you are going to make in this django_project
```
INSTALLED_APPS = [
    ..... ,
    .... ,
    'hello'
   ]
```

#### Check if server is formed
```
python manage.py runserver 0.0.0.0:8080
```

#### Go in hello/views.py

```
from Django.http import HttpResponse

def homePageView(request):
    return HttpResponse('Hello World')
```

#### In hello directory create a urls.py File
##### hello/urls.py
```
from django.conf.urls import url
from .views import homePageView

urlpatterns = [
    url('',homePageView, name = 'home')
  ]
```
Now link this in project's url file

#### Go in hello-world/urls.py
```
urlpatterns = [
    ....,
    url('',include('hello.urls'))
  ]
#### Now Runserver 
```
python manage.py runserver 0.0.0.0:8080
```
Go to your browser and go to http://127.0.0.1:8080

The hello world will appear in your browser
