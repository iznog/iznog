---
layout: post
title: Configurar MySQL Server no ubuntu server 
date: 2021-01-15
author: Paulo
categories: linux, mysql
---

Nas versões mais recentes do Ubuntu ao instalarmos o MySQL Server não é possivel aceder ao utilizador do root com password sem ser no utilizador root do sistema operativo.

Para que seja possivel aceder ao utilizador root do MySQL mesmo com outro utilizador da instalação do linux, devemos seguir os seguintes passos na linha de comandos:

{% highlight bash %}
mysql_secure_installation 
{% endhighlight %}

e seguir os passos.

aceder ao MySQL

{% highlight bash %}
mysql -u root
{% endhighlight %}

Alterar o plugin de autenticação do user root@localhost

{% highlight bash %}
mysql> update user set plugin="mysql_native_password" where host="localhost" and user="root";
{% endhighlight %}

de seguida já podemos alterar a palavra passe do utilizador root 

{% highlight bash %}
mysql> ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password_pretendida';
{% endhighlight %}

Desta forma já podemos aceder mesmo com outro utilizador no servidor onde está instalado o MySQL, ou também através de um tunel ssh de outro computador (por exemplo com o mysql workbench)
