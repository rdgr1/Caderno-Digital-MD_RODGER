## Tipos Primitivos:
#### Os oito tipos primitivos em Java são:
`int`,`byte`,`short`,`long`,`float`,`double` ,`boolean` e `char`- esses tipos não são
considerados objetos, e portanto representam valores brutos.
Eles são armazenados diretamente na pilha de memória.
Tabela de Tipos Primitivos e seus valores:

| Tipo  | Memória | Valor Mínimo               | Valor Máximo              |
| ----- | ------- | -------------------------- | ------------------------- |
| byte  | 1 byte  | -128                       | 127                       |
| short | 2 byte  | -32.768                    | 32.767                    |
| int   | 4 bytes | -2.147.483.648             | 2.147.483.647             |
| long  | 8 bytes | -9.223.372.036.854.775.808 | 9.223.372.036.854.775.807 |

Os tipos primitivos que podem conter partes fracionárias podem ser representados por dois tipos:

|Tipo|Memória|Mínimo|Máximo|Precisão|
|---|---|---|---|---|
|float|4 bytes|-3,4028E + 38|3,4028E + 38|6 – 7 dígitos|
|double|8 bytes|-1,7976E + 308|1,7976E + 308|15 dígitos|

Apesar de o tipo **float** ocupar metade da memória consumida do que um tipo double, ele é menos utilizado. Ele sofre de uma limitação que compromete seu uso em determinadas situações: somente mantém uma precisão decimal entre 6 e 7 dígitos.

Atualmente, com os computadores modernos, se tornou desnecessário utilizar os tipos `short` e `byte`, pois não precisamos nos preocupar tanto assim com o espaço de memória reduzido.

Da mesma forma, dificilmente utilizaremos o tipo `long`, pois não é tão comum trabalharmos com valores tão grandes.

Portanto, para representar números, na grande maioria das vezes utilizaremos o tipo `int` para representar números inteiros ou `double` para representar números fracionados.

#### *Por convenção de código usaremos quase sempre:*
 `int` e `double`.

## Declaração de Variáveis:

***Variável*** é uma identificação de um espaço em memória utilizado pelo nosso programa.
Seguindo as convenções em linguagem de programação, toda variável é composta por: `tipo de dados`+`identificação`+`valor atribuido.

***Estrutura Padrão:***

``<Tipo> <nomeVariavel> <atribuiçãoDeValorOpcional>``

*Exemplos -->* 
```java
int idade; //Tipo "int", nome "idade", com nenhum valor atribuído.
int anoFabricacao - 2021; //Tipo "int", nome "anoFabricacao", valor atribuído "2021".
double salarioMinimo = 2.500; //Tipo "double", nome "salarioMinimo", valor "2500".
```

*Exemplos Específicos -->*
```java
public class TipoDados{
		public static void main(String[] args){
		byte idade = 123;
		short ano = 2021;
		int cep = 21070333; // não pode começar com zero
		long cpf = 98765432109L; // não pode começar com zero
		float pi = 3.14F;
		double salario = 1275.33;
		}
}
```

Os tipos `float` e`long` precisam de suas iniciais no final para serem identificados com tais.

## Variáveis X Constantes:

Uma **Variável** é uma área de memória, associada a um nome, que pode armazenar valores de um determinado tipo, Um tipo de dado define um conjunto de valores e conjunto de operações. 

No **Java** utilizamos identificadores que representam uma ***referência (ponteiro)*** a um valor de memória, e esta referência pode ser redirecionada a outro valor, sendo portanto esta a causa do nome **"variável"**, pois o valor pode variar.

Já as ***Constantes*** são valores armazenados em memória que não podem ser modificados depois de declarados. em Java, esses valores são representados pela palavra reservada ``final``, seguida do tipo.

Por convenção, ***Constantes*** são sempre escritas em *CAIXA ALTA* após a representação `final` .

*Exemplo -->*

```java
public class ExemploVariavel{
		public static void main(String[] args){
		// Declaração de variável
		int numero = 7;
		// Alterando o valor da variável
		numero = 10;
		// Printando
		System.out.println(numero)
		// Declaração de uma CONSTANTE
		final double VALOR_DE_PI = 3.14;
		// Caso tentemos alterar o valor da constante
		VALOR_DE_PI = 3.14; // O compilador apresenterá erro de                     compilação!
			}
}
```
[[3 - Operadores]]
