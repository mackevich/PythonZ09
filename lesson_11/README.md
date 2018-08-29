# Useful links

* Туториал от разработчиков Django: https://docs.djangoproject.com/en/2.1/intro/
* Почти тоже самое, только на русском (проект больше не развивается, вероятно,
что вы встретите некоторые отличия в работе программы): https://djbook.ru/rel1.9/

# Tasks:

#1 Подготовить окружение:
 * Открыть terminal (linux & macos) или powershell (windows);  
 * создаем папку под проект: `mkdir my_awesome_project`  
 * создаем виртуальное окружение: `virtualenv env`  
 * запускаем виртуальное окружение: `source env/bin/activate`  
 * устанавливает Django: `pip install django`  
 * создаем новый django-проект `django-admin startproject my_awesome_project`  
 * переходим в django-проект `cd my_awesome_project`
 * запускаем сервер находясь в папке с файлом manage.py `./manage.py runserver`  
 * открываем в браузере `http://127.0.0.1:8000/`  
 * создаем django-приложение `django-admin startapp test_app`  
 * в test_app в файле views.py пишем:
```python
from django.http import HttpResponse


def my_view(request):
    return HttpResponse('<h1>My project working!</h1>')

```
* идем в `my_awesome_project/settings.py`, ищем list `INSTALLED_APPS` и добавляем туда строку с названием
нашего созданного аппа: test_app  
* в `my_awesome_project/urls.py`, `urlpatterns` добавляем новую запись: `
    path('', my_view),` а также импортируем наш новый вью - `from test_app.views import my_view`.  