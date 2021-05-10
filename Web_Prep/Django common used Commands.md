# Django common used Commands

View the python code with HackMD.

Reference Website
---
- https://www.learncodewithmike.com/2020/04/django-heroku.html
- https://developer.mozilla.org/zh-TW/docs/Learn/Server-side/Django/skeleton_website
- https://www.chunhongweb.com/django-tutorial-ep-one/
- https://www.learncodewithmike.com/2020/03/django-install.html
- https://ycy-tai.medium.com/django-beginner-05-%E8%A8%AD%E5%AE%9Atemplates%E8%B7%AF%E5%BE%91%E5%92%8C%E5%BB%BA%E7%AB%8B%E9%A6%96%E9%A0%81-b309ba394f0d
- https://yanwei-liu.medium.com/django-with-bootstrap-template-e814e6c89f73
- https://stackoverflow.com/questions/58786743/how-can-i-view-my-html-page-in-python-using-django
- https://djangobook.com/mdj2-django-templates/
- https://djangogirlstaipei.gitbooks.io/django-girls-taipei-tutorial/content/django/admin.html

Django Create Project
---
- django-admin startproject [name]
- python manage.py startapp [name]
- {at settings.py [installed_apps]} [appname],
- 


Django Templates
---
- mkdir templates
- {at settings.py [templates[dirs]]} os.path.join(BASE_DIR,'templates').replace('\\', '/')
- {when change about model} python manage.py makemigrations
python manage.py migrate
- create views 
def [name](request):
    1. return render(request, 'hello_world.html', {
        'current_time': str(datetime.now()),
    })
    2. return HttpResponse("Hello KKKKKKKKKKKKK!")
    3. return render(request,"test_index.html",{})
- 


#### - 若新增APP於django需要在settings.py 的Installed_APPS中加入APP名稱
- 編輯models.py:建立資料庫表格
- 編輯views.py:import在models.py中建立的資料模型
- 於跟目錄的admin.py中新增:from mysite.models import NewTable EX(from .models import Post)
- admin.site.register(NewTable) EX(admin.site.register(Post, PostAdmin))
- 

At admin SQLite create schema
---
- {models.py}
    class Post(models.Model):
    title = models.CharField(max_length=100)
    content = models.TextField(blank=True)
    photo = models.URLField(blank=True)
    location = models.CharField(max_length=100)
    created_at = models.DateTimeField(auto_now_add=True)
    created_at = models.DateTimeField(auto_now_add=True)

    def __str__(self):
        return self.title
- admin.py register
    from BCD_web.models import Post
    admin.site.register(Post)

URLS setting
---
- need
    from django.conf.urls import include, url
from django.contrib import admin
from django.urls import path
- create yourself
    from BCD_web.views import hello_world, hello_world_index, test_index
- url patterns ex:
    path('admin/', admin.site.urls),
    url(r'^hello/$', hello_world),
    url(r'^test/$', hello_world_index),
    path('', test_index, name="test_index"),
- [Features](/s/features)

Settings
---
- Change Base Dir
    BASE_DIR = os.path.dirname(os.path.dirname(os.path.abspath(__file__)))
- Static Root
    STATIC_ROOT = os.path.join(BASE_DIR, 'static')
    STATIC_URL = '/static/'
- Installed apps
    {at Installed_apps}
    '[app-name]',
- Database Base SQLite
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': os.path.join(BASE_DIR, 'db.sqlite3'),
    }
- Database PGSQL
    'default': {
        'ENGINE': 'django.db.backends.postgresql',                                          #PostgreSQL
        'NAME': 'd7eu9qsublnd6e',                                                           #資料庫名稱
        'USER': 'lvbstcegsalqac',                                                           #資料庫帳號
        'PASSWORD': 'a1001590e6979b1c0dcc8ac371462f756c1b8c5f8db7cb7d3c1df952323bf011',     #資料庫密碼
        'HOST': '184.73.198.174',                                                           #Server(伺服器)位址
        'PORT': '5432'                                                                      #PostgreSQL Port號
    }


Rex Tsou 2021/05/08

###### tags: `Django` `Templates` `SQL`
