## 프로젝트 초기 셋팅
### 1. 내가 사용할 앱 등록
``` python
INSTALLED_APPS = [
    'django.contrib.admin',             # 어드민
    'django.contrib.auth',              # 회원-인증
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',

    # '생성한 app이름', <- 쉼표 잊지말고 꼭 쓰기(나중에 안까먹어요.)
]
```

### 2. template 셋팅
(1) 프로젝트 폴더/templates 폴더를 생성하기
(2) settings.py에서 templates 경로 설정
``` python
import os  # 맨위에
...
TEMPLATES = [
    {
        'BACKEND': 'django.template.backends.django.DjangoTemplates',
        # 프로젝트의 templates 폴더를 템플릿 경로로 등록
        'DIRS': [os.path.join(BASE_DIR, "templates")],
        ...
    },
]
```


### 3. static 셋팅
(1) 프로젝트폴더/static 폴더를 생성하기
(2) settings.py에서 static 경로 설정

```python
STATIC_URL = 'static/'
STATIC_ROOT = BASE_DIR
```


### 4. Time 셋팅
UTC(국제 표준시) 한국은 UTC +9
```python
TIME_ZONE = 'Asia/Seoul'
```



## 앱생성하기
### 1. 앱생성하기
```
$ django-admin startapp 앱이름
```

### 2. settings.py에 앱 등록하기
``` python
INSTALLED_APPS = [
    'django.contrib.admin',             # 어드민
    'django.contrib.auth',              # 회원-인증
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',

    # '생성한 app이름', <- 쉼표 잊지말고 꼭 쓰기(나중에 안까먹어요.)
]
```

### 3. 앱별로 urls.py vkdlf생성후 config/urls.py에 연결하기
- config/urls.py에다가 앱별로 만든 urls.py를 연결하기

```python
from django.contrib import admin
from django.urls import path,include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include("feed.urls"))
]

```

### 4. 앱별 urls.py에서 메인 함수를 생성하기
(1) 앱이름/urls.py
```python
from django.urls import path
from . import views

urlpatterns = [
    path('', views.main, name='main')
]
```

(2) 앱이름/views.py
```python
from django.shortcuts import render
from django.http import HttpResponse

# Create your views here.

def main(request):
    return HttpResponse('하이루')
```




