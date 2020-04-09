##Django 설정 방법

####environment : python 3.7, Windows 10, db : sqlite3, IDE : Pycharm

1. 가상환경 만들기 (python -m venv [폴더명])
    cmd 내에서 원하는 폴더로 이동한 뒤 가상환경을 만든다.
    ```python -m venv kvenv```

2. 가상환경 사용하기 (activate)
    가상환경이 만들어지면 해당 폴더 내에 kvenv\Scripts 폴더가 생성이 되는데 Scripts까지 이동한뒤</br>
    cmd에 activate를 입력하여 가상환경을 사용한다.

3. Django 설치
    다시 kvenv까지 돌아와서 Django를 설치한다.
    ```
    python -m pip install --upgrade pip
    pip install django~=2.0.0
    ```

4. Django 프로젝트 생성
    Django 프로젝트를 생성시킨다.
    ```
    django-admin start project "프로젝트 이름"
    ```

5. settings.py 설정
    ```
    LANGUAGE_CODE = 'ko'
    TIME_ZOME='Asia/Seoul'
    ```

6. DB설정(settings.py)
    ```
    DATABASES = {
        'default': {
            'ENGINE': 'django.db.backends.sqlite3',
            'NAME': os.path.join(BASE_DIR, 'db.sqlite3'),
        }
    }
    ```

7. sqlite3 migration
    프로젝트 폴더에 들어간 다음 migrate
    ```python manage.py migrate```

8. 서버 구동
    ```python manage.py runserver```

9. 어플리케이션 만들기
    python manage.py startapp "어플리케이션 이름"

10. 서버에 앱 등록 (settings.py)
    ```
    INSTALLED_APPS = [
        "어플리케이션 이름",
    ]
    ```

11. django.contrib.auth 사용(settings.py)
    ```
    INSTALLED_APPS = [
        'django.contrib.auth',
    ]
    ```


출처 : https://kev1n.tistory.com/34