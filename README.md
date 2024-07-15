# x-vision-cloud
python --version 
посмотреть версию python

python -m venv .venv 
создаем окружжение
source .venv/bin/activate 
активируем окружение 
pip install django 
устанавливаем джанго

django-admin startproject website
создаем корневое приложение в django

cd website
переходим в паку корневого приложения , там находится manage.py

python manage.py startapp xvision
Создаем наше приложение 

Далее settings.py нужно добавить наже приложение в список INSTALL_APPS.

В Urls корневого приложения добавляем.
path('', include('xvision.urls')),

В нашем приложении создаем файл Urls и прописываем.
from django.urls import path
from . import views
urlpatterns = [
    path("", views.index, name="index"),
]

В корневой папке приложения создаем папку Шаблонов
tamplates и static

Прописываем пути
import os
Для шаблонов:
TEMPLATE_DIR = os.path.join(BASE_DIR, 'templates')
TEMPLATES = ..."DIRS": [TEMPLATE_DIR,],
Для статических файлов:
STATICFILES_DIRS = [ os.path.join(BASE_DIR, "static")]
