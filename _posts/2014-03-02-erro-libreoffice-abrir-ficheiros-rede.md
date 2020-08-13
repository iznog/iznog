---
layout: default
title: Libreoffice erro abrir ficheiros rede no KDE
categories: libreoffice
---
# Libreoffice - erro a abrir ficheiros de rede no KDE

Se ao tentar abrir ficheiros com o libreoffice no KDE de um recurso da rede, nada acontece, pode dever-se a um bug existente e reportado [aqui](https://www.libreoffice.org/bugzilla/show_bug.cgi?id=67527), sendo que já referi o mesmo no meu [post]({%post_url 2013-11-19-libreoffice-4-1-do-ppa-de-libreoffice-org-erro-abrir-ficheiro-de-partilha-samba%}).

Para corrigir o problema, enquanto o problema não é corrigido em alguma actualização, devemos nos atalhos do libreoffice localizados em /usr/share/applications, comentar a linha "X-KDE-Protocols=file,http,smb,ftp,webdav".

Aproveitando a sugestão colocada no comentário #47 ao report do bug referenciado acima, podemos fazer o seguinte:

- abrir um terminal, no kde podemos usar o konsole
- executar o seguinte:

{% highlight ruby %}
sudo sed -i 's/X-KDE-Protocols=file,http,smb,ftp,webdav/#X-KDE-Protocols=file,http,smb,ftp,webdav/' /usr/share/applications/libreoffice-*
{% endhighlight %}


