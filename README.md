
# Github account and new repository
- Open a github account
- Create a repository named python learning
- create a file Readme.md

# What is markdown
- .md file extension
- Readme.md - In github repository it will by default look for Readme.md file
- If file exists it will show the file contents
- Mark down is simple way to write htm type page using text

- #  heading H1
- ## heading H2
- - dash and space (bullets)
- ``` (ticks)  coding box```
- ** (double stars) bold


# Installing python in windows 10

https://www.freecodecamp.org/news/how-to-install-python-in-windows-operating-system/

- **check python is installed or not**

```
C:\Users\mukun>python --version
```

Follow the url https://www.freecodecamp.org/news/how-to-install-python-in-windows-operating-system/

- download

![](https://i.imgur.com/SP1xNys.png)




- Use custom installation

![](https://www.freecodecamp.org/news/content/images/2022/02/06.png)

- Make sure to check all of the boxes,

![](https://www.freecodecamp.org/news/content/images/2022/02/07.png)

- Next select the following

![](https://www.freecodecamp.org/news/content/images/2022/02/08.png)

- max_path

If you get this type of prompt to disable the path length limit, then simply click on that box. It disables the path length limit by removing the limitation on the MAX_PATH variable.

This change will not break anything, or make any negative changes. It will just allow Python to use long path names. It is recommended to disable the path length limit.

![](https://i.imgur.com/5J1Y1J8.png)

- Successfully installed

```
C:\Users\mukun>python --version
Python 3.10.4
```

# Python virtual environment

- pip command : this will install python packages Eg: Django, numpy, pandas, requests, scipy
- pip install Django
- this will install system wide
- But we dont want to install it system wide, we only want to install for a particular project
- Thas why we have to create virtual environment

## STEP1: command to create virtual env (First Time)
```
python -m venv venv
```
The above command will craete a folder called venv as shown in the below iamge

![](https://i.imgur.com/UnJH74P.png)

## STEP2: Activate the virtual environment (Everytime before you run python)

```
C:\Users\mukun\Desktop\django>.\venv\Scripts\activate.bat

(venv) C:\Users\mukun\Desktop\django>
```
The below image shows how to activate virtual environment. 

![](https://i.imgur.com/Fjfc5oQ.png)

# Installing Django

```
(venv) C:\Users\mukun\Desktop\django>pip install django
```

The output will be 
```
Collecting django
  Downloading Django-4.0.3-py3-none-any.whl (8.0 MB)
     ---------------------------------------- 8.0/8.0 MB 94.2 kB/s eta 0:00:00
Collecting sqlparse>=0.2.2
  Downloading sqlparse-0.4.2-py3-none-any.whl (42 kB)
     ---------------------------------------- 42.3/42.3 KB 29.7 kB/s eta 0:00:00
Collecting asgiref<4,>=3.4.1
  Downloading asgiref-3.5.0-py3-none-any.whl (22 kB)
Collecting tzdata
  Downloading tzdata-2022.1-py2.py3-none-any.whl (339 kB)
     ---------------------------------------- 339.5/339.5 KB 100.3 kB/s eta 0:00:00
Installing collected packages: tzdata, sqlparse, asgiref, django
Successfully installed asgiref-3.5.0 django-4.0.3 sqlparse-0.4.2 tzdata-2022.1

(venv) C:\Users\mukun\Desktop\django>
```

![](https://i.imgur.com/nG3kXxO.png)

django package is installed in `C:\Users\mukun\Desktop\django\venv\Lib\site-packages`

This image shows packages installed along with django Eg: asgiref, sqlparse, tzdata

![](https://i.imgur.com/oxKcSyW.png)

# Checking django version

```
(venv) C:\Users\mukun\Desktop\django>django-admin --version
4.0.3

(venv) C:\Users\mukun\Desktop\django>
```
# Create new django project

```
(venv) C:\Users\mukun\Desktop\django>django-admin startproject testing

(venv) C:\Users\mukun\Desktop\django>
```
This will create a new folder called testing

![](https://i.imgur.com/cv8z5ei.png)

# Running django server

```
(venv) C:\Users\mukun\Desktop\django>cd testing

(venv) C:\Users\mukun\Desktop\django\testing>python manage.py runserver
Watching for file changes with StatReloader
Performing system checks...

System check identified no issues (0 silenced).

You have 18 unapplied migration(s). Your project may not work properly until you apply the migrations for app(s): admin, auth, contenttypes, sessions.
Run 'python manage.py migrate' to apply them.
March 25, 2022 - 20:55:59
Django version 4.0.3, using settings 'testing.settings'
Starting development server at http://127.0.0.1:8000/
Quit the server with CTRL-BREAK.
```

![](https://i.imgur.com/OcoVXpI.png)


# EDITOR vscode

open the project in vscode editor

```
C:\Users\mukun\Desktop\django>code -n .
```

![](https://i.imgur.com/6zTfGyU.png)

by running 

```
django-admin startproject testing
```

We see the below files getting created

![](https://i.imgur.com/LjMKuMb.png)


also `manage.py` is used in `python manage.py runserver` command


# create a new application called basic

```
C:\Users\mukun\Desktop\django>.\venv\Scripts\activate.bat

(venv) C:\Users\mukun\Desktop\django>cd testing

(venv) C:\Users\mukun\Desktop\django\testing>django-admin startapp basic

(venv) C:\Users\mukun\Desktop\django\testing>
```

![](https://i.imgur.com/s0kcZJY.png)

It will create a new folder called basic

# add basic inside INSTALLED_APPS 

`testing > settings.py`

```
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'basic.apps.BasicConfig',
]
```

![](https://i.imgur.com/TlGiT4W.png)


# How to create a url

## create a template/html file

create

`basic > templates > basic > basic.html `

![](https://i.imgur.com/z8mtcCG.png)

```
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Homepage</title>
</head>
<body>
    <h1>Basic Page</h1>
</body>
</html>
```


## create a view

![](https://i.imgur.com/Y8RHotp.png)

```
# import Http Response from django
from django.shortcuts import render
  
# create a function
def basic_view(request):
    return render(request, "basic/basic.html")
```

## create a url

![](https://i.imgur.com/CNJWAIq.png)

```
from django.contrib import admin
from django.urls import path
from basic.views import basic_view

urlpatterns = [
    path('admin/', admin.site.urls),
    path('basic/', basic_view),
]
```



# Python
Python Django installation and creation of Virtual server

# Creating static files

Static files means
- images
- css
- js


```
Structure:
testing (django-admin startproject testing)
|--testing (django-admin startproject testing)
|----|
|    |--settting.py (we have to new apps created using django-admin, example django-admin startapp basic
|    |--urls.py (we have to mention the urls)
|
|--manage.py (python manage.py runserver) (created by django-admin startproject testing)
|--basic (django-admin startapp basic) (we added basic inside settings.py)
    |--templates
    |     |--basic
    |          |--basic.html
    |          |--contact.html
    |
    |--static  (to use these, mention the url as "/static/images/test.jpg" in the template file)
         |--css
         |--js
         |--images
```

# Downloading and installing bootstrap
  Compiled CSS and JS
https://getbootstrap.com/docs/5.0/getting-started/download/

Download the zip file

and place bootstrap.min.css in static/css folder

and place bootstrap.bundle.min.js in static/js folder

And write this template

```
<html> 
<head>
    <link href="/static/css/bootstrap.min.css" rel="stylesheet">
</head>
<body>
    <script src="static/js/bootstrap.bundle.min.js"></script>
</body>
</html>
```


# CRUD

![](https://i.imgur.com/7wTQFyP.png)

# Task

Create new app called students <-- inside this create templates, students.html, students_edit.html, students_delete.html

create 3 urls also
```
/students
/students/edit  <--- /students/<int>/edit
/students/delete <--- /students/<int>/delete
```
# Views page

![](https://imgur.com/M6vnjUw.png)
