---
layout: post
title: "Aprimorando Git e Github"
excerpt: "Clone, Init, Add, Commit, Push, Pull , não sabe o que é ? Venha aprender do Init ao Push!"
tags:
 - GitHub
 - Git
feature: http://i.imgur.com/Ds6S7lJ.png
comments: true
---

**Git** é o nosso assunto de hoje !

No tópico anterior **[Instalando Git e Github](http://jhoemrs.github.io/desenvolvimento/usando-git-github)** demonstrei uma maneira bem fácil de instalar e ter em sua máquina o Git, que é a ferramenta para manipularmos nossos repositórios.  
Também foi falado das diferenças entre `Git` e `Github` e o que é cada um.

Além dos 2 comandos de configuração de `user` e `email`, não tivemos um verdadeiro contato com `Git` !

Mas isso mudará neste momento, o que abordaremos hoje:

1. **[Init](https://git-scm.com/docs/git-init)**
2. **[Clone](https://git-scm.com/book/pt-br/v1/Git-Essencial-Obtendo-um-Reposit%C3%B3rio-Git#Clonando-um-Reposit%C3%B3rio-Existente)**
3. **[Add](https://git-scm.com/docs/git-add)**
4. **[Commit](https://git-scm.com/docs/git-commit)**
5. **[Push](https://git-scm.com/docs/git-push)**
6. **[Pull](https://git-scm.com/docs/git-pull)**


Estes 5 comandos básicos do git serão explanados abaixo, o git possui diversos outros que serão assuntos para próximos tópicos.

Git Init
--------
{% highlight ruby %}
git init
{% endhighlight %}

O comando `git init` é responsável por inicializar um repositório em branco ou reinicializar algum já existente.

Quando criamos um novo repositório como na imagem abaixo é visível que nos deparamos com o `GIT INIT` como primeiro comando git para um novo repositório em branco.

<figure>
	<img src="{{ site.url }}/images/bancoPostagens/usandogit/repositorionovo.jpeg">
	<figcaption><a data-toggle="tooltip" title="Criando novo repositório.">Novo Repositório no Github</a></figcaption>
</figure>

Não se preocupe por agora com os comandos seguintes, rapidamente veremos todos eles.

Git Clone
---------
{% highlight ruby %}
git clone LINKDOREPOSITORRIO
{% endhighlight %}

Onde encontrar o `LINKDOREPOSITORIO` ?

<figure>
	<img src="{{ site.url }}/images/bancoPostagens/usandogit/ondeclonar.jpg">
	<figcaption><a data-toggle="tooltip" title="Link para Clonar o Repositorio.">Encontre facilmente o link do Repositorio</a></figcaption>
</figure>

Ao realizar o `GIT CLONE`, você estará realizando uma cópia do repositório em questão, ou como o nome já diz, uma clonagem.

Ao clonar um repositório git o mesmo já vira inicializado, **não** sendo **necessário** utilizar o `GIT INIT` em um repositório clonado.

Git Add
-------
{% highlight ruby %}
git add NomeDoArquivo.extensao
git add -a
{% endhighlight %}

<figure>
	<img src="{{ site.url }}/images/bancoPostagens/usandogit/jackestripador.jpg">
	<figcaption><a data-toggle="tooltip" title="Jack diz: Vamos por Partes.">Jack, o Estripador</a></figcaption>
</figure>

Como diria Jack nosso amigo acima, vamos por partes:
O comando que contém o `NomeDoArquivo.extensao` , você estará adicionando ao seu próximo commit apenas aquele arquivo.  
O comando que contém o `-a` , é uma abreviação para `-all` que significa (tudo) ou todos os arquivos, novos ou alterados, serão adicionados para o seu próximo commit.

Imagine o `Git Add` como um carrinho de compras, e a cada arquivo (ou todos) que você colocar no carrinho, será enviado para o repositório servidor quando você resolver commitar e empurrá-los.

Seguiremos nesta ordem, após adicionar os arquivos precisamos commitar o que nos leva ao nosso próximo tópico.

Git Commit
----------
{% highlight ruby %}
git commit -m "Mensagem sobre o que se trata seu commit."
{% endhighlight %}

Cada programador tem suas manias, então o que serve para mim talvez não sirva para você ou sua empresa, o parametro `-m` é obrigatório ( caso não se passe nenhum argumento "forçando" o contrário ), em minha visão sempre é bom você dizer sobre o que aquele `Commit` se trata, principalmente se você tiver que consultar suas alterações futuramente, eu costumo definir um padrão para minhas mensagens como "[DEV] Controller e Entidades" para quando eu estiver construindo controllers e entidades, ou, "[FIX] Controller e Entidades", quando eu estiver corrigindo alguma coisa ou realizando alguma alteração posterior em controllers e entidades, mas aí vai do gosto de cada um, ou da metodologia adotada, por sua empresa, ideal é que essa separação seja feita, com os issues, ou seja, arrumou issue, já é fix.

Fazendo isso seu `Commit` estará com arquivos adicionados, com a mensagem preparada, e pronto para ser enviado para o servidor.

O que nos leva a empurrar este `Commit` para lá com nosso `PUSH` !

Git Push
--------
{% highlight ruby %}
git push origin BRANCHDESTINO
{% endhighlight %}

Falaremos de `BRANCH` em um próximo tópico mas precisamos ao menos ter uma noção do que se trata para realizar a façanha de fazer o `PUSH` para o lugar certo em nosso repositório. Saiba então que seu repositório pode ser dividido em `branchs`, você pode ter o seu `branch master` de um `produto pronto`, testado e sem bugs, e um `branch desenvolvimento`, que podem estar trabalhando em `novas features` ainda não testadas, e com bugs, e após conseguirem uma nova versão deste produto, realizarem o `MERGE` para `unir` os `branchs`( Que também é assunto pra um próximo tópico).

Então escolha bem o branch que estiver trabalhando e jogue seu commit para ele.

Git Pull
--------
{% highlight ruby %}
git pull
git pull origin BRANCHRECEBEDOR
{% endhighlight %}

Pouco provável grandes projetos de programação serem feitos sozinhos, pessoas, ou até mesmo times estarão trabalhando ao mesmo tempo no projeto em várias features diferentes, e todas elas no mesmo repositório.

Para este exemplo vou utilizar você e mais 1 amigo.
O seu trabalho é fazer uma caixa, o do seu amigo é colocar uma cerveja na caixa.

<figure>
	<img height="50%" width="50%" src="{{ site.url }}/images/bancoPostagens/usandogit/caixacerveja.png">
	<figcaption><a data-toggle="tooltip" title="Uma deliciosa, caixa com cerveja">Ambos fizeram PUSH & PULL</a></figcaption>
</figure>

O repositório já está criado, você faz sua caixa, adiciona os arquivos, o commita, e faz push para o servidor.  
{% highlight ruby %}
git add caixa.box
git commit -m "[DEV] Caixa e seu compartimento."
git push origin master
{% endhighlight %}

Neste momento, seu amigo ainda não sabe que sua caixa está pronta, para receber esta caixa no código dele, ele precisa realizar um `PULL`, assim realizará toda a atualização do projeto conforme o último commit no servidor, no caso o seu.

Ao realizar o `PULL` e ver sua caixa, ele realiza seu trabalho e coloca a cerveja.
Para enviar a cerveja pro servidor seu amigo realizará :

{% highlight ruby %}
git add cervejeiro.beer
git commit -m "[DEV] Cerveja e seus beneficios."
git push origin master
{% endhighlight %}

Você não verá a cerveja automaticamente, é necessário você também realizar um `PULL` após ele ter commitado para o servidor, após realizar ambos estarão com a caixa e a cerveja em seus códigos.

*Siga [@jhoemrs](http://www.twitter.com/jhoemrs) no twitter!*

Obrigado galera e até a próxima !
