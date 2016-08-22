---
layout: post
title: "Symfony 3 jQuery BootStrap Install"
excerpt: "Utilizando Assetic para Instalar Dependencias JQuery e Bootstrap em um projeto Symfony3"
tags:
 - Symfony
 - Bootstrap
 - Jquery
feature: http://i.imgur.com/Ds6S7lJ.png
comments: true
---

Utilizar os Assets para instalar o `Bootstrap` e o `jQuery` (entre outros) pode ser um desafio muito grande para os iniciantes no Symfony.

Se você assim como eu, deseja utilizar o composer para gerenciar suas dependências e não gostaria de colocar diretamente estes Assets genéricos na pasta web, bom existe uma excelente forma de utilizar os mesmos.

Hoje irei demonstrar um dos métodos de Instalação com grande embasamento na documentação do **[SYMFONY](http://symfony.com/doc/current/cookbook/assetic/asset_management.html)** que você pode conferir mais detalhes se desejar direto na documentação.

Necessito maiores buscas para dizer se o método que demonstrarei é uma boa prática ou se segue os `Design Patterns` indicados, então que sirva mais como estudo ou base se você necessita fazer o mesmo.
E se você tiver uma opinião ou um material que possa vir aprimorar o que aqui descrevo, fique à vontade para comentar, até agradeço !

Vamos lá, mãos à obra!

O Primeiro passo foi dizer ao meu composer quais dependências eu vou instalar, a primeira de todas é o `assetic/bundle` então entre na pasta do seu projeto e execute o seguinte comando:
{% highlight shell %}
composer.phar require symfony/assetic-bundle
{% endhighlight %}

Então agora habilite este `Bundle` no seu `AppKernel.php` da sua aplicação Symfony:
{% highlight php %}
<?php
// app/AppKernel.php

// ...
class AppKernel extends Kernel
{
    // ...

    public function registerBundles()
    {
        $bundles = array(
            // ...
            new Symfony\Bundle\AsseticBundle\AsseticBundle(),
        );

        // ...
    }
}
{% endhighlight %}

Agora vamos no nosso arquivo `config.yml` e colocar estas configurações mínimas do bundle:
{% highlight yaml %}
# app/config/config.yml

# Assetic Configuration
assetic:
    debug:          '%kernel.debug%'
    use_controller: '%kernel.debug%'
    filters:
        cssrewrite: ~
# ...
{% endhighlight %}

Agora que já temos nosso gerenciador de `assets` instalado, precisamos do `jQuery` e do `Bootstrap`.  

Vamos dizer diretamente ao composer os componentes que precisamos.

Primeiro `jQuery`:
{% highlight shell %}
composer.phar require components/jquery
{% endhighlight %}

Agora o `Bootstrap`:
{% highlight shell %}
composer.phar require twbs/bootstrap
{% endhighlight %}

Ao terminar a Instalação dos dois voltaremos ao nosso Arquivo `config.yml` e adicionaremos estes `assets` da seguinte forma:
{% highlight yaml %}
# Assetic Configuration
assetic:
    debug:          '%kernel.debug%'
    use_controller: '%kernel.debug%'
    filters:
        cssrewrite: ~
    assets:
        jquery:
            inputs:
                - '%kernel.root_dir%/../vendor/components/jquery/jquery.min.js'
        bootstrap_css:
            inputs:
                - '%kernel.root_dir%/../vendor/twbs/bootstrap/dist/css/bootstrap.min.css'
        bootstrap_js:
            inputs:
                - '%kernel.root_dir%/../vendor/twbs/bootstrap/dist/js/bootstrap.min.js'
{% endhighlight %}

Após isto nossos `assets` já estarão prontos para serem acessados por nossas views, porém para deixar a coisa ainda mais legal, vamos deduzir que o bootstrap e o jquery será um asset padrão, e então vamos alterar o nosso arquivo `base`.

Este arquivo pode ser localizado dentro da pasta do projeto seguido de `Resources/views/default/base.html.twig` lá então teremos nosso arquivo base, e vamos deixá-lo desta seguinte maneira:

{% gist 9fb3c1e2f4eda0116f4ef638a1909f70 %}

Agora só precisamos extender nossas futuras `views` apontando para `base` e teremos já o bootstrap disponível.

Para exemplificar e testar faça uma view deste forma:

{% gist 4b089dc2298a619bfd395bfced73030f %}

Se você ver o resultado do botão semelhante à esta imagem:
<figure>
	<img src="{{ site.url }}/images/bancoPostagens/symfonyJqueryBootstrap/botaoBootstrap.png">
</figure>

Você fez tudo corretamente!

Obrigado e Abraços !
