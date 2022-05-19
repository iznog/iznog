---
layout: post
author: Paulo Cruz
title: SCRCPY - mostrar e controlar dispositivo android no linux
date: 2020-08-18
tags: linux android scrcpy
---

Tal como refere na página do projeto [scrcpy](https://github.com/Genymobile/scrcpy):

"This application provides display and control of Android devices connected on USB (or over TCP/IP). It does not require any root access. It works on GNU/Linux, Windows and macOS."

A aplicação permite visualizar e controlar dispositivos android por USB (ou através de TCP/IP).

Sendo multiplataforma permite a sua utilização em linux, assim como no Windows e OSX.

## O que é possivel fazer com este software
Normalmente uso o software para a validação de sites/aplicações web do meu portatil ou desktop e quando necessito de dar formação na utilização de aplicações específicamente em dispositivos móveis.

### Instalação em ubuntu
A aplicação está disponivel nos repositórios de várias distribuições, como se pode verificar pelas instruções na página do projeto. 
No caso particular do ubuntu (testado no 18.04 e 20.04), basta executar o comando no terminal (tem que ser administrador do computador):
{% highlight bash %}
sudo apt-get install scrcpy
{% endhighlight %}

### Preparação do equipamento android para utilização com o scrcpy

Assim para podermos usar temos que ativar o "Developer mode" e o "usb debugging" no equipamento que pretendemos controlar. 
O último equipamento que usei com o scrcpy foi um samsung S6 (embora já tenha usado com outros equipamentos android, como por exemplo no samsung galaxy tab s3), pelo que apesar de ser fácil de encontrar com uma pequena pesquisa no duckduckgo, descrevo abaixo como se faz para este modelo em particular.

Ativar o developer mode:
- Definições
- Sobre o telefone
- Informação Software
- pressionar no Build Number várias vezes até aparecer a informação de que o "Developer mode" está ativo
- Voltar ao ecrã principal das definições
- Entrar em Opções de desenvolvimento
- Ativar a opção "Opçoes de desenvolvimento"
- Ativar o "usb debugging"

Depois destes passos, ligar o cabo usb ao computador e num terminal digitar o comando

{% highlight bash %}
scrcpy
{% endhighlight %}

Para aprender a controlar o dispositivo, podemos consultar a ajuda do scrcpy, bastando para isso, executar no terminal o seguinte comando:

{% highlight bash %}
scrcpy --help
{% endhighlight %}

ou em alternativa:

{% highlight bash %}
man scrcpy
{% endhighlight %}




