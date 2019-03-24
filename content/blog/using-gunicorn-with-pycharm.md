---
title: "Using Gunicorn with PyCharm"
date: 2012-07-18T05:28:00-07:00
---

![The Green Unicorn](/img/large_gunicorn.png)
 
When you develop projects with Django it comes with a handy ``runserver``
which is a lightweight webserver bundled with Django, see more
[here](https://docs.djangoproject.com/en/1.4/ref/django-admin/#runserver-port-or-address-port).
It goes without saying you would never want to deploy any production
code with this as it doesn't scale nor is it particularly secure. It
does not get much attention from the Django developers, lets face it
there are better things to work on. So a few alternatives have popped
up. The one which caught my eye is [gunicorn](http://gunicorn.org/). Now
gunicorn can be used on preprod or production sites as well, but I stick
to development here (what I use for production will feature in another
post).  
  
Gunicorn is actually a fork of [Unicorn](http://unicorn.bogomips.org/)
which is designed for use with Ruby. It is a WSGI webserver, WSGI is
*the* way to run webservers. It also features integration with Django so
can be a drop in replacement for ``runserver``.
Installation is a breeze, ``pip install gunicorn`` and add ``gunicorn``
to your ``INSTALLED_APPS`` in your ``settings.py`` - Easy.

From the command-line you might do ``./manage.py runserver 192.168.1.1:9000``
with the Django runserver. To use Gunicorn simply run ``./manage.py run_gunicorn 192.168.1.1:9000``. Again straight forward. Within PyCharm
you need edit your django run configuration and tick the "run custom
command" box. Add ``run_gunicorn`` and run that. ``run_gunicorn`` is a helper
function that gunicorn adds to ``manage.py``. Unfortunately, I found not 
all gunicorn options can be specified via this, which can be annoying.  
To access all gunicorn options you need to run gunicorn direct and feed 
it a wsgi application, handily django is wsgi ready and from 1.4 includes 
a wsgi file when you create a new project (look for ``wsgi.py`` in your 
project directory). When using gunicorn direct you do not need to list gunicorn in your ``INSTALLED_APPS``. From your virtualenv run ``gunicorn -b 192.168.1.1:9000 myproject.wsgi:application``, where myproject is your Django project
name. You can drop in any gunicorn options you like as well. As for
running in PyCharm you need to create a Python run configuration, not
Django, and provide the following information:  
  
1.  Script: ``/Users/craig/.virtualenvs/blogenv/bin/gunicorn`` (your virtualenv of choice)
2.  Script parameters: ``-b 192.168.1.1:9000 myproject.wsgi:application``
3.  Working directory: ``/Users/craig/PycharmProjects/MyDjangoApp``

There is another reason to use gunicorn directly - you can use it with
[supervisor](http://supervisord.org/).

You may come across the ``gunicorn_django`` application
as well. That is fine to use if you are not on Django 1.4, otherwise use
the gunicorn application direct, as shown above.  
  
There is also [devserver](https://github.com/dcramer/django-devserver/)
from David Cramer. I've not used it personally but the other projects
that David works on are top rate, so I imagine this is too.