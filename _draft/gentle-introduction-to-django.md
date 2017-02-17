---
layout: post
title: Gentle introduction to Django Web Framework
comments: true
share: true
date:   2016-11-20
categories: python django web
---


Django is a very high scalable web Framework for dead line.

Having started learning django some years back, have found it to be the most complete web framework. (my personal opinion)

Django web principle
The MVT (Model View Template)


First am using an ubuntu box machine

So let create a virtual environment. You can check my previous tutorials on how to create virtual environment

# Creating a django project virtual environment

Creating a directory where our django project will be stored
> mkdir myfirstdjangoproject
Navigating into the directory so we perform all other task there
> cd myfirstdjangoproject
> mkvirtualenv django_webs
> pip install django 
> django-admin startproject firstapp

Our project structure
# here should contain a screenshot of the sample project structure

# let go over all the details of what each of those file means

manage.py [basically the power engine room for all django commands, from database maintance, to administrative task]
firstapp/settings.py this contain all our project configurations, like database to use, custom app to include, templating system
firstapp/urls.py
firstapp/wsgi.py [our application server to power our simple django application]

