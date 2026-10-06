# Django Web Framework

### Battery Include
Django-কে **"Battery Include"** ফ্রেমওয়ার্ক বলা হয় কারণ এতে সব বিল্ট-ইন ফিচার থাকে।

### Django is MVT Architecture used


* **Model:** Acts as the data interface. It defines the structure of your data and is usually backed by a database (e.g., MySQL, PostgreSQL).
* **View:** A Python function or class that handles web requests. It interacts with the Model and renders a response, typically by passing data to a Template.
* **Template:** Contains static HTML mixed with Django’s templating syntax. Templates are used to display dynamic data on the web page.

---

### 1. First Virtual Environment Create
```markdown
python -m venv environment_name
```
### 2. Environment Activate
```py
# for windows user
environment_name\Scripts\activate

# for linax user
source environment_name\bin\activate
```
### 3. Django Install
```py
# go the the pipi website search (Django install)
pip install Django

pip list # for check the django is install or not 
```

### 4. Poject Create
```markdown
django-admin startproject Project_name .
```
### 5. App Create
```py
django-admin startapp app_name
```
### Requirement.txt Generate
```py
pip freeze > requirement.txt
```
### install django version check
```py
python -m django --version
```

### Server Configuration
* **Asgi.py** and **wsgi.py** is the server of django project.