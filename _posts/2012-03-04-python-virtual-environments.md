---
layout: default
title: Python Virtual Environments
date: 2012-03-04 07:35 +0700
tags: python
---

![Python]({{ "/assets/python_logo.jpg" | absolute_url }})
  
Anyone who uses Python regularly will soon encounter the need to install
an extra package be it [MySQLdb](http://pypi.python.org/pypi/MySQL-python),
[numpy](http://pypi.python.org/pypi/numpy) or [Django](http://pypi.python.org/pypi/Django). Thanks to tools like ``pip`` and ``easy_install`` this is very trivial to 
do, as long as you have internet access from your command-line. Those of 
you behind corporate firewalls might want to try 
[cntlm](http://cntlm.sourceforge.net/) to help. Typically they will
install the package into your home directory for only you to use. If you
are root they will install into the system installation for all users to
use. In both scenarios it is hard to mix and match multiple versions of
packages. As a developer this becomes very important, I might want to
try the lastest version of a package, but for my production code I want
to remain on the stable release. The easiest way to manage this is using
virtual environments. [Virtualenv](http://www.virtualenv.org/) is a
python package that allows you to manage multiple python instances with
different combinations of packages. It is easy to mix python and package
versions for development and production code. Virtualenv is great and
has been extended with
[virtualenvwrappers](http://www.doughellmann.com/projects/virtualenvwrapper/),
which adds even more functionality.  
  
To get started run the following:  
  
{% highlight bash %}
$ easy_install virtualenv
$ easy_install virtualenvwrappers  
{% endhighlight %} 

Next you need to alter your environment slightly in ``~/.bashrc`` or equivalent add:  
  
{% highlight bash %}
export WORKON_HOME=$HOME/.virtualenvs
export PROJECT_HOME=$HOME/projects
export VIRTUALENVWRAPPER_VIRTUALENV=/usr/local/bin/virtualenv
source /usr/local/bin/virtualenvwrapper.sh
{% endhighlight %} 

Fire up a new terminal or run ``source ~/.bashrc`` and the new commands are
now available to you. Lets create our new virtual environment with 
``mkvirtualenv test``. This creates and loads the new virtual environment called
test. Your command prompt will indicate you are using test as well. Now
run easy_install to install your packages. You can see what packages
are available with ``lssitepackages``. To leave this environment run
``deactivate``. Create another environment and list your packages, there will be none.
Switch back to test with ``workon test``.  
  
You can tie this virtual environment to Eclipse by pointing at the
python for the test environment, which can be found at ``~/.virtualenvs/test/bin/python``.  
  
See all the commands available for virtualenvwrappers at <http://www.doughellmann.com/projects/virtualenvwrapper/>. 

Enjoy your new virtual python environments!  
  
*Image courtesy of <http://www.flickr.com/photos/ptshello/2312382347/>*