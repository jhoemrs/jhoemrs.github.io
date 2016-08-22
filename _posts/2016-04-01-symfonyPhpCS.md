---
layout: post
title: "Symfony PHP Code Sniffer"
excerpt: "Symfony Coding Standards Code Sniffer, O que é ? Aprenda e Instale!"
tags:
 - Symfony
feature: images/postagens/symfonyPhpCs/symfonyPhpCs.jpg
comments: true
---
Symfony PHP Code Sniffer ?!
Mas e aí o que é primeiramente o **PHP Code Sniffer** ?

Vamos explicando aos poucos logo abaixo...

Sabemos que dificilmente um código será mantido pelo seu criador eternamente.

Por isso precisamos de padrões de código, para manter um código bem escrito e descrito, e as convenções de código padronizam de acordo com a experiência já testada na área.

**O PHP Code Sniffer, visa validar um padrão de código.**

Os Padrões de Código Definem:

  > Indentação do Código  
  >  Conveção de nomenclatura  
  >  Espaços em Branco  
  >  Padrão de Comentários  
  >  Etc...  

Assim sendo, padrões de código definem um código com qualidade, legibilidade, assim como reduzem custo de manutenção.

O `Php Code Sniffer` é um módulo da biblioteca `PEAR`, que possui um "Script" que verifica violações no Standard ( Padrão ) definido.

Para inicio de conversa precisamos ter o `PEAR` instalado execute:

{% highlight shell %}
sudo apt-get install php-pear
{% endhighlight %}

Agora vamos para a parte do `CodeSniffer` propriamente dita.

Executaremos agora:
{% highlight shell %}
sudo pear install PHP_CodeSniffer
{% endhighlight %}

Após a instalação, verificaremos se está instalado, execute:
{% highlight shell %}
phpcs -i
{% endhighlight %}

Você será capaz de ver os Standards instalados que será algo parecido com isso:
<figure>
	<img src="{{ site.url }}/images/bancoPostagens/symfonyphpcs/phpcsi.png">
</figure>

Porém o nosso Querido `SYMFONY 2` não aparecerá aí ...
Porque esse **Standard** ainda não está instalado.

Agora vamos encontrar qual o caminho está seu `PEAR` para instalarmos este **Standard**.
Execute:
{% highlight shell %}
pear config-show | grep php_dir
{% endhighlight %}

Agora entre dentro do caminho acima `+ PHP/CodeSniffer/Standards`, no meu caso assim:
<figure>
	<img src="{{ site.url }}/images/bancoPostagens/symfonyphpcs/phpcsdir.png">
</figure>

Agora dentro da Pasta de **Standards**, vamos adicionar o nosso `Symfony 2` como padrão reconhecido, clonando o projeto do **[Symfony Standards](https://github.com/leaphub/phpcs-symfony2-standard)**, para dentro desta pasta, com os seguinte comando:
{% highlight shell %}
sudo git clone https://github.com/leaphub/phpcs-symfony2-standard.git Symfony2
{% endhighlight %}

Logo configuraremos o nosso `PHPCS` para analisar como padrão os Standards do Symfony2...
{% highlight shell %}
phpcs --config-set default_standard Symfony2
{% endhighlight %}

Para utilizar, podemos ou via linha de comando chamar o `PHPCS` para analisar a pasta `src/` do projeto ou integrar com a IDE.
Para fazer a chamada via linha de comando utilize:
{% highlight shell %}
phpcs --standard=Symfony2 --extensions=php src/
{% endhighlight %}

Lembre-se que só irá funcionar desta forma se você estiver dentro da pasta do projeto, senão você terá que referenciar o caminho completo para a pasta `src/`` .

Aqui finalizamos a instalação do `Symfony 2 Standard Php Code Sniffer` !

Como utilizo o `PhpStorm` (recomendo demais esta IDE), vou ensinar como integrar com esta IDE.

Primeito entre em Settings em sua IDE, e na busca dos Settings digite `Code Sniffer`.

<figure>
	<img src="{{ site.url }}/images/bancoPostagens/symfonyphpcs/phpstormcs1.png">
</figure>

Onde se encontra Configuration Local clique nos três pontinhos **...** para validarmos nosso `phpcs` , conforme imagem abaixo:

<figure>
	<img src="{{ site.url }}/images/bancoPostagens/symfonyphpcs/phpstormcs2.png">
</figure>

Após esta mensagem voltaremos e clicaremos em Inspections lá nos Settings, logo a direita onde marquei de amarelo selecione Default.
<figure>
	<img src="{{ site.url }}/images/bancoPostagens/symfonyphpcs/phpstormcs3.png">
</figure>

Onde fiz um circulo vermelho, clique para atualizar, e na setinha selecione o nosso Padrão `Symfony 2`.

Provavelmente acenderá algumas luzes em sua IDE passe o mouse por cima, e comece a melhorar seu código...

Veja os exemplos abaixo:
<figure>
	<img src="{{ site.url }}/images/bancoPostagens/symfonyphpcs/phpstormcs4.png">
</figure>

<figure>
	<img src="{{ site.url }}/images/bancoPostagens/symfonyphpcs/phpstormcs5.png">
</figure>

Bom meus amigos, é isso, espero que tenham gostado, e que sigam no passo a passo de fazer um código, limpo, legivel e inteligivel !
Seja inteligente !

Um abraço.

<i class="icon-smile"></i>
