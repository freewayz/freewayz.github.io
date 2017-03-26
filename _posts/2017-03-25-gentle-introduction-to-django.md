---
layout: post
title: Gentle introduction to Django Web Framework
comments: true
share: true
date:   2017-03-25
categories: python django web
---

Django is a very high scalable web framework for perfectionist dead line.
Having started learning django some years back, have found it to be the most complete web framework. (my personal opinion)

## Django web principle
One of the most important concept of any software component, is the pattern used in the developing the 
software, as such Django follows a principle called the MVT


# The MVT (Model View Template)
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
         - composable and reusable html code (inheritance)


Lastly,  one thing that is also very important to note is the `URLs` which is a 
very important part of django, basically anytime a client visit your website 
by hitting `www.website.com/hellohumans`, which means  your url contain a configuration
on what that url maps to.


# The Gentle Introduction
First  I am using an ubuntu machine
Python 2.7 (but you can use any version of python you have as at this time of reading)
Python virtual environment (if you are using python3.4 up it comes with venv so no need for any configuration )

1. Creating a directory where our django project will be stored
``` bash
$ mkdir myfirstdjangoproject
```
If you dont want to want to make use of virtual environment you can skip 
and jump straight to `step 3`
2.  Creating a  virtual environment 
```bash
$ pip install virtualenv
$ virtualenv -p /usr/bin/python2.7 django_webs # the python can point to any version of your python 
$ source django_webs/bin/activate # to make our virtual environment active so we dont corrupt our main python directory
```
3.  Navigating into the directory so we install our django framework
```bash
$ cd myfirstdjangoproject
$ pip install django 
$ django-admin startproject firstapp

```
Our project structure should look like this now

![project structure](/assets/images/structure1.png, "Project file")

## What does this files means?

- manage.py [basically the power engine room for all django commands, from database maintenance, to administrative task]
- firstapp/settings.py this contain all our project configurations, like database to use, custom app to include, templating system
- firstapp/urls.py
- firstapp/wsgi.py [our application server to power our simple django application]

## Creating a simple store app app

```bash
$ django-admin startapp store 
```

Next inside our INSTALLED_APP variable located at
the `settings.py` file  we put the name of our apps at the bottom of the list

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

## View
Let start with a simple view that show Welcome to django stored `views.py`

```python 
from django.shortcuts import render
def landing_page(request):
	return render(request, template_name="store/index.html", context={})
```


Creating a url to point to store landing page when your user's hit that 
url

> Create a file called `urls.py` inside your store app folder

Then we want to say when the user visit our site by going to `127.0.0.1:8000/store'
tell our view `landing_page` to handle that request and do some stuff with it.

## URL 
```python
from django.conf.urls import url
from .views import landing_page
urlpatterns = [
	url(r'^$', view=landing_page, name="landing-page")
]
```

Screen shoot of result when you visit the url