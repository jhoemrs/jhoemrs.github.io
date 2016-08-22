---
layout: post
title: "Instalando Git e Github"
excerpt: "Como instalar , configurar e o que é."
tags:
 - GitHub
 - Git
feature: http://i.imgur.com/Ds6S7lJ.png
comments: true
---

Hoje iniciaremos o aprendizado sobre Git e Github.

De acordo com a **[Documentação do Git](https://git-scm.com/book/pt-br/v1/Git-Essencial-Trabalhando-com-Remotos)** :

> Para ser capaz de colaborar com qualquer projeto no Git, você precisa saber como gerenciar seus repositórios remotos. Repositórios remotos são versões do seu projeto que estão hospedados na Internet ou em uma rede em algum lugar. Você pode ter vários deles, geralmente cada um é somente leitura ou leitura/escrita pra você. Colaborar com outros envolve gerenciar esses repositórios remotos e fazer o push e pull de dados neles quando você precisa compartilhar trabalho. Gerenciar repositórios remotos inclui saber como adicionar repositório remoto, remover remotos que não são mais válidos, gerenciar vários branches remotos e defini-los como monitorados ou não, e mais.

**Git** é a aplicação , **GitHub** é uma "montagem" desta aplicação.

Como assim ?
Bom, caso você tenha uma empresa e queira montar o seu próprio **Git**, você deve configurar em seu servidor uma cópia deste **Git** digamos que "limpo".

Você pode fazer **[DOWNLOAD](https://git-scm.com/downloads)**
 da aplicação, caso desejar.

Atualmente ainda não tive a oportunidade de realizar tal façanha. Assim que conseguir efetuar algo do tipo, trarei os *baby-steps* pra vocês da minha experiência.

Já o **GitHub** é uma plataforma **Git** montada e aberta para uso público (e privado, caso pague por isto) com servidores dispostos e prontos para você utilizar.
Basta criar sua conta e sair utilizando.

Creio que sair utilizando não é bem assim tão simples, né...  
Pelo menos pra quem nunca utilizou e não sabe nem por onde começar e se depara com  diversos comandos, realmente parecem assustadores...  

Mas rapidamente verão a facilidade que é !

Certamente irá adiantar sua vida. Se eu tivesse o conhecimento desta ferramenta antes, toda a minha matéria da faculdade e códigos estariam lá, bonitinhos, organizados e versionados, por exemplo!

Não me foi ensinado numa faculdade como utilizar e/ou ao menos como funciona. Acredito que as universidades estão muito atrasadas no quesito desenvolvimento, mas isso é matéria pra outro tópico.

Voltando ao assunto... Eu sou **Linux User**, apoio e sou apaixonado por seu uso para trabalho. Infelizmente para lazer não existem muitos investimentos para a produção de games nesse sistema operacional.

Bom o primeiro passo é: **Use Linux**!

Simples assim, caso queira usar Ruindows para programar arrume uma máquina virtual e instale o Linux !

**Como instalar o Git no Linux ?**

Primeiro atualize o seu repositório de aplicações com o famoso:

{% highlight shell %}
sudo apt-get update
{% endhighlight %}

Em seguida, basta selecionar o Git e instalar:

{% highlight shell %}
sudo apt-get install git
{% endhighlight %}

Após isso, o Git já estará instalado em seu sistema. Se bem me lembro, há uma configuração inicial que deve ser feita para setar nome e email :

{% highlight shell %}
git config --global user.name " Seu Nome"
git config --global user.email "Seu Email"
{% endhighlight %}

Em sequência, teremos devidamente configurado um ambiente com Git .


Se a sua distribuição Linux não contiver o **APT**, você pode instalar a partir do *source-code*.  
Para isso, siga através **[deste link](https://github.com/git/git)** para a página principal do repositório do projeto *Git* no *GitHub*. As instruções de acordo com sua distribuição para compilar a aplicação devem estar disponíveis na página.

Se você estiver pensando em iniciar no mundo Linux, indico algumas distribuições:  
1. **Debian**  
2. **Ubuntu**  
3. **Elementary OS**  

*Siga [@jhoemrs](http://www.twitter.com/jhoemrs) no twitter!*

Cada uma possui seus pontos positivos e negativos.


Hoje em dia a Distribuição que mais uso é o **Debian**, que é meu ambiente de trabalho diário.
Porém, em casa uso **Ubuntu**, e pra quem gosta de uma distribuição bonita, use o **Elementary**, que é de extremo bom gosto.

Por hoje é isso. Obrigado e aguardem as novas postagens de como utilizar o Git !
