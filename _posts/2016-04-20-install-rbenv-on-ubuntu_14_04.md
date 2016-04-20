---
layout: post
title: install rbenv on ubuntu 14.04
categories:
- blog
---

If you're in a hurry to install rbenv and ruby on Ubuntu 14.04:

{% highlight ruby%}
cd
git clone https://github.com/rbenv/rbenv.git ~/.rbenv
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(rbenv init -)"' >> ~/.bashrc
exec $SHELL

git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build
echo 'export PATH="$HOME/.rbenv/plugins/ruby-build/bin:$PATH"' >> ~/.bashrc
exec $SHELL

git clone https://github.com/rbenv/rbenv-gem-rehash.git ~/.rbenv/plugins/rbenv-gem-rehash

rbenv install 2.2.4
rbenv global 2.2.4
ruby -v
{% endhighlight %}

## Source(s)
* [rbenv](https://github.com/rbenv/rbenv)
* [ruby-lang](https://www.ruby-lang.org/en/downloads/)
* [go rails](https://gorails.com/deploy/ubuntu/14.04)
