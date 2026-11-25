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