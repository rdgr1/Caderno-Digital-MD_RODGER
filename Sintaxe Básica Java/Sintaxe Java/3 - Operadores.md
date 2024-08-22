# Classificação dos operadores

## *Atribuição*

Representado pelo símbolo de igualdade `=`.

O operador de atribuição é utilizado para definir o valor inicial ou sobrescrever o valor de uma variável. em Java definimos um tipo, nome e opcionalmente atribuímos um valor a variavel através do operador de atribuição. 

```java
String nome = "RODGER";
int idade = "20";
double peso = 58.3;
char sexo = 'M';
boolean doadorOrgao = false;
Date dataNascimento = new Date();
```

## *Aritméticos*

O operador aritmético é utilizado para realizar operações matemáticas entre valores númericos, podendo se tornar ou não uma expressão mais complexa.

Os operadores aritméticos são:
 - `+`  **Adição**
 - `-`  **Subtração**
 - `*` **Multiplicação**
 - `/` **Divisão**

*Exemplos -->*
```java
//classe Operadores.java
double soma = 10.5 + 15.7;
int subtração = 113 - 25;
int multiplicacao = 20 * 7;
int divisao = 15 / 3;
int modulo = 18 % 3;
double resultado = (10 * 7) + (20/4);
```

>**ATENÇÃO!** O operador de adição `(+)`, quando utilizado em variáveis do tipo texto, realizará a **“concatenação de textos”**.

```java
//classe Operadores.java
String nomeCompleto = "LINGUAGEM" + "JAVA";
		
//qual o resultado das expressoes abaixo?
String concatenacao ="?"; 

concatenacao = 1+1+1+"1";

concatenacao = 1+"1"+1+1;

concatenacao = 1+"1"+1+"1";

concatenacao = "1"+1+1+1;

concatenacao = "1"+(1+1+1);
```

## *Unários*

Esses *operadores* são aplicados juntamente com um outro operador aritmético. Eles realizam alguns trabalhos básicos como **incrementar**,**decrementar**, **inverter valores** **numéricos** e **booleanos**.

- `(+)` **Operador unário de valor positivo** – números são positivos sem esse operador explicitamente;
    
- ``(-)`` **Operador unário de valor negativo** – nega um número ou expressão aritmética;
    
- ``(++)``**Operador unário de incremento de valor** – incrementa o valor em 1 unidade;
    
- ``(--)`` **Operador unário de decremento de valor** – decrementa o valor em 1 unidade;
    
- ``(!)`` **Operador unário lógico de negação** – nega o valor de uma expressão booleana;

## *Ternário

O Operador de Condição Ternária é uma forma resumida para definir uma condição e escolher por um dentre dois valores. Você deve pensar numa condição ternária como se fosse uma condição IF normal, porém, de uma forma em que toda a sua estrutura estará escrita numa única linha.

O operador ternário é representado pelos símbolos `?:` utilizados na seguinte estrutura de sintaxe:
`` <Expressão Condicional>`` ` `**?**`` ``<Caso condição seja true>`` ``**:**` ` ``<Caso condição seja false>

*Exemplos -->*

```java
// classe Operadores.java
int a, b;

a = 5;
b = 6;

/* EXEMPLO DE CONDICIONAL UTILIZANDO UMA ESTRUTURA IF/ELSE
if(a==b)
   resultado = "verdadeiro";
else
   resultado = "falso";
*/

//MESMA CONDICIONAL, MAS DESSA VEZ, UTILIZANDO O OPERADOR CONDICIONAL TERNÁRIO
String resultado = (a==b) ? "verdadeiro" : "false";

System.out.println(valor);
```

## *Relacionais*

Os operadores relacionais avaliam a relação entre duas variáveis ou expressões. Neste caso, mais precisamente, definem se o operando à esquerda é igual, diferente, menor, menor ou igual, maior ou maior ou igual ao da direita, retornando um valor booleano como resultado.

- `==` Quando desejamos verificar se uma variável é IGUAL A outra.
    
- `!=` Quando desejamos verificar se uma variável é DIFERENTE da outra.
    
- `>` Quando desejamos verificar se uma variável é MAIOR QUE a outra.
    
- `>=` Quando desejamos verificar se uma variável é MAIOR OU IGUAL a outra.
    
- `<` Quando desejamos verificar se uma variável é MENOR QUE outra.
    
- `<=` Quando desejamos verificar se uma variável é MENOR OU IGUAL a outra.

```java
//classe Operadores.java
int numero1 = 1;
int numero2 = 2;

if(numero1 > numero2)
	System.out.print("Numero 1 maior que numero 2");

if(numero1 < numero2)
	System.out.print("Numero 1 menor que numero 2");

if(numero1 >= numero2)
	System.out.print("Numero 1 maior ou igual que numero 2");

if(numero1 <= numero2)
	System.out.print("Numero 1 menor ou igual que numero 2");

if(numero1 != numero2)
	System.out.print("Numero 1 é diferente de numero 2");jav
```

>⚠️ Quando estiver mais familiarizado com linguagem, recomendamos se aprofundar no conceito de espaço em memória **Stack** versus **Heap**.

## *Lógicos* 

Os operadores lógicos representam o recurso que nos permite criar expressões lógicas maiores a partir da junção de duas ou mais expressões.

- `&&` Operador Lógico "E"
    
- `||` Operador Lógico "OU"

```java
// Operadores.java
boolean condicao1=true;

boolean condicao2=false;

/* Aqui estamos utilizando o operador lógico E para fazer a união de duas 
expressões. 
É como se estivesse escrito:
 "Se Condicao1 e Condicao2 forem verdadeiras, executar código"
*/

if(condicao1 && condicao2)
	System.out.print("Os dois valores precisam ser verdadeiros");;

//Se condicao1 OU condicao2 for verdadeira, executar código.
if(condicao1 || condicao2)
	System.out.print("Um dos valores precisa ser verdadeiro");
```


## *Expressões lógicas avançadas*

Nós acabamos de aprender que existem os operadores lógicos `&` (E) e `||` (OU), mas por quê no exemplo acima, foram ilustradas as condições:

``if (condicao1 ``**&&** ``condicao2) e if (condicao1 ``***||*** ``condicao2) ?``

>A duplicidade nos operadores lógicos é um recurso conhecido como _**Operador Abreviado**, isso quer que se a condição1 atender aos critérios não será necessário validar a condição2.

```java
// ComparacaoAvancada.java
int numero1 = 1;
int numero2 = 1;

if(numero1== 2 & numero2 ++ == 2 )
    System.out.println("As 2 condições são verdadeiras");

System.out.println("O numero 1 agora é " + numero1);
System.out.println("O numero 2 agora é " + numero2);

// Vamos mudar a linha 5 do código acima para: if(numero1== 2 && numero2 ++ == 2 )
```

[[4 - Métodos]]
