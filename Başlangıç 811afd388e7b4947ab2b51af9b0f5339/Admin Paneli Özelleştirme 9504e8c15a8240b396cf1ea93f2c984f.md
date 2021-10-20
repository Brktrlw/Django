# Admin Paneli Özelleştirme

```python
#admin.py dosyası
@admin.register(Article)
class ArticleAdmin(admin.ModelAdmin):
		list_display = ["title","author","createdDate"] # admin tablosunda yazar ve olusturma tarihini göstermesini sağlar
		list_display_links = ["title","createdDate"]    # olusturma tarihine de link verir
		search_fields = ["title"]                       # admin sayfasına arama cubugu ekler ve title bilgisine göre arama yaptırır
    list_filter = ["createdDate"]                   # sağ tarafa "Süz" filtreleme işlemi yapan yeri getirir
		class Meta:
        model=Article
```

![Untitled](Admin%20Paneli%20O%CC%88zelles%CC%A7tirme%209504e8c15a8240b396cf1ea93f2c984f/Untitled.png)