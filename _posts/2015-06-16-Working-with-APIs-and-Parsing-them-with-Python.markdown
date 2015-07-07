---
layout: post
author: Jim Tunnessen
title:  "Requesting and Parsing APIs with Python"
date:   2015-06-16 18:32:00
categories: Programming, Python
permalink: working_with_apis_with_python
tags: API Python Programming JSON 
published: true
---
<br>
This walk-thru uses the Python Requests and Python JSON libraries and is demonstrated in the Python Interpreter.

Import the requests library in order to work with HTTP
{% highlight ruby %}
import requests
{% endhighlight %}

Import the JSON library in order to parse the JSON
{% highlight ruby %}
import json
{% endhighlight %}

Send a GET requests to the API you want to use
{% highlight ruby %}
$ r = requests.get('https://api.github.com/events')
{% endhighlight %}

Check the status code of your API connection
{% highlight ruby %}
$ r.status_code
{% endhighlight %}

View the JSON payload
{% highlight ruby %}
$ r.json()
{% endhighlight %}

Clean up the JSON to PARSE
Variable holding the entire JSON receipt
{% highlight ruby %}
$ json_to_parse = json.loads(json.dumps(r.json()))
{% endhighlight %}

Assigned a JSON Record to a variable (picked #3)
{% highlight ruby %}
$ y = json_to_parse[3]
{% endhighlight %}

View your asignment
{% highlight ruby %}
$ y
{% endhighlight %}

To prettify JSON with Python
{% highlight ruby %}
$ print json.dumps(y, sort_keys=True, indent=4)
{% endhighlight %}

Parse the JSON
{% highlight ruby %}
$ print(json_to_parse['actor']['login'])
{% endhighlight %}
<br>

###References:
[Python Document Library: JSON](https://docs.python.org/2/library/json.html "Python JSON Documents")

[Quickstart Requests](http://docs.python-requests.org/en/latest/user/quickstart/ "Quickstart for Python Requests")

[Python Guide: JSON](http://docs.python-guide.org/en/latest/scenarios/json/ "Python Guide: JSON")

[Python Documents: Data Structures - Dictionaries](https://docs.python.org/3.2/tutorial/datastructures.html#dictionaries "Python Dictionaries")