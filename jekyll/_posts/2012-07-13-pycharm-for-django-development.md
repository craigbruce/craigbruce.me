---
layout: post
title: PyCharm for Django development
date: 2012-07-13 04:55 -0700
tags: django, pycharm, python
---


![PyCharm]({{ "/assets/pycharm-logo.png" | absolute_url }})


I have been dabbling with Django for a few years now. Previously, I
always used Eclipse for this. Eclipse by itself doesn't support Python
or Django but add [PyDev](http://pydev.org/) or [Aptana
Studio](http://www.aptana.com/products/studio3) and it merrily
understands what is going on. This was great when I worked on multiple
projects in multiple languages. I now find myself working solely in a
Python/Django environment. PyCharm was getting rave reviews from my
former work colleagues, but I did so little Django it didn't seem worth
making the transition. However, with a new role I thought now was the
time and I haven't looked back. If you have ever used IntelliJ IDEA for
Java you'll be familiar with PyCharm as it is built upon the same
framework. Being written in Java also means you are able to code on your
Mac, Linux and Windows devices.  
  
For once PyCharm is fully aware of Django, not just syntax highlighting
(which was also hit and miss especially in templates mixing
HTML/CSS/Django template syntax in Eclipse).  Truth be told I have
barely touched the surface of features that PyCharm packs in.
See <http://www.jetbrains.com/pycharm/features> for a full
run down. Each release, of which updates are frequent, either refine or
add more features. In the 2.5 release virtualenv support was added, it
worked with manual intervention before, but now PyCharm automatically
detects them. In addition the support at JetBrains is
superb. Admittedly this is a commercial product, although they
license favorably for open source project - free.  
  
Just like IntelliJ various plugins are available. A whole host ship by
default, Git, CoffeeScript and JavaScript to name a few. More are
available online at the [plugin
repository](http://plugins.intellij.net/). The nginx support and NodeJS
plugins caught my eye.  

One of my favorite features is suport for running ``mange.py``
tasks from within the IDE, no need to setup the environment and run from
there, as shown (image courtesy of
[JetBrains](http://www.jetbrains.com/pycharm/features)).  
  
In fairness I did look at other Python IDEs with Django support, but
feel they fall into the same camp as Eclipse. The Django support is just
tacked on and is limited. With PyCharm you can see Django support was
core to the design and features implemented. I see the PyCharm team will
be at [DjangoCon US](http://www.djangocon.us/). This is great for two
reasons a) I can congratulate them on a great IDE and b) they will be
bring a new update
(<http://blog.jetbrains.com/pycharm/2012/06/pycharm-at-djangocons-around-the-world/>). 