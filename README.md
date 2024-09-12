git commit -m "Initial project setup"
git push origin main
property_management/
│
├── property_management/          # Django project folder
│   ├── __init__.py
│   ├── asgi.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
│
├── tenants/                      # Django app folder
│   ├── __init__.py
│   ├── admin.py
│   ├── apps.py
│   ├── models.py
│   ├── tests.py
│   └── views.py
│
├── manage.py
└── requirements.txt              # Optional: for dependencies

INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'tenants',  # Add your app here
]

from django.db import models

class Tenant(models.Model):
    first_name = models.CharField(max_length=100)
    last_name = models.CharField(max_length=100)
    email = models.EmailField(unique=True)
    phone_number = models.CharField(max_length=15)
    lease_start_date = models.DateField()
    lease_end_date = models.DateField()

    def __str__(self):
        return f"{self.first_name} {self.last_name}"

        from django.contrib import admin
from django.urls import path

urlpatterns = [
    path('admin/', admin.site.urls),
]

from django.http import HttpResponse

def index(request):
    return HttpResponse("Welcome to the Tenants app!")

    from django.urls import path
from . import views

urlpatterns = [
    path('', views.index, name='index'),
]

from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('tenants/', include('tenants.urls')),
]

git clone <repository-url>

cd property_management

python -m venv env

.\env\Scripts\activate

source env/bin/activate

source env/bin/activate

pip install -r requirements.txt

python manage.py makemigrations
python manage.py migrate

python manage.py runserver



