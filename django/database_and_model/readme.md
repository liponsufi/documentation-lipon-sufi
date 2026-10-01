# Database Setup and Model & Relationship

### Configuration PostgreSQL in Django

By default django given a database name of SQL lite, that is a lite weight database 

- now we have to use postgreSQL so go to [settings.py](http://settings.py) and comment the  databases dictionary that given by default
- go to google and search postgre connection in django then paste to the databases dictionary of postgre connection with django and configure the code in  [settings.py](http://settings.py) ( have to install a package first) - psycopg-binary
- by default django needed some table so that have to go terminal and commend run Python [manage.py](http://manage.py) migrate

### Define Model & field & Relationship

**how to create table in django**

- go to app level models.py
- everything is writing with model fields

```python
from django.db import models

class Task(models.Model):
    title=models.CharField(max_length=250)
    drescripton=models.TextField()
    due_date=models.DateField()
    is_completed=models.BooleanField(default=False)
    created_at=models.DateTimeField(auto_now_add=True)
    updated_at=models.DateTimeField(auto_now=True)
```

- query written by class and have to convert the class to SQL because postgre only or know use SQL query
- go to terminal for convert the class to SQL ( python [manage.py](http://manage.py) makemigrations ) after the run this commend then see a updated in the app folder in migration in created a file name initial.py
- and run python [manage.py](http://manage.py) migrate ( created a table )
- Choice in  model field

```python
class Task_details(models.Model):
    PRIORITY_CHOICE=(
        ('H','High'),
        ('M','Medium'),
        ('L',"Low")
    )
   assigned_to=models.CharField(max_length=100)
   priority=models.CharField(max_length=1,choices=PRIORITY_CHOICE,default="L")
```

### One to One Relationship

- in these table is dependent another table like parent and child table have to added relation in the child table ( write models.OneToOneField( table_name, On_delete ))
- Use there foreign key on_delete attibute  here and have more on delete option

### Introduction to Django Shell

- python [manage.py](http://manage.py) shell
- in google se how to query data write ( django model )
- first have to import the table ( like from app_name.models import table_name ) in django  we are  not calling it table_name we are calling it model

```json
//for get any object from database
task = Task.objects.get(id=1)
//Project is the name of class name mean table name
Project.objects.create()
//database thaka all data show kore Project table er 
project=Project.objects.all()

//for second project
projects = Project.objects.all()
second_project = projects[1] # 0 hole prothom, 1 hole ditiyo
print(second_project)
```

### Many to One Relationship

- Many to one relationship write which table is dependent to the parent ( models.ForeignKey ( table_name, on_delete ) )

### Many to Many Relationship