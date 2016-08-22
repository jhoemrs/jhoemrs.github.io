---
layout: post
title: "Python - Criando Relatório a Partir de Arquivo de Texto"
excerpt: "Aprenda a Manipular Dados em Arquivos Texto com Python, Criando um Relatório em Arquivo Texto com Python"
tags:
 - Python
 - Exercicios
feature: http://i.imgur.com/Ds6S7lJ.png
comments: true
---

Olá amigos, na antiga postagem sobre exercicios resolvidos em Python, surgiu uma questão nos comentários para se resolver.

Confira a postagem **[Aqui Neste Link](https://guiaprogramador.com.br/desenvolvimento/exerciciospython1)**.

Tivemos a Seguinte Questão:

<figure>
	<img src="{{ site.url }}/images/bancoPostagens/criandoRelatorioPython/sugestaoQuestao.png">
</figure>

{% highlight plaintext %}
A ACME Inc., uma empresa de 500 funcionários, está tendo problemas de espaço em disco no seu servidor de arquivos. Para tentar resolver este problema, o Administrador de Rede precisa saber qual o espaço ocupado pelos usuários, e identificar os usuários com maior espaço ocupado. Através de um programa, baixado da Internet, ele conseguiu gerar o seguinte arquivo, chamado "usuarios.txt":

alexandre 456123789
anderson 1245698456
antonio 123456456
carlos 91257581
cesar 987458
rosemary 789456125

Neste arquivo, o nome do usuário possui 15 caracteres. A partir deste arquivo, você deve criar um programa que gere um relatório, chamado "relatório.txt", no seguinte formato:

ACME Inc. Uso do espaço em disco pelos usuários
Nr. - Usuário - Espaço utilizado -  % do uso
1 alexandre 434,99 MB 16,85%
2 anderson 1187,99 MB 46,02%
3 antonio 117,73 MB 4,56%
4 carlos 87,03 MB 3,37%
5 cesar 0,94 MB 0,04%
6 rosemary 752,88 MB 29,16%
Espaço total ocupado: 2581,57 MB
Espaço médio ocupado: 430,26 MB

O arquivo de entrada deve ser lido uma única vez, e os dados armazenados em memória, caso sejam necessários, de forma a agilizar a execução do programa. A conversão da espaço ocupado em disco, de bytes para megabytes deverá ser feita através de uma função separada, que será chamada pelo programa principal. O cálculo do percentual de uso também deverá ser feito através de uma função, que será chamada pelo programa principal.
{% endhighlight %}

Algumas Observações que não podem Passar em Branco:

- O arquivo deve conter nos primeiros 15 espaços apenas o nome do Usuario ( Se esta Condição não for Cumprida o Código não funcionará Perfeitamente, terão então que ser feitos ajustes no código para limitar ou diferenciar os separadores das Strings )
- A questão não deixa tão claro o item acima, pq no texto enviado a lista aparece com os nomes sem espaços em branco, o que deveria ter para completar os 15 caracteres de nome

Sem Mais enrolação o nosso arquivo ficou assim:

**usuarios.txt**
{% highlight plaintext %}
alexandre      456123789
anderson       1245698456
antonio        123456456
carlos         91257581
cesar          987458
rosemary       789456125
{% endhighlight %}


**Nosso Código ficou assim:**
{% highlight python %}
__author__ = 'Jhonatan Mark'
#Exercicio Sugestão/Dúvida Questão

with open('usuarios.txt') as arquivo:
    linhas = arquivo.read().splitlines()
    arquivo.close()

def organizaNomes(lista):
    listaNome = []
    for i in range(len(lista)):
       listaNome.append(lista[i][0:14].rstrip())
    return listaNome

def organizaTamanhoConsumido(lista):
    listaConsumo = []
    for i in range(len(lista)):
        listaConsumo.append(int(lista[i][15:len(lista[i])]))
    return listaConsumo

def transformaByteEmMega(lista):
    listaEmMega = []
    for i in range(len(lista)):
        listaEmMega.append(round(int(lista[i])/1048576,2))
    return listaEmMega

def calculaPercentuais(lista):
    percentuais = []
    valorTotal = sum(lista)
    for i in range(len(lista)):
       percentuais.append(round((lista[i]/valorTotal)*100,2))
    return percentuais

def calculaEspacoMedio(lista):
    espacoMedio = round(sum(lista)/len(lista),2)
    return espacoMedio

def criaRelatorio(nomes, consumosMega, percentuais):
    if (len(nomes) == len(consumosMega) == len(percentuais)):
        open('relatorio.txt','a')
        arquivo = open('relatorio.txt','w')
        for i in range(len(nomes)):
            arquivo.write(str(i)+' '+str(nomes[i])+' '+str(consumosMega[i])+'MB '+str(percentuais[i])+'%'+'\n')
        totalConsumo = sum(consumosMega)
        consumoMedio = calculaEspacoMedio(consumosMega)
        arquivo.write('Consumo Total: '+str(totalConsumo)+'\n'+'Consumo Medio: '+str(consumoMedio)+'\n')
        arquivo.close()
    else:
       print('Quantidade de Usuarios e Dados Não Conferem.')

nomes = organizaNomes(linhas)
consumos = organizaTamanhoConsumido(linhas)
consumosMega = transformaByteEmMega(consumos)
percentuais = calculaPercentuais(consumosMega)
criaRelatorio(nomes,consumosMega,percentuais)

{% endhighlight %}

Primeiro Abrimos o Arquivo e o colocamos dentro de uma lista.
Definimos funções para organizar e calcular tudo que o relatório precisa.
Criamos uma função que gera o relatório, passando como parametro nossas listas já tratadas.

Dúvidas ??? Utilize o Campo de Comentário abaixo ! Um Abraço !
