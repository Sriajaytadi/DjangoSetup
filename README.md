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
