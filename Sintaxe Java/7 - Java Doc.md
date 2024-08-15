Uma das maiores características da linguagem **Java** é que desde suas primeiras versões tinhamos em nossas mãos uma documentação **rica** e **detalhada**dos recursos da linguagem.

Dentro do **Java** conseguimos gerar uma documentação com todos os recursos organizados por pacotes e classes bem específicas sem nem mesmo escrever **uma linha de código**.

## Tags

Mas e quais as informações que obtemos através de classes documentadas na linguagem ? **Java Documentation** é composto por*tags* que representam dados relevantes para a compreensão da proposta de uma classe e os conjunto de seus métodos e atributos conforme tabela *abaixo*: 

|Tag|Descrição|
|---|---|
|@autor|Autor / Criador|
|@version|Versão do recurso disponibilizado|
|@since|Versão / Data de início da disponibilização do recurso|
|@param|Descrição dos parâmetros dos métodos criados|
|@return|Definição do tipo de retorno de um método|
|@throws|Se o método lança alguma exceção|

Abaixo iremos ilustrar a classe Calculadora com um exemplo de documentação destacando as **tags** mais utilizadas.
```java
/**
* <h1>Calculadora</h1
* A Calculadora realiza operações matemáticas entre números inteiro
* <p>
* <b>Note:</b> Leia atenttamente a documentação destas classes
* para desfrutar dos recursos oferecidos pelo autor
*/ 
public class Calculadora{
	/**
	* Este método é utilizado para somar dois números inteiros
	* @param numeroUm este é o primeiro parâmetro do método
	* @param numeroDois este é o segundo parâmetro do método
	* @return int o resultado deste método é a soma de dois número
	*/
	public int somar(int numeroUm, int numeroDois){
		return numeroUm + numeroDois;
	}
}
```

## Tipos de comentários

### One Line
```java
// Olá, eu sou um comentário em uma única linha
```
### Mult Line 
```java
/* Olá,
* Eu sou um comentario
* que posso ser mais detalhado
* quando necessario
*/
```
### Documentation
```java
/**
* Esta duas estrelinhas acima
* é para identificar que você
* prentede elaborar um comentário
* a nível de documentação.
* Que incrível !!
```

> ⚠️ Um comentário não possui a finalidade de *amenizar* um algoritmo não estruturado conforme as convenções da linguagem.

```java
/*
 * Este método foi elaborado as pressas
 * por isso eu abrevei o nome das variáveis
 * mas olha, ele tem a finalidade somar ou  multiplicar
 * dois números
 * /
public int somaMultiplica (int n, int x, String m){
    int r = 0; // r é igual ao resultado
    if (m == "M"){ // M= multiplicação
        r= n * x;
    }else{
        // se não soma mesmo
        r = n + x
    }
    return r;
}
```

## Javadoc

**Javadoc** é um gerador de documentação criado pela **Sun Microsystems** para documentar a **API** dos programas em **Java**, a partir do código fonte. O resultado é expresso em **HTML**. É constituido, basicamente, por algumas marcações muitos simples inseridas nos comentários do programa.

Este sistema é o padrão de documentação de classes em Java, e muitas dos **IDEs** desta linguagem irão automaticamente gerar um Javadoc em **HTML**.

Criando nossa documentação no formato **HTML** para disponibilizar **via web.**
`// No terminal execute o comando abaixo`
```cmd
javadoc -encoding UTF-8 -docencoding ISO-8859-1  -d ../docs  src/*.java
```


