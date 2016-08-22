---
layout: post
title: "Novo Bundle Symfony"
excerpt: "Aprenda a Criar um novo Bundle no Symfony e Limpar o AppBundle()."
tags:
 - Symfony
feature: http://i.imgur.com/Ds6S7lJ.png
comments: true
---

Hoje iremos criar nosso Bundle !

Um bundle é algo que pode ser reutilizado como uma peça independente de software, por exemplo, se um Bundle Fatura depende do Bundle Produto para funcionar, então não há sentido dos dois estarem separados.

Esta informação está disponível no **[Symfony Best Practices](http://symfony.com/doc/current/best_practices/creating-the-project.html)** , fiz uma tradução livre e resumida, ainda exerço algumas coisas que devem ser melhoradas neste intuito, já criei bundles que não funcionavam como uma peça sozinha mas funcionavam bem para organização, então é uma espada de 2 gumes, mas seguir as melhores práticas sempre acredito que seja uma boa, mas não é algo de extrema preocupação para quem está aprendendo.

Vamos lá, mão na massa!

Primeiro vamos limpar o Bundle que já veio com nosso projeto.

<figure>
	<img src="{{ site.url }}/images/bancoPostagens/novoBundle/limparPastasAppKernel.png">
</figure>

Para limpar o Bundle antigo apague-o do AppKernel e exclua as duas pastas AppBundle que estão selecionadas também na imagem acima, o próximo passo é limpar nosso routing.yml conforme imagem abaixo.

<figure class="half">
	<a href="{{ site.url }}/images/bancoPostagens/novoBundle/routingSujo.png"><img src="{{ site.url }}/images/bancoPostagens/novoBundle/routingSujo.png"></a>
	<a href="{{ site.url }}/images/bancoPostagens/novoBundle/routingLimpo.png"><img src="{{ site.url }}/images/bancoPostagens/novoBundle/routingLimpo.png"></a>
</figure>

Agora abrimos o terminal e acessaremos a pasta de nosso projeto.

<figure>
	<img src="{{ site.url }}/images/bancoPostagens/novoBundle/pastaProjeto.png">
</figure>

Após isso executaremos o comando:

{% highlight shell%}
bin/console generate:bundle
{% endhighlight %}

Nos depararemos agora com a primeira pergunta:
{% highlight shell%}
Are you planning on sharing this bundle across multiple applications? [no]:
{% endhighlight %}

Ao Pressionar Enter você estará selecionando a **resposta padrão** que se encontra **entre colchetes**.

**IMPORTANTE**, este tipo de resposta padrão poderá ser utilizado e será, em vários comandos bin/console que executaremos daqui para frente.

Logo após isto será questionado o nome do nosso novo Bundle, que deve terminar com Bundle.
{% highlight shell%}
Bundle name:
{% endhighlight %}
Para dar sequência escolhi o nome de **JornalBundle** para nossa aplicação.

Próximo questionamento será:
{% highlight shell%}
Target Directory [src/]:
{% endhighlight %}

A não ser que você esteja fazendo algo muito customizado, o costume do bundle é se localizar dentro de src/ .
Pressione Enter para continuar.

Logo será nos dado a próxima questão, qual será o formato de nossa configuração, por padrão é sugerido annotation, é exatamente ele que vamos utilizar em nossos exemplos.
{% highlight shell%}
Configuration format (annotation, yml, xml, php) [annotation]:
{% endhighlight %}

Ao fim deste passo, terá uma tela similar a esta:
<figure>
	<img src="{{ site.url }}/images/bancoPostagens/novoBundle/generateBundle.png">
</figure>

Agora Rode o Projeto com o Comando:
{% highlight shell%}
bin/console server:run
{% endhighlight %}

Ao acessarmos o endereço do servidor iniciado, se você executou todos os passos acima, verá a seguinte tela no navegador:

<figure>
	<img src="{{ site.url }}/images/bancoPostagens/novoBundle/navegadorHelloWorld.png">
</figure>

Oficialmente Seja Bem-Vindo ao seu Bundle no Symfony.

Um abraço, e até a próxima!
