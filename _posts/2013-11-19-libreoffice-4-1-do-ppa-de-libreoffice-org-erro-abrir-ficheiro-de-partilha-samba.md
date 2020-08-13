---
layout: post
title: Libreoffice 4.1 do PPA de libreoffice.org - erro abrir ficheiro de partilha samba
date: 2013-11-19
comments: false
---

Ao usar a versão 4.1.3.2 do Libreoffice do PPA do LibreOffice e ao abrir ficheiros localizados em partilha disponibilizada por um servidor SAMBA, poderá aparecer mensagem de erro de que o ficheiro que estamos a tentar aceder está corrompido.
Para podermos ultrapassar este problema, devemos editar o ficheiro de atalho da aplicação do LibreOffice que pretendemos usar e remover a linha ou comentar a linha "X-GIO-NoFuse=true" ou alterar para o valor "false".

[Link](https://www.libreoffice.org/bugzilla/show_bug.cgi?id=67527) para o bug report onde foi sugerida esta solução

EDITADO em 2014-03-02:

Tal como sugerido no comentário 47 do report do bug referenciado acima, podemos adaptar para usar neste caso:

Para alterar o valor para "false":
{% highlight ruby %}
sudo sed -i 's/X-GIO-NoFuse=true/X-GIO-NoFuse=false/' /usr/share/applications/libreoffice-*
{% endhighlight %}

Para comentar:
{% highlight ruby %}
sudo sed -i 's/X-GIO-NoFuse=true/#X-GIO-NoFuse=true/' /usr/share/applications/libreoffice-*
{% endhighlight %}

