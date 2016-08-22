---
layout: post
title: "Python - 2ª Lista Iniciante"
excerpt: "Resolva Algoritmos Simples com Python."
tags:
 - Python
 - Exercicios
feature: http://i.imgur.com/Ds6S7lJ.png
comments: true
---

Olá amigos hoje venho trazer o restante da lista de Python !

Agora esta lista iniciante possui maiores laços de repetição ou decisão.
Espero que consigam compreender , e que sirva de exemplo para vocês !

E programar em Python é muito simples tente você também !

<figure>
	<img style="width:40%;height: auto;" src="{{ site.url }}/images/bancoPostagens/listapython1/snakepython.png">
</figure>

1) Faça um Programa que peça os três lados de um triângulo. O programa deverá informar se os valores podem ser um triângulo. Indique, caso os lados formem um triângulo, se o mesmo é: equilátero, isósceles ou escaleno:
{% highlight python %}
__author__ = 'Jhonatan Mark'
#Exercicio 01

a = int(input('Valor do Lado 1 : ').replace(',', '.'))
b = int(input('Valor do Lado 2 : ').replace(',', '.'))
c = int(input('Valor do Lado 3 : ').replace(',', '.'))
ok = False

if ((a + b) > c) == True and ((b + c) > a) == True and ((a + c) > b) == True:
    print('Triangulo Existe')
    ok = True
else:
    print('Não existe')
if ok:
    if (a == b) and (a == c) and (b == c):
        print('Triagulo Equilatero')
    elif (a == b) or (a == c) or (b == c):
        print('Triagulo Isosceles')
    elif (a != b) and (a != c) and (b != c):
        print('Triangulo Escaleno')
    else:
        print('Erro de Lógica')
else:
    print('Não é possivel calcular triangulo inexistente')
{% endhighlight %}

2) Determine se um ano é bissexto: ( Confesso que nessa eu apelei ! )
{% highlight python %}
__author__ = 'Jhonatan Mark'
#Exercicio 02

from calendar import isleap

print('----Determinar se Ano é bissexto----')

ano = int(input('Digitar o Ano a ser Verificado: '))
if isleap(ano):
    print('Bissexto')
else:
    print('Não é Bissexto')
{% endhighlight %}

3) João Papo-de-Pescador, homem de bem, comprou um microcomputador para controlar o rendimento diário de seu trabalho. Toda vez que ele traz um peso de peixes maior que o estabelecido pelo regulamento de pesca do estado de São Paulo (50 quilos) deve pagar uma multa de R$ 4,00 por quilo excedente. João precisa que você faça um programa que leia a variável peso (peso de peixes) e verifique se há excesso. Se houver, gravar na variável excesso e na variável multa o valor da multa que João deverá pagar. Caso contrário mostrar tais variáveis com o conteúdo ZERO:
{% highlight python %}
__author__ = 'Jhonatan Mark'
#Exercicio 03

print('----Multa do Pescado!----')

peso = int(input('Digitar o quantidade de KG pescado: '))
excesso = 0
multa = 0

if peso > 50:
    excesso = peso - 50
    multa = float(excesso x 4)
    print('Deverá pagar o valor de R${:.2f} de multa.'.format(multa))
elif peso < 0:
    print('Valor inserido Inválido.')
else:
    print('Excesso = %i'%excesso)
    print('Multa = %i'%multa)
{% endhighlight %}

4) Faça um Programa que leia três números e mostre o maior deles:

{% highlight python %}
__author__ = 'Jhonatan Mark'
#Exercicio 04

i=0
lista=[]
maior=0

for i in range(3):
    lista.append(float(input('Favor Inserir o %iº numero :'%(i+1)).replace(',','.')))

for i in range(len(lista)):
    if lista[i]>maior:
        maior=lista[i]
print('O Maior Numero é o : %.2f'%maior)
{% endhighlight %}

5) Faça um Programa que leia três números e mostre o maior e o menor deles:

{% highlight python %}
__author__ = 'Jhonatan Mark'
#Exercicio 05

i=0
lista=[]
maior=0
menor=0

for i in range(3):
    lista.append(float(input('Insira o %iº numero : '%(i+1)).replace(',', '.')))

if lista[0]>lista[1]:
    maior=lista[0]
    menor=lista[1]
else:
    maior=lista[1]
    menor=lista[0]

if maior<lista[2]:
    maior=lista[2]
if menor > lista[2]:
    menor=lista[2]

print('O maior numero da lista é %.2f' %maior)
print('O menor numero da lista é %.2f' %menor)
{% endhighlight %}

6) Faça um Programa que pergunte quanto você ganha por hora e o número de horas trabalhadas no mês. Calcule e mostre o total do seu salário no referido mês, sabendo-se que são descontados 11% para o Imposto de Renda, 8% para o INSS e 5% para o sindicato, faça um programa que nos dê o salário bruto, quanto pagou ao INSS, quanto pagou ao sindicato e o salário líquido. Observe que Salário Bruto - Descontos = Salário Líquido. Calcule os descontos e o salário líquido, conforme a tabela abaixo: a. + Salário Bruto : R$ b. - IR (11%) : R$ c. - INSS (8%) : R$ d. - Sindicato ( 5%) : R$ e. = Salário Liquido : R$
{% highlight python %}
__author__ = 'Jhonatan Mark'
#Exercicio 06

n1=float(input('Informe o ganho por hora: R$').replace(',','.'))
n2=int(input('Insira a Quantidade de Horas Trabalhadas: '))

salbruto = round(n1*n2,2)
ir = salbruto * 0.11
inss = salbruto * 0.08
sind = salbruto * 0.05
salliq = round(salbruto - (ir + inss + sind),2)

print('-------------------Calculo Salarial--------------------')
print('- Salário Bruto: R$%.2f'%salbruto)
print('----------------------Descontos------------------------')
print('- IR: R$%.2f'%ir)
print('- INSS: R$%.2f'%inss)
print('- Sindicato: R$%.2f'%sind)
print('------------------------Total--------------------------')
print('- Liquido: R$%.2f'%salliq)
print('--------------------------------------------------------')
{% endhighlight %}

7) Faça um programa para uma loja de tintas. O programa deverá pedir o tamanho em metros quadrados da área a ser pintada. Considere que a cobertura da tinta é de 1 litro para cada 3 metros quadrados e que a tinta é vendida em latas de 18 litros, que custam R$ 80,00. Informe ao usuário a quantidades de latas de tinta a serem compradas e o preço total. Obs. : somente são vendidos um número inteiro de latas:

{% highlight python %}
__author__ = 'Jhonatan Mark'
#Exercicio 07

n1=float(input('Informe a Area a ser Pintada em m²: ').replace(',','.'))
litnec=n1/3         #PADRAO DE NECESSIDADE
qtdlataf=18         #VALOR DE LITROS FIXO
qtdlata=0           #VALOR DE LITROS NECESSARIOS
valorlata=float(80) #PRECO LATA
lata=0
i=1
while qtdlata<litnec:
    lata=lata+i
    qtdlata=qtdlataf*lata

print('A quantidade de Latas de tintas necessárias é: %i'%lata)
print('O valor a ser pago é: R$%.2f'%(valorlata*lata))
{% endhighlight %}
