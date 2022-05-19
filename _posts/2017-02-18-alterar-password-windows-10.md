---
layout: post
title: Windows 10 - Alterar password de utilizador
date: 2017-02-18
tags: jekyll
---
Esqueceram-se da vossa password do Windows? E agora?

Existe uma forma de alterar a vossa password para poderem voltar a ter acesso ao mesmo.

Primeiro, a não ser que já tenham uma pen ou CD disponivel com a uma Live Distro, necessitamos de um computador para efectuar o download de uma.
Normalmente uso o [Xubuntu](http://xubuntu.org/) , ou o [Ubuntu](http://www.ubuntu.com) ou qualquer outro derivado deste último.

Depois de fazermos o download do ficheiro ISO, vamos criar uma pen ou um CD com que possamos efectuar o arranque do PC. Como normalmente uso o linux, concretizo usando os passos descritos [aqui](http://www.paulocruz.com.pt/criar-um-disco-com-dd), para Windows podem seguir [aqui](http://www.paulocruz.com.pt/criar-disco-boot-windows).


Iniciamos o arranque como a Live Linux e montamos a particao do Windows, correspondente à instalação do sistema.

Vamos para a pasta "C:\Windows\System32"
{% highlight bash %}
    cd <mount point>/Windows/System32
{% endhighlight %}

procuramos o ficheiro cmd.exe e renomeamos para cmd.exe.tmp

{% highlight bash %}
    mv cmd.exe cmd.exe.tmp
{% endhighlight %}

procuramos o ficheiro setch.exe e renomeamos para cmd.exe
{% highlight bash %}
    mv cmd.exe cmd.exe.tmp
{% endhighlight %}


voltamos a renomear o ficheiro cmd.exe.tmp para setch.exe
{% highlight bash %}
    mv cmd.exe cmd.exe.tmp
{% endhighlight %}


Reiniciamos o computador mas retirando a pen ou CD usado para arrancar com o Live Linux e quando chegamos à janela de login, pressionamos a tecla de SHIFT 5 ou 6 vezes, aparecendo de seguida uma janela de linha de comandos.

***Nessa janela executamos os seguintes comandos:***

Para verificar quais os nomes de utilizador criados, nomeadamente o(s) que pretendemo(s) alterar  a password

{% highlight bash %}
    net user
{% endhighlight %}

Mudar a password

{% highlight bash %}
    net user <nomeutilizador> <novapassword>
{% endhighlight %}


De seguida deverá renomear para os nomes originais dos ficheiros, invertendo o processo descrito anteriormente (cmd.exe e sethc.exe)
