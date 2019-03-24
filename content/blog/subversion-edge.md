---
title: "Subversion Edge"
date: 2010-09-23T18:32:43+00:00
---

![Subversion Edge](/img/csvn.png)

Subversion is an excellent version control system. It is mature enough
to have all sorts of integration - with Apache and Python amongst
others. This enables easy communication via the HTTP protocol and
language bindings, such as python to form web interfaces for
repositories.  
  
With subversion being a server-client model the version of the server is
the most important component as it determines what features you can
actually use. No good having a 1.6 client if the server is 1.2 as only
1.2 features are available. Depressingly this was the situation I was
in. Unsurprisingly, the good folk at CollabNet have added lots of useful
new features, which I need to use.  
  
Compiling subversion is actually dead easy (as I have
discussed [previously](http://cheminsilico.blogspot.com/2008/09/install-and-setup-subversion.html),
plus lots of binaries are available). So what is Subversion Edge?
Essentially a bundle of Apache, Subversion and ViewVC server in
a convenient tarball. Then throw in a bonus admin web interface as well.
Upgrading your server version becomes slightly more tricky when Apache
and Python are tied to it. No worries with Subversion Edge as it has a
built-in update mechanism. One of my pet peeves is multiple
usernames/passwords. Another freebie from Subversion Edge is LDAP
support so plug straight in your authentication system - nice. One
less component to ensure you compile against.  
  
I started using the beta over the summer and have had no problems. The
1.2.1 release is now happily serving many repositories for me.  If you
run a very large and complicated setup you may find Subversion Edge is
too restricted for you, but for a large number of users it will meet
your needs.  
  
If you maintain subversion repositories I strongly recommend you give
Subversion Edge a go today. Did I mention it was free as well?  
  
Useful links:   

-   [Project homepage](https://ctf.open.collab.net/sf/projects/svnedge)
-   [Screenshots](https://ctf.open.collab.net/sf/projects/svnedge)
-   [Mailing
    list](http://subversion.open.collab.net/ds/viewForumSummary.do?dsForumId=3)
-   [Documentation](http://help.collab.net/nav/12)