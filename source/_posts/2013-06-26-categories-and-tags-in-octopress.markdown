---
layout: post
title: "Categories and Tags in Octopress"
date: 2013-06-26 12:39
comments: true
categories: blog
tags: octopress
---
In order to add Categories and Tags pages, create those:
    rake new_page[blog/categories]
    rake new_page[blog/tags]

And insert the following content:
{% codeblock blog/categories %}
{% raw %}
<ul>
{% for item in site.categories %}
    <li><a href="/blog/categories/{{ item[0] }}/">{{ item[0] | capitalize }}</a> [ {{ item[1].size }} ]</li>
{% endfor %}
</ul>
{% endraw %}
{% endcodeblock %}

{%codeblock plain blog/tags %}
{% raw %}
<ul>
{% for item in site.tags %}
    <li><a href="/blog/tags/{{ item[0] }}/">{{ item[0] | capitalize }}</a> [ {{ item[1].size }} ]</li>
{% endfor %}
</ul>
{% endraw %}
{% endcodeblock %}

Finally add them to the navigation bar:
{% codeblock plain source/_includes/custom/navigation.html %}
{% raw %}
  <li><a href="{{ root_url }}/blog/categories">Categories</a></li>
  <li><a href="{{ root_url }}/blog/tags">Tags</a></li>
{% endraw %}
{% endcodeblock %}

