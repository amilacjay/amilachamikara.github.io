---
layout: post
title:  "Debugging a Java Process"
date:   2017-08-31 00:33:25 +0530
categories: Java update
---
Problem

*If there is a java process that is started within our main java application, it is not possible to
debug in normal way.*

{% highlight java %}

Runtime.getRuntime().exec("java com.test.debugging.Test");

{% endhighlight %}

Solution

Steps of JDWP using command line,
1. Start a java process in debug mode (to debug Test.java class)

On Windows:
{% highlight java %}
java -Xdebug -Xrunjdwp:transport=dt_shmem,address=debug,server=y,suspend=y Test
{% endhighlight %}

On Oracle Solaris and Linux operating systems:
{% highlight java %}
java -Xdebug -Xrunjdwp:transport=dt_socket,address=8888,server=y,suspend=y Test
{% endhighlight %}


2. Connect to the debug server using another command line

On Windows:
{% highlight java %}
jdb -attach "debug"
{% endhighlight %}

On Oracle Solaris and Linux operating systems:
{% highlight java %}
jdb -attach 8888
{% endhighlight %}

Using IntelliJ IDEA

({{ site.url }}/_posts/assets/image1.png)

Check the [JDWP Documentation][jdwp-docs] for more information. If you have questions, you can inbox me.

[jdwp-docs]: https://docs.oracle.com/javase/8/docs/technotes/guides/troubleshoot/introclientissues005.html
