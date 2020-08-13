---
layout: post
lang: zh
ref: how-to-make-jekyll-multilingual
title: 用jekyll实现多语言版本的网站
date: 2020-08-13 23:41:00 +0900
tags: [jekyll]
---

[Making Jekyll multilingual](https://www.sylvaindurand.org/making-jekyll-multilingual/)

[How to make Jekyll multilingual](https://medium.com/@desfocado/how-to-make-jekyll-multilingual-c13e74c18f1c)

{% highlight markdown %}
---
title: Hello world!
lang: en
ref: hello
---
{% endhighlight %}

{% highlight markdown %}
---
title: 你好，世界!
lang: zh
ref: hello
---
{% endhighlight %}

{% highlight markdown %}
---
title: こんにちは，世界!
lang: ja
ref: hello
---
{% endhighlight %}