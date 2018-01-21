---
layout: default
title: Eclipse with C++/OEChem
date: 2009-06-01 14:30 +0000
tags: eclipse, openeye
---

![Eclipse CDT]({{ "/assets/cdt.png" | absolute_url }})

The final post in this series, allowing you to develop your OpenEye
applications using Eclipse.  
  
First off you will need to ensure the [CDT](http://www.eclipse.org/cdt)
plugin is installed, or download Eclipse for C++ developers.  
  
Now we are set to go. Create a new C++ Project (Executable &gt; Hello
World). Edit/Add C++ files to the source folder. Next we need to inform
the project about OpenEye.  
  

-   Open your project properties (Project &gt; Properties).
-   Pick C/C++ Build &gt; Settings
-   Edit [ All Configurations ] (by default Debug and Release)
-   Set include paths (``-I``) under GCC C++
    Compiler &gt; Directories &gt; Include paths
-   Add ``$OE_DIR/toolkits/include``
-   Set library paths (``-L``) under GCC C++
    Linker &gt; Libraries &gt; Library search path
-   Add ``$OE_DIR/toolkits/lib``
-   Set specific libraries (``-l``) under GCC C++
    Linker &gt; Libraries &gt; Libraries
-   Add ``oeplatform``, ``oesystem``, ``oechem``, ``m``, ``z``, ``pthread``
-   You can set further Makefile details from this panel
    (optimisation etc)

If you have multiple versions of the toolkit you can create a
configuration for each one.  
  
Between C++/Java/Python you should be able to code away happily within
Eclipse.