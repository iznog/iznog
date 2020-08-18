---
layout: post
title: Fazer o upload do site criado com o jekyll de forma facil com o glynn
date: 2015-03-09
categories: jekyll
---
# Fazer o upload do site criado com o jekyll de forma facil com o glynn

Para não ter que efectuar o upload do site manualmente para o alojamento por FTP, após efectuar o "build" do mesmo com o jekyll, acabei por encontrar referenciado no site do [jekyll] (http://jekyllrb.com) o projecto glynn de [Damien MATHIEU] (https://github.com/dmathieu/glynn) que permite fazer o build do site e o upload apenas com o comando "glynn", simplificando bastante o processo.

De momento estou a usar o [Xubuntu] (http://xubuntu.org/) pelo que vou enumerar os passos que usei para instalar o jekyll e o glynn

Para instalar o jekyll é tão simples como abrir um terminal e com um utilizador que tenha permissões para instalar aplicações, digitar:

{% highlight ruby %}
	sudo apt-get install jekyll
{% endhighlight %}

Após a instalação do jekyll foi necessário instalar o ruby-dev, pois dava erro ao fazer o build do glynn sem este pacote.

{% highlight ruby %}
	sudo apt-get install ruby-dev
{% endhighlight %}

De seguida só é necessário executar o comando que se encontra na página do Damien Mathieu 

{% highlight ruby %}
	gem install glynn --source http://gemcutter.org
{% endhighlight %}

Se tudo correr como previsto o glynn será instalado.

Será necessário no projecto, no ficheiro _config.yml efectuar a configuração dos dados da localização e login do servidor FTP de destino.

Exemplo do ficheiro _config.yml:

{% highlight ruby %}
name: endereço do site
markdown: redcarpet
highlighter: pygments

ftp_host: 'endereco do servidor ftp'
ftp_dir: '/public/www'
ftp_passive: false

# optional
ftp_port: 21                  # default 21
ftp_username: 'ftpuser'     # default read from stdin
ftp_password: 'ftppassword' # default read from stdin
{% endhighlight %}

De seguida, estando na raiz da estrutura de pasta do site, basta digitar "glynn".

