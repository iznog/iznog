---
layout: post
title: Plesk - importação de email - pastas grandes
date: 2022-05-19
author: Paulo
tags: linux plesk email
---

Ao importar caixas de correio que contêm pastas com muitos emails, a ferramenta de importação pode falhar a efetuar a sincronização.

Assim e seguindo as instruções que estão no site de suporte do plesk [aqui](https://support.plesk.com/hc/en-us/articles/360009682414--BUG-Mail-importing-of-a-large-mailbox-fails-in-Plesk-Failed-to-backup-IMAP-folder-INBOX-got-more-than-1000000-bytes-All-messages-of-that-folder-will-not-be-migrated), podemos efetuar a alteração no ficheiro /opt/plesk/python/2.7/lib64/python2.7/imaplib.py :

A alteração a efetuar será na linha que contêm:

{% highlight python %}
    _MAXLINE = 1000000
{% endhighlight %}

e alterar o valor, acrescentado 2 zeros, passando a:

{% highlight python %}
    _MAXLINE = 100000000
{% endhighlight %}


Depois de gravar as alterações, basta ir à configuração da importação de email e clicar em "resync" para continuar o processo de importação.


