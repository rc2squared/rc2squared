---
layout: post
title: generating ssh keys
categories:
- blog
---

Here's quick guide for generating ssh keys and then uploading the public key to
a server. I find that these types of guides help when you can't remember something
specific, even if you've done it a hundred times.

Check if you have any ssh keys:
`ls -al ~/.ssh`

Generate ssh keys, and  if you want, you can insert a name or alias, but it should go in the quotes:
`ssh-keygen -b 4096 -t rsa -f ~/.ssh/id_rsa -C “INSERT-NAME-OR-ALIAS”`.
(Note: Be sure not to simply copy and paste, but rather put your name or alias in quotes.)

Enter your passphrase.

Add the new sshy key to the ssh-agent:
{% highlight ruby %}
eval “$(ssh-agent -s)”
ssh-add ~/.ssh/id_rsa
{% endhighlight %}

Share your public key with the server. You can use various methods. For example:

* You could view your public key by going to the /.ssh directory and entering `cat id_rsa.pub`.
You can then copy and paste your key into the appropriate directory, which is generally /.ssh/authorized_keys.

* You could copy and share it with one command: `cat ~/.ssh/id_rsa.pub | ssh USER@IPADDRESS “mkdir -p ~/.ssh && cat >> ~/.ssh/authorized_keys”`.

* You could copy and share it with another command: `ssh-copy-id USER@IPADDRESS`
(Note: Again, be sure not to simply copy and paste comments, but rather enter your own username and IP address.)

## Source(s)
* [Magnus Deininger](https://ef.gy/hardening-ssh)
* [Digital Ocean Community](https://www.digitalocean.com/community/tutorials/how-to-set-up-ssh-keys--2)
* [Coolest Guides](https://coolestguidesontheplanet.com/make-passwordless-ssh-connection-osx-10-9-mavericks-linux/)
