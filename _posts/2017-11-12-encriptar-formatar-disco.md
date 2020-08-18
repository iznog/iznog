---
layout: post
title: Encriptar e formatar discos em linux
date: 2017-11-12
categories: linux
---
## Passos para encriptar discos em Linux (neste caso testado em xubuntu 16.04)

Limpar disco

{% highlight bash %}
    dd if=/dev/zero of=/dev/<disk>
{% endhighlight %}


Encriptar o disco

{% highlight bash %}
    cryptsetup -y -v luksFormat /dev/<disk>
{% endhighlight %}

Desencriptar o disco para acesso

{% highlight bash %}
    cryptsetup luksOpen /dev/<disk> <nome>
{% endhighlight %}

o nome pode ser o que se quiser
formatar o disco

{% highlight bash %}
    mkfs.ext4 /dev/mapper/<nome>
{% endhighlight %}

criar ponto de montagem

{% highlight bash %}
    mkdir /media/<ponto de montagem>
{% endhighlight %}

montar o disco

{% highlight bash %}
    mount -t ext4 /dev/mapper/<nome> /media/<ponto de montagem>
{% endhighlight %}

Para desmontar e encriptar novamente

{% highlight bash %}
    umount /media/<ponto de montagem>
    cryptsetup luksClose <nome>
{% endhighlight %}
