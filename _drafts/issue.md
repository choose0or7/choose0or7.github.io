---
layout: post
title: "issue"
description: ""
tags: [Salesforce, security]
---

<!--
  If this is a security related bug, please email the maintainer of
  this repository (found via `security`) and let them know in private...
  all security issues are handled promptly, and quickly, however an
  early release could severely impact people.
-->

- [x] I tried updating to the latest version
- [x] I am on macOS 10.15

## Description

<!--
  Replace this with a description of your issue.  Try to be as
  detailed as you can, because the lack of a detailed description
  will not help us reproduce it, and if we cannot reproduce and
  you do not answer, your ticket could be closed.
-->
Resources don't generate if they are not mentioned in the final html.
On the other hand, they will be generated even if they are just in the comment. (which is also very annoying, I have to clear those comments when the files are deleted)

## Steps
Example like this:
```html
    {% if site.blog_theme == "light" %}
      <link rel="icon" type="image/x-icon" href="{% asset favicon-light.ico @path %}">
      <link rel="apple-touch-icon" href="{% asset apple-touch-icon-light.png @path %}">
    {% else %}
      <link rel="icon" type="image/x-icon" href="{% asset favicon-dark.ico @path %}">
      <link rel="apple-touch-icon" href="{% asset apple-touch-icon-dark.png @path %}">
    {% endif %}
```
When I set the `site.blog_theme ` to light, `favicon-dark.ico` and `apple-touch-icon-dark.png` will not be generated.

One more example is if I write the source of images in SCSS rather than HTML, they will not be generated either.

In HTML
```html
<a href="{{ '/' | relative_url }}" class="header-logo" title="{{ site.name }}">
```
In SCSS
```scss
.header-logo {
  background-image: asset_url('navlogo-light.png');    
  background-repeat:  no-repeat;
}
```


## Output

```sh
# Doing stuff.
# Doing more stuff.
# Oh no error.
```

## Expected

<!--
  Replace this with what you expected to happen.
  Sometimes there are bugs, sometimes it's just a feature,
  but it's always nice to know what you wanted.
-->
