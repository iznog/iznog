---
layout: post
title: Obter mime type de ficheiro
date: 2021-11-21
author: Paulo
categories: linux
---

Já aconteceu um determinado ficheiro aparentar ser de um determinado formato mas a aplicação que usamos não o consegue manipular?

Isso pode acontecer por exemplo, quando a extensão do ficheiro é incorreta. Como poderemos saber qual o tipo de ficheiro que temos?

Para obter o mime type de um determinado ficheiro, de forma a perceber qual a aplicação que poderá usar para manipular o ficheiro, poderemos usar o comando **file** para atingir esse objetivo.

Assim poderemos usar o comando da seguinte forma:

{% highlight bash %}
file --mime-type nomedoficheiro.ext
{% endhighlight %}


Desta forma obtemos o mime type do ficheiro. Se pretendermos obter apenas o encoding do ficheiro, podermos usar --mime-encoding em vez de mime-type.
Podemos no entanto obter as duas informações se usarmos a opção -i :

{% highlight bash %}
file -i nomedoficheiro.ext
{% endhighlight %}
