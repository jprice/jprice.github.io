---
layout: post
title: The following packages have been kept back
categories: [debian, linux]
modified: 2015-01-09 21:43:29
tags: [debian, linux, apt-get, update, dist-upgrade]
published: True

---

I've had it happen to me, and I'm sure you have too. It's a simple fix in most cases.

{% highlight bash %}
Building Dependency Tree... Done
The following packages have been kept back:
  some-super-duper-util
0 upgraded, 0 newly installed, 0 to remove and 1 not upgraded.
{% endhighlight %}

Yep, our some-super-duper-util package won't upgrade. So how do I fix this? Just a simple dist-upgrade should fix it. 

{% highlight bash %}
sudo apt-get dist-upgrade
Building Dependency Tree... Done
Calculating Upgrade... Done
The following NEW packages will be installed:
  some-super-duper-util-dep
The following packages will be upgraded:
  some-super-duper-util
1 upgraded, 1 newly installed, 0 to remove and 0 not upgraded.
Need to get 12KB of archives.
After unpacking 120KB of additional disk space will be used.
Do you want to continue? [Y/n]
{% endhighlight %}

That should be all it takes!