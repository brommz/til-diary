---
layout: post
title: "How to get value by reference in Dictionary"
date: 2022-02-18 01:00:00 +0100
description: Hi! # Add post description (optional)
---

It's pretty simple. Try it out.

{% highlight csharp %}
ref var valueRef = ref CollectionsMarshal.GetValueRefOrAddDefault(dict, "key", out _);
{% endhighlight %}

[https://github.com/brommz/poc-tests/blob/main/Program.cs](https://github.com/brommz/poc-tests/blob/main/Program.cs)
