---
layout: post
ref: translation-mistakes-of-trailhead
title: "Trailhead 翻訳の戸惑"
description: "Trailheadで勉強する時、日本で仕事している私は大体日本語を選択してやっていました。しかし、日本語翻訳に戸惑うことはよくあります。ここでは、その中の一つの例を説明します。"
date: 2020-08-15 20:41:00 +0900
tags: [salesforce, trailhead]
---

### 認証とは？

{% include image.html path="documentation/Authorization-ja" path-detail="documentation/Authorization-ja" alt="認証とは" %}

例えば上記「[データ漏洩の防止](https://trailhead.salesforce.com/ja/content/learn/modules/data-leak-prevention/learn-how-authorization-works-in-force-com-apps)」という、セキュリティについてプログラミングにデータのアクセス制御を適用する対策を紹介するモジュールからいいます。

> 認証とは？
> 
> 一般的にオンラインデータへのアクセスは**識別**、**認証**、および**承認**されたユーザのみに制限されます。このモジュールでは、どのリソースに誰がアクセスできるのかを判別する**認証**に焦点を絞ります。

認証というキーワードをいうと、どんなものが視野に入り込むでしょうか？

２要素認証？OAuth 2.0? とかでしょうか？私の場合、大体はユーザのログインや、セッションを認証する仕組みを思い出します。

しかし、このモジュールではそういう話をされているでしょうか？

**違います！**続きをよんでみると、わかると思います。

### 完全に別の話をしている

{% include image.html path="documentation/authorizaition-defination" path-detail="documentation/authorizaition-defination" alt="Salesforce での認証: 入門" %}

CRUDの設定、項目レベルセキュリティ、共有ルール、これら全部アクセス制御の話でしょう。ユーザ認証に全く関係ないじゃないか。

なので、このモジュールをやっていた時、すごく戸惑ったんです：いったいおれ何を読んでいるの？

この時は、やはり英語のオリジナルバージョンを切り出して確認するんです。

### オリジナル・バージョン

{% include image.html path="documentation/Authorization-en" path-detail="documentation/Authorization-en" alt="認証とは" %}

> What Is Authorization?
> 
> Access to online  data is generally  restricted to only those who are **identified**, **authenticated**,  and  **authorized**. In this module,  we focus on **authorization**,  which determines  who is able to access which resources.

かなり近似な用語が使われているので、ここでは簡単な表を作って、その意味を整理してみます。


英語 | 日本語意味
--- | ------
identify  | 人の身元を識別
authenticate  | 本物であることを証明する
authorize  | 権限を与える, ...に許可する

<br/>

### 認証ではなく、データへの権限

ちゃんと日本語の文章と比べてみたら、

「なるほど！」

ここで説明したい「認証」の概念は「Authorization」、たしかにユーザにデータへのアクセス権限を与えることを話していることがわかりますよね。

### Trailheadの言語の問題

Trailhead は Salesforce 社が作った開発者、ユーザ向け勉強するための素晴らしいサイトだと思います。本当に顧客を中心にする態度がこのサイトで多少わかります。すでに６種類の言語が対応されていることもすこいと思います。

たっだ、そのどんどん増えてくるモジュール数に対して、すべての言語の翻訳の品質を保つのはかなり難関ですよね。

モジュールの文書に対して、コメント機能やサポートに指摘を提出できる機能があったらいいなと思います。