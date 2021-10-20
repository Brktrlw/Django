# Model İşlemleri

### Model oluşturma

```python
class Article(models.Model):
    author     = models.ForeignKey("auth.User",on_delete=models.CASCADE,verbose_name="Yazar")   # on_delete ile kullanıcı silinirse makalelerin de silineceğini sağlar | verbose_name= admin panelinde türkçe gözükmesini sağlar
    title      = models.CharField(max_length=50)
    content    = models.TextField()
    createdDate= models.DateTimeField(auto_now_add=True)                   # auto_now_add= suanki tarihi alır
```

### Modeli admin panelinde gösterme

```python
# admin.py dosyasında ekle
from .models import Article
admin.site.register(Article)
```

### Settings dosyasına uygulamayı yazma

```python
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'article',                 # buraya ekliyoruz
]
```

### Uygulamanın veritabanı tablolarını olusturmak için gerekli initial dosyasını olusturma

```python
python manage.py makemigrations
```

### Tabloları olusturma

```python
python manage.py migrate
```