---
layout: default
title: GDG DevFest now includes Albuquerque
date: 2013-11-19 05:00 -0700
tags: google
---

![Google Developer Group (GDG) Albuquerque]({{ "/assets/gdg_abq.png" | absolute_url }})

Albuquerque just had it's first [GDG DevFest](http://www.gdgabq.com/)
(translation - Google Developer Group meetup). Where a selection of
Google employees and enthusiasts met to share their experiences and
insight to a few Google products (let's be honest there are quite a few
now). Google Glass was out in force, six pairs, which is presumed to be
the greatest concentration of them in New Mexico! I attended the
following talks:  
  
### Google Drive Realtime API

The challenge for Drive is collaboration. Everything is stored as
structured data - JSON. Due to the structured nature mutations can be
created, which reflect a specific change, but not the actual data
itself. Mutations are kept forever until the file is deleted. In fact
the mutations make up the file, a snapshot describes the summary of
changes to give the current file, save having to process all the
mutations, which could be numerous. Mutations are saved on the server
and the client (your browser) otherwise collisions when collaborating
can easily occur, having the transformation manager on the client allows
the reconciling of the incoming mutations and your local mutations,
which are then pushed back to the server to the other collaborators.
This technique is also how you can work offline, as the mutations are
stored and reconciled later.  
  
### Welcome to Android

I have never done any Android programming, suffice to say it looks like
a regular Java project with a touch of HTML (e.g. storing multiple
resolutions of your images etc). Interestingly the IDE of choice,
Eclipse with a plug-in is shifting to Android Studio. This is based on
JetBrains IntelliJ - perhaps the gold standard of Java IDE (in cost as
well), but free for Android developers.  
  
### ChromeCast - In Love

The instant success of the ChromeCast (nothing to do with that free
Netflix subscription I'm sure) has a API available now. The ChromeCast
is a receiver which runs web pages and you build the sender in your app
(desktop, mobile, browser etc) to pair establish a connection with the
ChomeCast. It looks surprisingly simple (famous last words).  
  
### AngularJS - Life changing tech

Google's latest JavaScript library which is receiving much love both
within and outisde the company. While many Google products are built on
Closure, it seems new sites are being built with AngularJS. AngularJS
lets you extends the HTML vocabulary and is a powerful MVC aide.  
  
### HTML5 in the Movies

Since ABQ is now the center of the film universe directors look to local
talent to fill various facets, which now include computer props. We saw
numerous demonstrations of easy to use demos (single click for the
actors) that make it appear as they type emails, send and receives
replies all with a few random clicks. No surprise making the demos
foolproof and loop-able was highly desirable, as was avoiding Windows
for stability.  
  
### Startup Weekend Panel

For the final session we got a taste of what the the startup weekend
events are like. A surprising amount of these events are cropping up
around the state, not just in ABQ. We were given two disconnected words
and had 10 minutes to come up with a business and 1 minute pitch,
certainly a good ice breaker!  
  
### Summary

Overall it was an enjoyable day, my thanks to the GDG ABQ for taking the
time to organize it and the sponsors (who doesn't want to see a 3D
printer in action?) for making it possible. I think almost everyone left
with a prize as well, I won an O'Reilly book in the raffle (worth more
than the cost of the ticket). I was really impressed with the ChromeCast
API and think I have found my next Hack Day project for work.