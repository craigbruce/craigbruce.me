---
title: "Homebrew"
date: 2012-05-01T06:44:00-07:00
---

[Homebrew](https://brew.sh), the OS X package manager, not the beverage, is the third
package manager I've used on OS X. I started in 2005 with
[Fink](http://www.finkproject.org/) and [MacPorts](http://www.macports.org/). 
MacPorts seemed to be more active, especially with the flurry of Leopard releases. 
Indeed it also has some advanced features including dependencies to let you install
[MAMP](http://en.wikipedia.org/wiki/MAMP) stacks. However, I find I prefer to have control
of my MAMP stack especially in my volatile development environments, upgrades can be 
particularly painful with MacPorts.  
  
Homebrew has quite a different approach. There is no need for sudo, all
binaries get symlinks in ``/usr/local``, but point to ``/usr/local/Cellar``
which controls the formula (aka package) version. The formula scripts
are ruby based, so adding your own is very easy.  
  
If you don't want to search forumlae via the command-line then head
to <http://braumeister.org/> (another GitHub project).  
  
Installation is pretty simple. If you are a developer, e.g. you have
Xcode installed it is probably a
[one-liner](https://github.com/mxcl/homebrew/wiki/installation).
Installation alongside MacPorts is not recommended, but to check you can
get everything you need from Homebrew it will probably not cause too
many problems.  
  
Now you have ``brew`` in your path lets explore some use cases:  

-   ``brew list`` - list installed formulae
-   ``brew search wget``  - search for formula called wget
-   ``brew info wget`` - get information about the formula wget
-   ``brew nstall wget`` - install wget
-   ``brew uninstall wget`` -u ninstall wget
-   ``brew update`` - update homebrew (effectively a git pull)
-   ``brew outdated`` - list formulae which are out of date
-   ``brew upgrade`` - upgrade all outdated formulae

For more features see the
[FAQ](https://github.com/mxcl/homebrew/wiki/FAQ) and
follow [@MacHomebrew](https://twitter.com/#!/MacHomebrew).  
  
Now I wonder if I can convince [puppet](http://puppetlabs.com/) to use
Homebrew over MacPorts...