---
layout: default
title: OSX - permissão de aplicações sem permissões de programadores
date: 2019-11-04
author: Paulo
categories: OSX
---

# OSX - permissão de aplicações sem permissões de programadores

Para que se possa executar a aplicação a instalar, mas que o programador não é reconhecido pela Apple, podemos executar o comando seguinte na imagem descarregada, antes de a montar: 

{% highlight bash %}
xattr -d com.apple.quarantine ~/Downloads/<instalador_aplicacao>.dmg 
{% endhighlight %}

ou após a instalação da mesma, executar o seguinte:

{% highlight bash %}
xattr -dr com.apple.quarantine /Applications/<aplicacao_instalada>.app 
{% endhighlight %}


