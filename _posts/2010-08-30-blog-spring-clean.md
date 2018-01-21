---
layout: post
title: Blog spring clean
date: 2010-08-30 18:08 +0000
description: Enabling code highlighting using Google Blogger
---

Admittedly this is late for a spring clean, but Blogger has introduced a
host of updates since I last looked. One being this nifty new template.  
  
Also, something I've wanted to try out is a decent syntax highlighter
and this one looks good. See
<http://alexgorbatchev.com/SyntaxHighlighter/>. The instructions I
followed for Blogger can be
found [here](http://www.cyberack.com/2007/07/adding-syntax-highlighter-to-blogger.html).  
  
So now I can easily publish code like this:  

{% highlight html %}
<html>
  <head>
    <title>Tutorial: HelloWorld</title>
  </head>
  <body>
    <h1>HelloWorld Tutorial</h1>
  </body>
</html>
{% endhighlight %}  

(You have escape angular brackets)  
  
{% highlight python %}
print "Hello, World!"
{% endhighlight %} 

{% highlight java %}
// Outputs "Hello, world!" and then exits
public class HelloWorld {
   public static void main(String[] args) {
       System.out.println("Hello world!");
   }
}
{% endhighlight %} 

  
Don't use the Blogger WYSIWYG editor for this, switch to HTML else it
will get very confused. I have used the pre method over script. I
imagine if you switch templates this may break, but a quick copy and
paste should bring the functionality back.  
  
Fingers crossed it comes out ok through RSS readers as well!