---
layout: page
title: 我的博客
tagline: Supporting tagline
---
{% include JB/setup %}
<h2>{{ page.title }}</h2>

<p>最新文章</p>

<ul>
	{% for post in site.posts %}
		<li>{{ post.date | date_to_string }} <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></li>
	{% endfor %}
</ul>