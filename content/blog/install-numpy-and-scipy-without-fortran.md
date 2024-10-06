---
title: "Install NumPy and SciPy without Fortran"
date: 2013-12-15T21:39:01-07:00
---

[NumPy](http://www.numpy.org/) and [SciPy](http://www.scipy.org/) are
two great Python packages for scientists, as is the popular
[Matplotlib](http://matplotlib.org/). However, installing NumPy and
SciPy is not for the faint hearted if you install your Python packages
via [pip](http://www.pip-installer.org/). Assuming you have fortran,
blas, lapack and atlas already installed it is actually quite a slow
installation, especially SciPy. NumPy took 46 seconds to install,
whereas SciPy took 6 mins and 50 seconds on my MacBook Pro. So what if
you install once and forget? Two problems with that. First I use 
``mktmpenv`` when debugging issues. Second I also use
[tox](http://tox.readthedocs.org/) to test against multiple version of
Python and/or Django. All of a sudden 6 build configurations is 42
minutes of SciPy compilation!  
  
Let's not forget Windows users, Fortran - I don't think so and they
should be able to enjoy pip and virtualenv as much as any Python
developer.  
  
The obvious solution is for SciPy to be packaged with
[wheel](http://wheel.readthedocs.org/), the new Python binary
distribution format. However, I appreciate that would be very hard for
the authors, but hopefully one day.  
  
In the meantime [Anaconda](https://store.continuum.io/cshop/anaconda/)
might be of interest. It is like apt-get/yum for scientific Python, but
a new feature has just been announced, you can pip install anaconda
itself then take advantage of the binary distributions it provides for
you.

So try this (assuming you have pip, virtualenv and virtualenvwrapper 
installed)  

{{< highlight bash >}}
$ mktmpenv
$ pip install conda
$ conda init
$ conda install scipy
{{< / highlight >}}
    
SciPy plus NumPy and numerous dependencies are installed in under a
minute! Obviously, you can not convert this to a requirements.txt per
se, but using [Fabric](http://fabfile.org/) you can make a task to
install conda and then the conda packages all with a one liner.