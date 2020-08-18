---
layout: post
title: Workaround para aparecer icon do Dropbox no Xubuntu 16.04
date: 2016-04-20
categories: dropbox
---
Sendo utilizador de xubuntu, normalmente nas versões LTS e nomeadamente da versão 16.04 e também utilizador do Dropbox para alguns tipos de conteudos, deparei-me com o problema do icon de notificação do Dropbox, não aparecer correctamente.

Após alguma pesquisa encontrei no AskUbuntu este post [http://askubuntu.com] (http:askubuntu.com).

Resumindo o que resultou no meu caso foi copiar o atalho dropbox.desktop existente na pasta ~/.config/autostart/, por exemplo para dropbox_hack.desktop e efectuar as seguintes alterações como sugerido por um dos utilizadores que comentou no post que referi anteriormente:

Criar uma directoria na pasta do utilizador com  o nome "bin" :

{% highlight bash %}
cd ~
mkdir bin
{% endhighlight %}

criar um script com o nome dropbox_hack.sh com o seguinte conteudo:

{% highlight bash %}
#!/bin/bash

# Pára alguma instância do dropbox que esteja a correr
dropbox stop

# inicia novamente o Dropbox
dbus-launch dropbox start -i
{% endhighlight %}

e de seguida definimos o script como executável

{% highlight bash %}
chmod +x ~/bin/dropbox_hack.sh
{% endhighlight %}

Editamos o atalho da aplicação do dropbox criado de forma a que a linha Exec= contenha o caminho para o ficheiro criado anteriormente, no exemplo seria /home/<nomeutilizador>/bin/dropbox_hack.sh

O atalho original do dropbox deve ser removido do arranque, por exemplo, eliminando o ficheiro original em "~/.config/autostart/" com o nome "dropbox.desktop"
