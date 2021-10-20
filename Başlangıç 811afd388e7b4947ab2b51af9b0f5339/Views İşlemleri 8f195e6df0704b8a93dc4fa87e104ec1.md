# Views İşlemleri

```python
# views.py dosyası
def index(request):
    return render(request,"index.html")
def about(request):
    return render(request,"about.html")
```

```python
# urls.py dosyası
from django.contrib import admin
from django.urls import path
from article.views import index
urlpatterns = [
    path('admin/', admin.site.urls),
    path('', index,name="index"),
		path('about/',about,name="about")
]
```

```python
# index.html dosyası
<!DOCTYPE html>
{% load static %}
<html lang="en">
<head>
    <meta charset="UTF-8">
    <link rel="stylesheet" href="{% static 'css/style.css' %}">
    <title>Ana Sayfa</title>

</head>
```