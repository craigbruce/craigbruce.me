---
layout: post
title: Book chapter on the use of open source software in the pharmaceutical industry
date: 2013-05-05 06:28 +0000
tags: cheminformatics, django, python, red hat
---


![Open source software in life science research: Practical solutions to common challenges in the pharmaceutical industry and beyond]({{ "/assets/ospharmacover.jpg" | absolute_url }})

During my final year at AstraZeneca I was asked to contribute a chapter
to "Open source software in life science research: Practical solutions
to common challenges in the pharmaceutical industry and beyond". Given
this work would be very hard to publish in JCIM, JMC etc and I have
never written a book chapter before it was the perfect opportunity. The
chapter was entitled: Design Tracker: an easy to use and flexible
hypothesis tracking system to aid project team working. It was
coauthored by Martin Harrison, who wrote Design Tracker. The abstract
sums up best what it covers:

> Design Tracker is a hypothesis tracking system used across all sites
> and research areas in AstraZeneca by the global chemistry community.
> It is built on the LAMP (Linux, Apache, MySQL, PHP/ Python) software
> stack, which started as a single server and has now progressed to a
> six-server cluster running cutting-edge high availability software and
> hardware. This chapter describes how a local tool was developed into a
> global production system.

Design Tracker has been mentioned in a few external presentations before
but I believe this is the first firm details about it. We talk about its
use and how it came to be a global chemistry tool from a prototype at
one site. As the book topic suggests we also cover the open source
technologies we used to power it. While LAMP is not new, it is not
exactly mainstream in the corporate environment for many pharmaceutical
companies. We had to harden our setup to make it suitable for 24/7 use,
so in addition to the regulars on LAMP we added [Red Hat Cluster
Suite](http://www.redhat.com/products/enterprise-linux-add-ons/high-availability/),
[Continuent Tungsten](http://www.continuent.com/) and
[NGINX](http://nginx.com/). We also took the opportunity to move away
from apache/mod\_python to
apache/[mod\_wsgi](https://code.google.com/p/modwsgi/). The end result
was a service which is available 24/7 and future proofed compared to our
previous solution.  
  
The worlds most dynamic and frequently visited websites are powered by
similar technologies so they have clearly proven themselves to be suited
for the relatively modest needs of a single pharmaceutical company.  
  
The book is available on Amazon UK & US and probably your favourite book
reseller as well (ISBN: 978-1907568978). I hope you enjoy our chapter
and the many others interesting topics covered.