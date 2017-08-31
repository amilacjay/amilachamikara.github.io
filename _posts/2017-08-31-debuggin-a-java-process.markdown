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

Process process = Runtime.getRuntime().exec( &quot;java com.test.debugging.Test&quot; );

{% endhighlight %}

Check the [JDWP Documentation][jdwp-docs] for more information. If you have questions, you can inbox me.

[jdwp-docs]: https://docs.oracle.com/javase/8/docs/technotes/guides/troubleshoot/introclientissues005.html
