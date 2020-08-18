---
layout: post
title: Sincronizacao de dispositivos logitech unifying em Linux
date: 2018-03-17
categories: hardware logitech
---

# Sincronização de dispositivos logitech unifying em Linux

A tecnologia unifying da Logitech, permite que com o mesmo receptor usb, se possam ligar até 6 dispositivos, desde que suportem esta tecnologia.

Para que se possa associar (ou emparelhar) um dispositivo com um determinado receptor, é necessário usar o software "Unifying Software" da Logitech, que disponibiliza o mesmo para Windows, Apple OSX e ChromeOS, não sendo o linux suportado pela marca.

Apesar disso, existem vários projectos que permitem efectuar esta mesma função sendo que um deles, é o [Solaar](https://pwr.github.io/Solaar/).

Se usar o ubuntu, a instalação passará apenas por abrir um  terminal e executar o seguinte comando:

{% highlight bash %}
sudo apt-get install Solaar
{% endhighlight %}

NOTA: Testado em ubuntu 16.04 and Linux Mint 18.
