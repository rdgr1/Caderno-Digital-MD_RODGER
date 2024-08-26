Uma coleção **(Collection)** é um estrutura de **dados** que serve pra agrupar muitos **elementos** em uma **única unidade**, estes elementos precisão ser *Objetos*.
	- Uma *collection* pode ter coleções **homogêneas e heterogêneas**, normalmente utilizamos coleções **homogêneas** de um tipo **especifico.**
	- O núcleo principal das *coleções* é formado pelas **interfaces** da figura abaixo, essas interfaces permitem **manipular** a coleção **independentes** do nível de *detalhe* que elas representam.
	- Temos **quatro grandes** tipos de *coleções*: `List` (Lista), `Set`(Conjunto), `Queue`(Fila) e `Map`(Mapa) a partir dessas **interfaces**, temos muitas **subclasses concretas** que implementam varias *formas* diferentes de se trabalhar com cada *coleção*.

![[JavaCollection.png]]

- Todas as **interfaces e classes** são encontradas dentro do pacote (package) **java.util**.
- Embora a interface **Map** não seja filha direta da interface **Collection**, ela também é 
  considerada uma *coleção* devido à sua **função**.
	![[collection-framework-methods.png]]

[[https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/Collection.html| Method Summary Collection]]

## Generic Type

- Um tipo genérico é uma classe genérica ou uma interface que é parametrizada em relação a tipos.
- A classe `Box` a seguir será modificada para demonstrar o conceito:

```java
public class Box {
    private Object object;

    public void set(Object object) { this.object = object; }
    public Object get() { return object; }
}
```

- O símbolo `<>` é chamado de "diamond" ou "diamond operator" foi um recurso introduzido no Java 7 e é usado no contexto de tipos genéricos em Java para inferir automaticamente o tipo com base no contexto.
- Para atualizar a classe `Box` para usar generics, você cria uma declaração de tipo genérico alterando o código `public class Box` para `public class Box<T>`.
- Isso introduz a variável de tipo, `T`, que pode ser usada em qualquer lugar dentro da classe:

```java
/**
Versão genérica da classe Box.
@param <T> o tipo do valor sendo armazenado
*/
public class Box<T> {
	// T representa "Type" (tipo)
    private T t;

    public void set(T t) { this.t = t; }
    public T get() { return t; }
}
```

- Como você pode ver, todas as ocorrências de **Object** são substituídas por **T**.
- Uma **variável** de *tipo* pode ser qualquer tipo não *primitivo* que você especificar: qualquer tipo de classe, qualquer tipo de interface, qualquer tipo de **array** ou até mesmo outra variável de **tipo**.
- Essa mesma técnica pode ser aplicada para criar interfaces genérica.
- Os nomes de parâmetros de tipo mais comumente usados são:
    - **E** - Elemento (usado extensivamente pelo **Java Collections Framework**)
    - **K** - Chave
    - **N** - Número
    - **T** - Tipo
    - **V** - Valor
    - **S, U, V, etc.** - 2º, 3º, 4º tipos

## Comparable e Comparator

- `Comparable` fornece uma única sequência de ordenação. Em outras palavras, podemos ordenar a coleção com base em um único elemento, como id, nome e preço.
- `Comparable` afeta a classe original, ou seja, a classe atual é modificada.
- `Comparable` fornece o método `compareTo()` para ordenar elementos.
- `Comparable` está presente no pacote `java.lang`.
- Podemos ordenar os elementos da lista do tipo `Comparable` usando o método `Collections.sort(List)`.

## Comparator

- O `Comparator` fornece o método `compare()` para ordenar elementos.
- O `Comparator` fornece múltiplas sequências de ordenação. Em outras palavras, podemos ordenar a coleção com base em múltiplos elementos, como id, nome, preço, etc.
- O `Comparator` não afeta a classe original, ou seja, a classe atual não é modificada.
- Um `Comparator` está presente no pacote `java.util`.
- Podemos ordenar os elementos da lista do tipo `Comparator` usando o método `Collections.sort(List, Comparator)`.

## Collections

- A classe `Collections` é uma classe utilitária do Java para operações comuns em coleções.
- Ela fornece métodos para ordenação, busca, manipulação e sincronização de coleções.
- O método `sort()` é usado para ordenar uma lista em ordem ascendente.
- O método `sort()` em conjunto com `Collections.reverseOrder()` permite ordenar em ordem descendente.

```java
package main.java.comparableXcomparator;

import java.util.Comparator;

// Uma classe 'Livro' que implementa Comparable
class Livro implements Comparable<Livro> {
	private String titulo;
	private String autor;
	private int ano;

	// Construtor
	public Livro(String ti, String au, int an) {
		this.titulo = ti;
		this.autor = au;
		this.ano = an;
	}

	// Usado para ordenar livros por ano
	public int compareTo(Livro l) {
		return titulo.compareTo(l.titulo);
	}

	// Métodos getters para acessar os dados privados
	public String getTitulo() {
		return titulo;
	}

	public String getAutor() {
		return autor;
	}

	public int getAno() {
		return ano;
	}
}

// Classe para comparar Livro por autor
class CompararAutor implements Comparator<Livro> {
  @Override
  public int compare(Livro l1, Livro l2) {
		return l1.getAutor().compareTo(l2.getAutor());
	}
}

// Classe para comparar Livro por ano
class CompararAno implements Comparator<Livro> {
  @Override
  public int compare(Livro l1, Livro l2) {
		if (l1.getAno() < l2.getAno())
			return -1;
		if (l1.getAno() > l2.getAno())
			return 1;
		else
			return 0;
	}
}

class CompararAnoAutorTitulo implements Comparator<Livro> {
	@Override
	public int compare(Livro l1, Livro l2) {
		int ano = Integer.compare(l1.getAno(), l2.getAno());
		if (ano != 0)
			return ano;
		int autor = l1.getAutor().compareTo(l2.getAutor());
		if (autor != 0)
			return autor;
		return l1.getTitulo().compareTo(l2.getTitulo());
	}
}
```
