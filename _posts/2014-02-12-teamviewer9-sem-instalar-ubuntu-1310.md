---
layout: default
title: Utilizacao do teamviewer 9 sem instalar
categories: ubuntu
---

O [Teamviewer](http://www.teamviewer.com) é um software de assistência remota útil quando precisar de ajudar um(a) amigo(a) ou precisar de ajuda. A sua utilização individual é gratuita (o que não se aplica para uso profissional).

Uma das vantagens, é que o mesmo funciona, tanto em Windows, como OSX ou Linux.

Assim para linux poderemos instalar um dos pacotes adequado para a distribuição que usamos, ou alternativamente, usar a versão para distribuições não suportadas, que pode inclusivamente ser instalada sem serem necessários privilégios de administração no computador em causa.

## Instalação em Ubuntu 32 e 64bits (13.10) desta ultima opção:

{% highlight ruby %}
tar -xzvf team_viewer.tar.gz
cd <directoria teamviewer>
{% endhighlight %}


iniciar com 
{% highlight ruby %}
./teamviewer
{% endhighlight %}


Caso dê erro verificar as dependências em falta com:
{% highlight ruby %}
./tv_setup --checklibs
{% endhighlight %}


Instalar as dependências indicadas.

No teste que efectuei precisei de instalar a seguinte libraria (ubuntu 64bits)

{% highlight ruby %}
sudo apt-get install libxtst6:i386
{% endhighlight %}


Após estes passos ficou a funcionar correctamente

. 
