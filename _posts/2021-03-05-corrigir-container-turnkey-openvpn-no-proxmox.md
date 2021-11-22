---
layout: post
title: Corrigir configuração de container turnkey openvpn em proxmox
date: 2021-03-06
author: Paulo
tags: linux, openvpn, turnkey
---

Usando o template turnkey no proxmox para criar um servidor openvpn, após a sua configuração de acordo com os passos da instalação do container, poderemos deparar-nos com um erro em que os clientes de VPN não se conseguem ligar.

Para tentarmos averiguar com mais detalhe os erros, podemos alterar o ficheiro de configuração do servidor de openvpn em /etc/openvpn/server.conf e adicionar as linhas:
 
{% highlight bash %}
log         /var/log/openvpn/openvpn.log
log-append  /var/log/openvpn/openvpn.log
{% endhighlight %}

E se necessitamos de mais detalhe mudamos também para

{% highlight bash %}
verb  5
{% endhighlight %}

Reiniciamos o servidor de openvpn 

{% highlight bash %}
systemctl restart openvpn
{% endhighlight %}

Podemos verificar os erros no ficheiro de log criado em /var/log/openvpn e com o nome indicado na configuração que no meu caso será openvpn.log.

No mesmo, encontraremos um erro a indicar que não foi possivel a criação da interface tun. Esta mensagem deve-se ao facto de não ser permitido ao container criar determinados dispositivos, visto estar configurado para funcionar no modo "unprivileged".

Para ultrapassar esta questão devemos fazer o seguinte:

Encerramos o container

Adicionamos no proxmox, no ficheiro de configuração do container, em /etc/pve/lxc e com o nome de XXX.conf (em que o XXX será o numero do container, por exemplo 102.conf) o seguinte:

{% highlight bash %}
lxc.mount.entry: /dev/net/tun dev/net/tun none bind,create=file 
{% endhighlight %}

De seguida poderemos iniciar novamente o container e já poderemos experimentar a nossa ligação de VPN. Se verificarmos os logs, agora já não temos a mensagem de erro.
