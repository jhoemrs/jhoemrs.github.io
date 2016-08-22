---
layout: post
title: "Ambiente Symfony"
excerpt: "Arquivos e Pastas Iniciais Symfony"
tags:
 - Symfony
feature: http://i.imgur.com/Ds6S7lJ.png
comments: true
---

Um dos maiores trunfos do Symfony é sua organização, você ter uma organização padrão de pastas separadas em Bundles, ajuda e muito em projetos grandes, além da sua maior capacidade de componentizar as coisas.

Já iniciamos nosso projeto, como você pode ver **[NESTE POST](http://jhoemrs.github.io/desenvolvimento/iniciandoProjetoSymfony)** !

Ao abrir um projeto Symfony nos deparamos com a seguinte estrutura de pastas:

<figure>
	<img src="{{ site.url }}/images/bancoPostagens/ambienteSymfony/estruturaPastas.png">
</figure>

Uma aplicação que utiliza Symfony provavelmente contará com um Banco de Dados, não é obrigatória a aplicação ter um Banco de Dados, mas é quase um desperdício ter um ORM parrudo como o Doctrine que é por padrão utilizado no Symfony e jogar fora seu potencial, para isso precisamos entrar nos **PARAMETERS.YML** de nossa aplicação e indicar onde está localizado nosso Banco.

Sendo assim localize o **parameters.yml** dentro de **app/config** e informe onde está localizado seu banco, seu user e senha do banco, etc...

<figure>
	<img src="{{ site.url }}/images/bancoPostagens/ambienteSymfony/parameters.png">
</figure>

O parameters não serve apenas para o Banco, podemos usar de várias formas, até mesmo para passar informações pra nossos serviços na aplicação, devemos ver nas próximas aulas.

Se você não tem nenhum banco instalado, recomendo que utilize o MySQL, é suficientemente simples e completo para aprendizagem e para ser utilizado em aplicações reais !

Para instalar não tem muito mistério...
{% highlight shell %}
sudo apt-get install mysql-client mysql-server mysql-workbench
{% endhighlight %}
Acredito que com estes comandos terá uma instalação completinha do MySQL sem muito o que acrescentar.
Durante a instalação pedirá para você definir a senha do user root, preste atenção pois será a senha de acesso ao banco.

Se você quer aprender mais sobre banco de dados recomendo o blog de um amigo meu que é especialista no assunto: **[DBANCHITE](http://dbanchite.blogspot.com)** !

Bom, o segundo ponto que gostaria de mostrar é onde nossos Bundles são registrados, temos um arquivo que identifica estes Bundles por assim dizer, necessário ao criarmos o bundle de nossa aplicação.

Assim como ao realizar a limpeza/excluir algum bundle, você deve retirá-lo do **AppKernel** senão provavelmente a sua aplicação vai quebrar.

O nosso arquivo inicial do AppKernel se encontra assim:
<figure>
	<img src="{{ site.url }}/images/bancoPostagens/ambienteSymfony/appKernel.png">
</figure>

Por observação já deduzimos a partir do código que temos a opção de inicializar Bundles a partir do Enviroment que eles se encontram ou seja, em Produção alguns bundles não estarão ativos, como nossa barra de Debug por exemplo.

Onde iremos fazer grande parte do nosso trabalho, controlar as rotas e Requests e Responses da vida é em nosso Controller, lá é uma parte importante da alma do Symfony, trabalharemos muito ali e por ser tão necessário, o nosso projeto quase em branco conta com 1 Controller criado, pois afinal precisamos acessar alguma rota:

<figure>
	<img src="{{ site.url }}/images/bancoPostagens/ambienteSymfony/controller.png">
</figure>

Na minha cabeça eu vejo o Symfony com a alma distribuída (Quase um Lord Voldemort) e o que mais vamos trabalhar no Symfony e veremos mais a frente é:

>Controller  
Entity  
Repository  
Services  
Views  

Básicamente:
O Controler chama um Service que pode verificar o que foi pedido e que acessa o Repository, que vai na Entity (**Controlada por Nosso ORM - Doctrine**) manipular informações, esta informação volta pro Service onde pode ser manipulada ou verificada, enviada de volta pro controller e tudo isso pode ser visto por nós em Views com nosso **Framework Front-End TWIG** .

Este fluxo pode mudar de N formas, esta é apenas uma pequena exemplificação.

Nas próximas postagens faremos nosso Bundle, e nosso Hello World Personalizado.

Se você chegou aqui e não entendeu nada e não tem seu Symfony configurado, acompanhe as Postagens Anteriores...

<a href="http://jhoemrs.github.io/desenvolvimento/composerInstall" class="btn btn-primary btn-sm">1 - Composer Install</a>
<a href="http://jhoemrs.github.io/desenvolvimento/symfonyInstall" class="btn btn-primary btn-sm">2 - Symfony Install</a>
<a href="http://jhoemrs.github.io/desenvolvimento/iniciandoProjetoSymfony" class="btn btn-primary btn-sm">3 - Iniciando Projeto Symfony</a>
