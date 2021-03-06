---
layout: post
title: "Post with Octopress"
date: 2013-06-25 21:50
comments: true
categories: blog
tags: octopress
---
This is my first post with [Octopress](http://octopress.org) (a framework designed by [Brandon Mathis](http://brandonmathis.com) for [Jekyll](http://github.com/mojombo/jekyll), the blog aware static site generator powering [Github Pages](http://pages.github.com)). Now I'm gonna look around to find out how it work's and if I cand use it as a tool to store useful information an knowledge about hacking.

## Code Snippets
First of all: it is possible to [include code snippets](http://octopress.org/docs/blogging/code) in posts, in several ways, and for many languages. For example, a snippet for ruby, using backticks (used by github):
### Syntax
    ``` [language] [title] [url] [link text]
    code snippet
    ```

### Example
``` ruby Small ruby backtick example
def test()
  puts "color"
end
```

### Without Highlighting
For code, that does not need to be higlighted (e.g. for shell commands) one can use four spaces in front of the snippet:
    snippet

### Liquid

One can also use [liquid](https://github.com/Shopify/liquid/wiki/Liquid-for-Designers) for code snippets. This has the ability to disable tag processing in order to add liquid examples.
{% codeblock %}
{% raw %}
{% codeblock %}
{% raw %}
liquid-snippet
{ % endraw % }
{% endcodeblock %}
{% endraw %}
{% endcodeblock %}

## Links

Links can be added by using `[link text](url)`.

## Posting
Ok, now, in order to post Octopress provides a rake command:
    $ rake new_post["title"]

This create a new file with right naming convention and puts the filename, so it can be opened with a text editor. I only whished I could set an editor which is fired automatically with the new file...

One can also create pages:
    $ rake new_page["page title"]
    # creates /source/page-title/index.markdown

    $ rake new_page[xyz/page.html]
    # creates /source/xyz/page.html

But I am not shure, how those pages my be accessible. Possibly one is expected to add an link to them somewhere.

## Preview

Changes can be inspected before deplying with:
    $ rake generate
    $ rake watch    # Watches source/ and sass/ for changes and regenerates
    $ rake preview  # Watches, and mounts a webserver

Visit webserver at [http://localhost:4000](http://localhost:4000) to see changes.

## Deploying

If new posts are ready the blog can be newly generated and deployed:
    $ rake generate
    $ rake deploy

