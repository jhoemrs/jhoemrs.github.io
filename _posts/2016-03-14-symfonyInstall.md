---
layout: post
title: "Symfony Install"
excerpt: "Instale e deixe o Symfony pronto para ser utilizado em seu linux."
tags:
 - Symfony
feature: images/postagens/symfonyInstall/symfonyInstall.jpg
comments: true
---

Hoje mostrarei como é simples instalar e deixar o Symfony disponivel para o linux.

Assim como o composer o Symfony tem algumas instruções para instalar e deixa-lo funcionando:

<figure>
	<a href="https://symfony.com/download" data-toggle="tooltip" title="Symfony Download">
		<img src="{{ site.url }}/images/bancoPostagens/symfonyInstall/comoInstalar.png">
	</a>
</figure>

Já vi algumas maneiras diferentes de instalar o Symfony então caso haja alguma alteração clique no link acima para obter maiores informações de como instalar.

Logo que executamos o primeiro comando listado acima podemos nos deparar com a seguinte mensagem:

<figure>
	<a data-toggle="tooltip" title="Curl Not Found">
		<img src="{{ site.url }}/images/bancoPostagens/symfonyInstall/curlNotFound.png">
	</a>
</figure>

Sendo assim precisamos instalar o curl, um erro comum é se instalar o php5-curl esperando que este seja o problema, bom não se trata do php5-curl o pacote que não está instalado é do próprio curl.
Para isso apenas execute:
<figure>
	<img src="{{ site.url }}/images/bancoPostagens/symfonyInstall/instalarCurl.png">
</figure>

Após o curl instalado e tudo corretamente setado:

Execute aqueles primeiros dois comandos de instalação do Symfony:
{% highlight shell %}
sudo curl -LsS https://symfony.com/installer -o /usr/local/bin/symfony
{% endhighlight %}

Este primeiro comando baixará o Symfony e o Alocará na pasta /usr/local/bin/ pois foi passado o parametro -o de OutPut .

{% highlight shell %}
sudo chmod a+x /usr/local/bin/symfony
{% endhighlight %}

Este segundo comando tornará o symfony Executável.

Sendo assim só executar **symfony** de qualquer lugar no console que chamará o instalador do symfony, como mostrado abaixo:
<figure>
	<img src="{{ site.url }}/images/bancoPostagens/symfonyInstall/chamadaSymfony.png">
</figure>

Sendo assim já temos o Symfony pronto para iniciarmos um novo projeto !

Obrigado e até a próxima !
