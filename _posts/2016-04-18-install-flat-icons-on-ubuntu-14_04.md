---
layout: post
title: install flat icons on ubuntu 14.04
categories:
- blog
---

I personalized my Ubuntu instance with some flat icons.

I began by installing the unity-tweak-tool:
`sudo apt-get install unity-tweak-tool`

I then added the repository and installed the Flatabulous icons:
{% highlight ruby %}
sudo add-apt-repository ppa:noobslab/icons
sudo apt-get update
sudo apt-get install ultra-flat-icons ultra-flat-icons-green ultra-flat-icons-orange
{% endhighlight %}

Thanks, [anmoljagetia](https://github.com/anmoljagetia/Flatabulous).

##Source(s)
* [anmoljagetia](https://github.com/anmoljagetia/Flatabulous)
* [Ubuntu Handbook](http://ubuntuhandbook.org/index.php/2015/11/flatabulous-flat-theme-ubuntu/)
