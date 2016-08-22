---
layout: post
title: "Python - Lista Iniciante"
excerpt: "Como resolver simples algoritmos em Python."
tags:
 - Python
 - Exercicios
feature: http://i.imgur.com/Ds6S7lJ.png
comments: true
---

Olá amigos, em meu antigo blog possuia algumas postagens que gostaria de portar pra esta nova plataforma, e uma delas é esta postagens sobre python e alguns exercícios resolvidos com esta linguagem.

De acordo com **[PyScience](http://pyscience-brasil.wikidot.com/python:python-oq-e-pq)**:

>
Python é uma linguagem de programação criada por Guido van Rossum em 1991. Os objetivos do projeto da linguagem eram: produtividade e legibilidade. Em outras palavras, Python é uma linguagem que foi criada para produzir código bom e fácil de manter de maneira rápida.

O que mostrarei abaixo são códigos de algoritmos básicos que se quiserem compare com outras linguagens e verão a transparência e inteligibilidade que é o Python.

Todos os exercícios abaixo são algoritmos simples! Não sabe o que é **[Algoritmo](https://pt.wikipedia.org/wiki/Algoritmo)** ?

>
    algoritmo
    substantivo masculino
        1.
        mat sequência finita de regras, raciocínios ou operações que, aplicada a um número finito de dados, permite solucionar classes semelhantes de problemas.
        2.
        inf conjunto das regras e procedimentos lógicos perfeitamente definidos que levam à solução de um problema em um número finito de etapas.

1) Faça um programa que peça dois números inteiros e imprima a soma de dois números:

{% highlight python %}
__author__ = 'Jhonatan Mark'
#Exercicio 01

print('----Soma de Inteiros----')
n1=int(input('Primeiro Numero: '))
n2=int(input('Segundo Numero: '))

print(n1+n2)
{% endhighlight %}

2) Escreva um programa que leia um valor em metros e o exiba convertido em milímetros, aceitar virgulas na entrada do usuário:

{% highlight python %}
__author__ = 'Jhonatan Mark'
#Exercicio 02

print('----Conversor de Metros para Milimetros-----')

n1=float(input('Valor em Metros: ').replace(',','.'))
n2=n1*1000
print('O valor em é : %.2f milimetros '%n2)
{% endhighlight %}

3) Escreva um programa que leia a quantidade de dias, horas, minutos e segundos do usuário. Calcule o total em segundos:

{% highlight python %}
__author__ = 'Jhonatan Mark'
#Exercicio 03

print('----Calculo de Tempo em Segundos----')
n1=int(input('Quantos Dias: '))
n2=int(input('Quantas Horas: '))
n3=int(input('Quantos minutos: '))

segs=(n3*60)+(n2*3600)+(n1*86400)
print(segs)
{% endhighlight %}

4) Faça um programa que calcule o aumento de um salário. Ele deve solicitar o valor do salário e a porcentagem do aumento. Exiba o valor do aumento e do novo salário:

{% highlight python %}
__author__ = 'Jhonatan Mark'
#Exercicio 04

print('----Calculo de Percentual de Aumento----')

sal=float(input('Insira o Salário Inicial: ').replace(',','.'))
perc=float(input('Insira o percentual de Aumento: ').replace(',','.'))

novosal=sal+(sal*(perc/100))
print('O Salário Reajustado é R$ %.2f'%novosal)
{% endhighlight %}

5) Solicite o preço de uma mercadoria e o percentual de desconto. Exiba o valor do desconto e o preço a pagar:

{% highlight python %}
__author__ = 'Jhonatan Mark'
#Exercicio 05

print('----Calculo de Percentual de Desconto----')

mercp=float(input('Insira o Preço da Mercadoria: ').replace(',','.'))
perc=float(input('Insira o percentual de Desconto: ').replace(',','.'))

valdesc=mercp*(perc/100)

print('O valor de desconto da mercadoria é R$ %.2f'%valdesc)

novoprec=mercp-valdesc
print('O valor da mercadoria com desconto é R$ %.2f'%novoprec)
{% endhighlight %}

6) Calcule o tempo de uma viagem de carro. Pergunte a distância a percorrer e a velocidade média esperada para a viagem:

{% highlight python %}
__author__ = 'Jhonatan Mark'
#Exercicio 06

print('----Calculo Tempo de Viagem de Automovel----')

dist = float(input('Insira a Distancia a ser Percorrida: ').replace(',', '.'))
vel = float(input('Insira a velocidade media: ').replace(',', '.'))

tempo = dist / vel
min = (round(tempo % 1, 2))
min = (min * 60)

print('O tempo esperado da viagem é de {:.0f} horas e {:.0f} minutos'.format(tempo,min))
{% endhighlight %}

7) Converta uma temperatura digitada em Celsius para Fahrenheit. F = 9*C/5 + 32. 8) Faça agora o contrário, de Fahrenheit para Celsius.

{% highlight python %}
__author__ = 'Jhonatan Mark'
#Exercicio 07
#F = 9*C/5 + 32

print('----Conversor Temperatura Celsius to Fahrenheit----')

c = float(input('Insira a Temperatura em Celsius: ').replace(',', '.'))
f = (9*(c/5)+32)

print('Fahrenheit : {:.2f}'.format(f))

##Exercicio 08
##°C = (°F − 32) / 1,8

print('----Conversor Temperatura Fahrenheit to Celsius----')

f = float(input('Insira a Temperatura em Fahrenheit: ').replace(',', '.'))
c = ((f-32)/1.8)

print('Celsius : {:.2f}'.format(c))
{% endhighlight %}

9) Escreva um programa que pergunte a quantidade de km percorridos por um carro alugado pelo usuário, assim como a quantidade de dias pelos quais o carro foi alugado. Calcule o preço a pagar, sabendo que o carro custa R$ 60,00 por dia e R$ 0,15 por km rodado:

{% highlight python %}
__author__ = 'Jhonatan Mark'
#Exercicio 09

print('----Calculadora de Dias de Carro Alugado----')

d = int(input('Quantos Dias o Carro Ficou Alugado: '))
k = float(input('Quantos Km foram rodados: ').replace(',','.'))

paga=(d*60)+(k*0.15)

print('O valor a ser pago é R${:.2f} devido a {:.0f} dias de aluguel e {:.0f} Km rodados'.format(paga,d,k))
{% endhighlight %}

10) Escreva um programa para calcular a redução do tempo de vida de um fumante. Pergunte a quantidade de cigarros fumados por dia e quantos anos ele já fumou. Considere que um fumante perde 10 minutos de vida a cada cigarro, calcule quantos dias de vida um fumante perderá. Exiba o total de dias:

{% highlight python %}
__author__ = 'Jhonatan Mark'
#Exercicio 10

qtde = int(input('Informe Quantos Cigarros você fuma por dia: '))
anos = int(input('Informe por quantos anos você fuma: '))

soma = qtde*(anos*365)
minutos = soma*10

subtrai = (minutos/60)/24

print('Voce tem %.2f dias a menos de vida' %subtrai)
{% endhighlight %}

11) Sabendo que str( ) converte valores numéricos para string, calcule quantos dígitos há em 2 elevado a um milhão.

{% highlight python %}
__author__ = 'Jhonatan Mark'
#Exercicio 11

n=str(int(2**1000000))
print('A quantidade de digitos é: %s' %len(n))
{% endhighlight %}
