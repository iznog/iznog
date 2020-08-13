---
layout: default
title: Erro de ligacao ao servidor de licenças pelos add-ons
categories: SAP B1
---
# Erro de ligacao ao servidor de licenças pelos add-ons

Após instalação do cliente de SAP B1 em Windows Server 2008 R2 e instalação sem quaisquer contratempos dos respectivos add-ons disponiveis, para a empresa em uso, os add-ons davam erro a iniciar, com mensagem de erro relacionada com a impossibilidade de se ligarem ao servidor de licenças.

Este erro acontecia, apesar de conseguir entrar sem problemas no SAP B1.

Após diversas verificações de todos os ficheiros de configuração do SAP e dos add-ons, assim como da reinstalação, do cliente SAP e respectivos add-ons, continuei com o mesmo problema.

No scn.sap.com, encontrei este [thread] (http://scn.sap.com/thread/3215229) de alguém com o mesmo problema.

A solução passou por copiar o ficheiro localizado em 

{% highlight ruby %}
	c:\Program files (x86)\SAP\SAP Business One\Conf\b1-local-machine.xml
{% endhighlight %}
para a pasta de instalação da DI API em 
{% highlight ruby %}
	c:\Program files (x86)\SAP\SAP Business One DI API\
{% endhighlight %}
sobrepondo o ficheiro que lá se encontrava, que aparentemente não foi actualizado durante a instalação.

Após esta alteração, ficaram os add-ons a funcionar como seria de esperar.
