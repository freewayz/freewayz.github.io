---
layout: post
title: Gentle introduction to Django Web Framework
comments: true
share: true
date:   2017-03-25
categories: python django web
---

> Django is a very high scalable python web framework .
Having started learning django some years back, I have found it to be the most complete web framework, (my personal opinion).

## Django web principle
One of the most important concept of any web framework, is some kind of pattern the framework follow to acheive it fuctionality.
* Model View Controller ( most web framework)
* Model View Presenter eg (GWT, GWTP)
* Model View View Pattern
* Model Template View

As such django follows the  MVT or MTV (Model View Template) pattern.


# The MVT (Model View Template)
![Django MVT]({{site.url}}/public/assets/images/django-in-a-nutshell.png "Project file")

* Model : which tells how your data looks, simple how you represent your table structure in 
        any database system.

* View:  one of the main heart of django web framework, view serves as the main controllers of the application, 
       most of your business logic are done here, also it act as way of taking data from 
       your model and representing it into your template html code which is then processed 
       and presented to the client. 


* Template: the main presentation layer for django, where most of your html code reside
         the template comes with lot of functionality from 
         
         - performing iterations
         - user permissions checks
         - logic conditions
         - filters, date manipulations,
         - composable and reusable html code (inheritance)


Lastly,  one thing that is also very important to note is the `URLs` which is a 
very important part of django, basically anytime a client visit your website 
by hitting `www.website.com/hellohumans`, which means  your url contain a configuration
on what that url maps to.


# The Gentle Introduction
* First  I am using an ubuntu machine
* Python 2.7 (but you can use any version of python you have as at this time of reading)
* Python virtual environment (if you are using python3.4 up it comes with venv so no need for any configuration )

1. Creating a directory where our django project will be stored
``` bash
$ mkdir myfirstdjangoproject
```
If you dont want  to make use of virtual environment you can skip and jump straight to `step 3`.
2.  Creating a  virtual environment 
```bash
$ pip install virtualenv
# the python can point to any version of your python 
$ virtualenv -p /usr/bin/python2.7 django_webs 
# to make our virtual environment active
$ source django_webs/bin/activate 
```
3.  Navigating into the directory so we install our django framework
```bash
$ cd myfirstdjangoproject
$ pip install django 
$ django-admin startproject firstapp
```
> Our project structure should look like this now

![project structure]({{site.url}}/public/assets/images/structure1.png "Project file")

## What does this files means?
- `manage.py` basically the power engine room for all django commands, from database maintenance, to administrative task]
- `firstapp/settings.py` this contain all our project configurations, like database to use, custom app to include, templating system
- `firstapp/urls.py` contain url to our different apps inside a django project.
- `firstapp/wsgi.py` [our application server to power our simple django application]

## Creating a simple store app app

```bash
$ django-admin startapp store 
```

>Next inside our `INSTALLED_APP` variable located inside
 the `settings.py` file,  we append the name of our apps at the bottom of the list

```python 
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'store'
]
```
Now our project structure should look like this
![project structure2]({{site.url}}/public/assets/images/structure-2.png "Project file")

## Start django server so we can start development

```bash 
$./manage.py runserver
```

> To make sure everything is ok visit `127.0.0.1:8000` so you should see an output  `It worked.`

## View
Let start with a simple view that show Welcome to django store 
- Open our `views.py` inside our store app

```python 
from django.shortcuts import render
def landing_page(request):
	return render(request, template_name="store/index.html", context={})
```


## Template 
We want to have our html code live some where in our code. So the first step
 - create a directory inside our store app `mkdir -p templates/store`
 - next we want to modify our  django `settings.py` 
 - an look for the variable `TEMPLATE` and change `'DIRS': []` to `'DIRS': ['templates']`
All we did here is to tell django where our templates 
 - create and html file called `index.html` in our new `templates/store` folder

```html
<html>
	<head>
		<title>Store App</title>
	</head>
	<body>
		Hello welcome to our store app
	</body>
</html>
```


## URL 
> As a part of all web application we need a routing process, on how users move from
page to another page. The url in django contains the information about that.

Create a file called `urls.py` inside your `store` app folder then we 
configure our url so  when the user visit our site by going to `127.0.0.1:8000/store`
we tell our view `landing_page` to handle that request and do some stuff with it.


```python
from django.conf.urls import url
from .views import landing_page
urlpatterns = [
	url(r'^$', view=landing_page, name="landing-page")
]
```

> Finally  we need to include the `store.urls` inside our main django project url 
due to django project app structure.

- Open our `urls.py` file under our project folder called `firstapp`
- Append this  code snippet to the list which already has `url(r'^admin/', admin.site.urls)`
```python
    url(r'^store/', include('store.urls'))
 ``` 

Now visit `127.0.0.1:8080/store`

![Project Live]({{site.url}}/public/assets/images/success-store.png "Success store app")

Thanks. more info can be found on  [Django Website](https://www.djangoproject.com/) 