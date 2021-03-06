---
layout: blogpost
categories: Opinion
---

# About Infinity

I'm not saying that it is easy to define <a href="http://en.wikipedia.org/wiki/Infinity">infinity</a>. But if you are using an API - for instance in an embedded device - you might want to consider if your own definition of infinity is the same as the definition of the API.
<h2>A real life example</h2>
Your API defines <em>infinity</em> as <code>int32.Maxvalue</code> in milliseconds. Before we use this somewhere we expect it to run for years let's do a simple calculation:

<code>int32.Maxvalue</code> is <a href="http://msdn.microsoft.com/en-us/library/system.int32.maxvalue.aspx">equal to 2,147,483,647 </a>. So that means that the API <em>infinity</em> is: 2,147,483,647 ms / (1000 ms/s * 60 s/min * 60 min/h * 24 h/day) =~ <strong>24 days</strong>. Well depending on you use case that may be a very short infinity.