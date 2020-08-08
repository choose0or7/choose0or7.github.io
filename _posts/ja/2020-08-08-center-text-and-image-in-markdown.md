---
layout: post
title: "Markdown で文字と画像を中央寄せ"
description: "githubpages を利用しているなら、これは一番簡単な書き方！"
tags: [markdown, jekyll]
---

下記文書を Markdown で文書を書く場合、画像を中央に寄せたいなと思ったら、どうすればいいんですか？

{% highlight markdown %}
こんにちは！
        ＜画像＞
        画像タイトル
終わり。
{% endhighlight %}

markdown で普通に書けば、下記のようになります：
{% highlight markdown %}
![my image](/img/myImage.jpg)
画像タイトル
{% endhighlight %}

![my image]({% asset 'documentation/logo-gold@small.png' @path %})
画像タイトル


## まずは結論を!

Markdown で文書書くとき、あまり HTML タグをいっぱい書きたくないし、なるべく Markdown 文法で統一したいので、個人的に一番いい書き方は下記です：

中央に寄せたい部分の直前に`{: align="center"}`の１行をおけばいいです。

それで終わりです。例は下記です：

{% highlight markdown %}
こんにちは！

{: align="center"}
![my image](/img/myImage.jpg)
画像タイトル

終わり。
{% endhighlight %}

{: align="center"}
![my image]({% asset 'documentation/logo-gold@small.png' @path %})
画像タイトル

備考：**Kramdown を使うのは前提です**。Kramdown は Jekyll のデフォルト Markdown レンダラーです。Jekyll を使ってサイトを構築している方は大丈夫です。もちろん Github page もOKです。標準な Markdown だと上記書き方は効かないです。

<br />
<br />
<br />

## 書き方は色々

### HTML タグ

ぐぐッてみたら、オンラインで流れている書き方は大体こんな感じです：

#### テキスト
{% highlight markdown %}
<div style="text-align: center;">
    センタリングしたい文章
</div>
{% endhighlight %}

<div style="text-align: center;">
    センタリングしたい文章
</div>
<br />
#### 画像
{% highlight markdown %}
<div align="center">
    <img src="画像のPATH" alt="属性">
</div>
{% endhighlight %}

<div align="center">
    <img src="{% asset 'documentation/logo-gold@small.png' @path %}" alt="属性">
</div>

もともと Markdown では HTML を書けるので、どちらでも問題なく中央寄せはできます。

##### 注意点：

テキストの場合の`text-align`と画像の場合の`align`が違うので、気をつけましょう。


<br />
<br />
<br />


### ほかの書き方

#### 1. `<center>`を使う

{% highlight markdown %}
<center><img src="画像のPATH" alt="属性"></center>
<center>画像タイトル</center>
{% endhighlight %}

<center><img src="{% asset 'documentation/logo-gold@small.png' @path %}" alt="属性" title="タイトル"></center>
<center>画像タイトル</center>

<br />
#### 2. もしCSSを定義できれば（これもすごくいい！）

{% highlight markdown %}
![my image](/img/myImage.jpg#center)
{% endhighlight %}

CSSに下記スクリプトを追加
{% highlight CSS %}
img[src*='#center'] { 
    display: block;
    margin: auto;
}
{% endhighlight %}

![my image]({% asset 'documentation/logo-gold@small.png' @path %}#center)


<br />

**参考ページ**：

[Using Markdown, how do i center an image and its caption](
https://stackoverflow.com/questions/3912694/using-markdown-how-do-i-center-an-image-and-its-caption) - Stackflow.

