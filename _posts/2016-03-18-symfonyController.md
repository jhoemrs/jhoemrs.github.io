---
layout: post
title: "Symfony Controller"
excerpt: "Aprenda como utilizar e o que é o Controller do Symfony"
tags:
 - Symfony
feature: images/postagens/symfonyController/symfonyController.jpg
comments: true
---

O que é o Controller ?

O Objetivo de um Controller é sempre o mesmo, depois de um HTTP **Request** , criar e retornar um HTTP **Response**!

Esta resposta pode ser uma Página, JSON, ARRAY, XML, IMAGEM ou qualquer coisa que sua mente imaginar !

Este é o nosso Controller atual:
<figure>
	<img src="{{ site.url }}/images/bancoPostagens/symfonyController/controllerInicial.png">
</figure>

Primeira percepção que temos que ter é que muita coisa no Symfony pode e irá ser feita nos comentários das funções, sendo assim analisaremos o primeiro **@Route("/")** .
Como o nome já diz essa é a nossa rota, se alterarmos seu valor, devemos alterar também a url que será acessada, pois se mudarmos por exemplo para **@Route("/teste")** e acessarmos o endereço "/" veremos a seguinte tela de erro:

<figure>
	<img src="{{ site.url }}/images/bancoPostagens/symfonyController/noRouteFound.png">
</figure>

**Symfony** é amigável com seus erros, mas fuja deste Fantasma, literalmente !

Agora quero ensinar a vocês sobre o **@Template()** que vem do nosso **SensioFrameworkExtraBundle**.
Ele facilitará muito nosso trabalho no intuito de ligar o **Contoller** ao nosso **Html/Twig**, teremos que mudar algumas coisas em nosso controller, que ficará exatemente, assim:

{% highlight php %}
<?php

namespace JornalBundle\Controller;

use Symfony\Bundle\FrameworkBundle\Controller\Controller;
use Sensio\Bundle\FrameworkExtraBundle\Configuration\Route;
use Sensio\Bundle\FrameworkExtraBundle\Configuration\Template;

class DefaultController extends Controller
{
    /**
     * @Route("/")
     * @Template()
     */
    public function indexAction()
    {
        return array();
    }
}
{% endhighlight %}

Repare que adicionamos **use** diferente no começo de nosso código, sendo assim já podemos utilizar o **@Template()** tranquilamente.
Já podemos retirar todo o **$this->render()** , já que o @Template identifica qual é a view que deve ser renderizada de acordo com o nome do nosso Controller e nossa função no Controller.
Por exemplo , nossa view está localizada aqui:

<figure>
	<img src="{{ site.url }}/images/bancoPostagens/symfonyController/localizacaoView.png">
</figure>

Perceba que ela se encontra dentro da pasta **Default** , o que se relaciona diretamente com **DefaultController** , e o arquivo da view se chama **index.html.twig** o que se relaciona diretamente com a **indexAction**.

**Importante**: As funções do Controller sempre terminam com Action, até hoje ainda não vi casos em que não se utilize este padrão, se há, ainda preciso aprender ;) !

Após esta enxugada no código, preciso salientar caso você não siga o padrão do nome de pasta e função no nome da view, você pode dentro do **@Template()** chamar a view que deverá ser renderizada, como por exemplo:
{% highlight php %}
@Template("SensioBlogBundle:Post:show.html.twig")
{% endhighlight %}

Dando sequência as nossas atividades, agora veremos como um controller pode mandar valores para sua View ou para os não acostumados com o termo seu HTML/TWIG.
**TWIG** é o framework Front-End, então se me referir à algum deles já sabem !

Vamos alterar nosso **indexAction**:
{% highlight php %}
<?php
/**
 * @Route("/")
 * @Template()
 */
public function indexAction()
{
    $pessoa = 'Aprendiz de Symfony';

    return array(
        'pessoa' => $pessoa
    );
}
{% endhighlight %}

Se atualizarmos nossa página agora, veremos ainda o mesmo **HELLO WORLD** de sempre, perceba então que mandamos para nossa view 'pessoa' mas como utilizar???
Como fazer aparecer o **'Aprendiz de Symfony'** lá dentro de minha view ?

Utilizaremos o comando **[TWIG](http://twig.sensiolabs.org/documentation)** , então nossa view ficará assim:

<figure>
	<img src="{{ site.url }}/images/bancoPostagens/symfonyController/twigAtributo.png">
</figure>

Ao atualizarmos agora nossa página:

<figure>
	<img src="{{ site.url }}/images/bancoPostagens/symfonyController/helloAprendiz.png">
</figure>

Finalizaremos por hoje! Espero que tenham entendido um pouco mais de como funciona um Controller, e como ele envia um simples dado para uma view, também aprendemos como utilizar o ExtraBundle @Template() !

Forte Abraço!
