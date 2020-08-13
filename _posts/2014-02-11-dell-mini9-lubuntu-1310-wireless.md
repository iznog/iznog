---
layout: default
title: instalação de driver wireless DELL mini9
categories: linux
author: Paulo Cruz
---
A instalação do Lubuntu 13.10 no netbook DELL mini 9, decorreu sem sobressaltos, excepto no caso dos drivers para wireless, em que é necessário efectuar o download e instalação do firware da placa em causa

{% highlight ruby %}
lspci | grep Network
{% endhighlight %}

resultado: 
{% highlight ruby %}
03:00.0 Network controller: Broadcom Corporation BCM4312 802.11b/g LP-PHY (rev 01)
{% endhighlight %}

remover bcmwl-kernel-source
{% highlight ruby %}
sudo apt-get remove bcmwl-kernel-source
{% endhighlight %}

instalar b43-fwcutter b43-sta-dkms firmware-b43-installer
{% highlight ruby %}
sudo apt-get install b43-fwcutter b43-sta-dkms firmware-b43-installer
{% endhighlight %}

na directoria /etc/modprobe.d
{% highlight ruby %}
cd /etc/modprobe.d
{% endhighlight %}

editar ficheiro broadcom-sta-dkms.conf comentar a linha:

" blacklist b43"

Deverá reiniciar o computador e se tudo correr bem ficará a funcionar o wireless.

Nota: apesar de este modelo estar equipado com um modem GSM, ainda não tive oportunidade de testar...




