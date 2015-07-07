---
layout: post
author: Jim Tunnessen
title:  "Installing couchDB on Ubuntu 14.04"
date:   2015-04-01 19:32:00
categories: Database Management, NoSQL Databases
permalink: install-couchDB-on-ubuntu
tags: couchDB, Databases, NoSQL, mongoDB, JSON
published: true
---

CouchDB is a NoSQL database that speaks JavaScript. You send the data that you store in couchDB in JavaScript Object Notation (JSON). A database in CouchDB is a collection of documents that live at a URL path one level down from the root. As you can imagine, this makes it a great solution for setting up RESTful APIs.

### This is an easy install: ###

{% highlight ruby %}
cd /usr/local/src
{% endhighlight %}

{% highlight ruby %}
sudo apt-get install software-properties-common -y
{% endhighlight %}

# add the ppa:
{% highlight ruby %}
sudo add-apt-repository ppa:couchdb/stable -y
{% endhighlight %}

# update cached list of packages
{% highlight ruby %}
sudo apt-get update -y
{% endhighlight %}

# remove any existing couchdb binaries
{% highlight ruby %}
sudo apt-get remove couchdb couchdb-bin couchdb-common -yf
{% endhighlight %}

# Add couchDB
{% highlight ruby %}
sudo apt-get install -V couchdb
{% endhighlight %}

# Start it from the command line
{% highlight ruby %}
sudo start couchdb
{% endhighlight %}

# Verify that it is running, connect to port 5984
{% highlight ruby %}
curl localhost:5984
{% endhighlight %}

This command will generate a response like this:
{"couchdb":"Welcome","uuid":"f3e729e12d8fe2183fd090854da00cbb",
"version":"1.6.1","vendor":{"version":"14.04","name":"Ubuntu"}}

# To add a user to the database...
{% highlight ruby %}
adduser --disabled-login --disabled-password --no-create-home couched
{% endhighlight %}

# To give the user permissions...
{% highlight ruby %}
chown -R couchdb:couchdb /usr/local/var/log/couchdb /usr/local/var/lib/couchdb 
/usr/local/var/run/couchdb
{% endhighlight %}

# To stop couchDB
{% highlight ruby %}
sudo stop couchdb
{% endhighlight %}

[Link to Apache CouchDB Ubuntu packages](https://launchpad.net/~couchdb/+archive/ubuntu/stable)