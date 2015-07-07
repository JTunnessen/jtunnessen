---
layout: post
author: Jim Tunnessen
title:  "0MQ on Ubuntu 14.04"
date:   2015-03-29 11:25:00
categories: Node.js
permalink: zero_m_q_and_node
tags: IT, Node.js, software, messaging, npm, server-side, client-side, scripting
published: true
---

###Installing 0MQ (Zero MQ 3.2.3) Base Library on Ubuntu 14.04 

{% highlight ruby %}
cd ~
wget http://download.zeromq.org/zeromq-3.2.3.tar.gz
tar zxvf zeromq-3.2.3.tar.gz && cd zeromq-3.2.3
./configure
sudo make && make install


To verify the install
*** Run man zmq ***

{% endhighlight %}

###Installing the zmq Node Module

After installing the base library you can install the zmq Module with npm

{% highlight ruby %}
Set up what directory you want to base this out of and --
npm install zmq
{% endhighlight %}