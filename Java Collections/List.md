
## List
- A interface `List` é uma coleção ordenada que permite a inclusão de elementos duplicados.
- É um dos tipos de coleção mais utilizados em Java, e as classes de implementação comuns são `ArrayList` e `LinkedList`.
- A `List` se assemelha a uma matriz com comprimento dinâmico, permitindo adicionar ou remover elementos.
- A interface `List` fornece métodos úteis para adicionar elementos em posições específicas, remover ou substituir elementos com base no índice e obter sublistas usando índices.
- A classe `Collections` fornece algoritmos úteis para manipulação de `List`, como ordenação (sort), embaralhamento (shuffle), reversão (reverse) e busca binária (binarySearch).

##### ArrayList: 
O ArrayList é uma implementação da interface List que armazena os elementos em uma estrutura de array redimensionável. Isso significa que ele pode crescer automaticamente à medida que novos elementos são adicionados. A principal vantagem do ArrayList é o acesso rápido aos elementos por meio de índices, o que permite recuperar um elemento específico de forma eficiente. No entanto, adicionar ou remover elementos no meio da lista pode ser mais lento, pois requer a realocação de elementos.

 ##### LinkedList: 
 O LinkedList é uma implementação da interface List que armazena os elementos em uma lista duplamente vinculada. Cada elemento contém referências para o elemento anterior e próximo na lista. A principal vantagem do LinkedList é a eficiência na adição ou remoção de elementos no início ou no final da lista, pois não é necessário realocar elementos. No entanto, o acesso aos elementos por meio de índices é mais lento, pois requer percorrer a lista até o elemento desejado.


 ##### _Vector_:
  O Vector é uma implementação antiga da interface List que é semelhante ao ArrayList, mas é sincronizada, ou seja, é thread-safe. Isso significa que várias threads podem manipular um objeto Vector ao mesmo tempo sem causar problemas de concorrência. No entanto, essa sincronização adiciona uma sobrecarga de desempenho, tornando o Vector menos eficiente do que o ArrayList em cenários em que a concorrência não é um problema. Por esse motivo, o uso do Vector é menos comum em aplicações modernas.

Crie uma classe chamada **"ListaTarefas"** que possui uma lista de tarefas como atributo. Cada tarefa é representada por uma classe chamada "Tarefa" que possui um atributo de descrição. Implemente os seguintes métodos:

- `adicionarTarefa(String descricao)`: Adiciona uma nova tarefa à lista com a descrição fornecida.
- `removerTarefa(String descricao)`: Remove uma tarefa da lista com base em sua descrição.
- `obterNumeroTotalTarefas()`: Retorna o número total de tarefas na lista.
- `obterDescricoesTarefas()`: Retorna uma lista contendo a descrição de todas as tarefas na lista.

## Criando Lista:

- ### Objeto:
```java
public class Tarefa{
		private String descrição;

	public void getDescricao(String descrição){
			return descrição
	}
	public void setDescricao(String descrição){
		this.descrição = descrição;
	}
		// Para que o GET retorne apenas a descrição, sem seu titulo e endereço de           mémoria junto.
	@Override
	public String toString(){
		return descrição;
	}
}
```

- ### Lista:
```java
import java.util.ArrayList;
import java.util.List;

//Criando Lista
public class ListaTarefa{
	ListaTarefa<Tarefa> tarefaList;
	public ListaTarefa(){
		this.tarefaList = new ArrayList<>();
	}
	//Métodos
	public void adicionarTarefa(String descrição){
			tarefaList.add(new Tarefa(descrição));
	}
	public void removerTarefa(String descrição){
		List<Tarefa> tarefasParaRemover = new ArrayList<>();
		for(Tarefa t : tarefaList){
			if(t.getDescricao().equalsIgnoreCase(descricao)){
				tarefasParaRemover.add(t);
			}
		}
	}
	public int obterNumeroTotalTarefas(){
		return tarefaList.size();
	}
	public void obterDescricoesTarefas(String descricao){
		System.out.println(tarefaList);
	}
}
```

- #### Testando Métodos e Funcionamento da Lista

```java
public static void main(String[] args){
	ListaTarefa List = new ListaTarefa
	 
	adicionarTarefa("Tarefa 1");
	removerTarefa("Tarefa 1");
	obterNumeroTotalTarefas();
	obterDescricoesTarefas();
	
}
```

### Exemplos práticos de como usar pesquisa em list no [[List]]

- 1 - Criando *Objeto* da nossa **Lista.**

```java
public class Livro{
	private String titulo;
	private String autor;
	private anoDePublicacao;

	public Livro(String titulo, String autor, int anoDePublicacao{
		this.titulo = titulo;
		this.autor = autor;
		this.anoDePublicacao = anoDePublicacao;
	}
	public String getTitulo(){
		return titulo;
	}
	public String getAutor(){
		return autor;
	} 
	public int getAnoDePublicacao(){
		return anoDePublicacao;
	}
}
```

### Criando Lista pra Manipular nossos Objetos:

```java
import java.util.ArrayLisy;
import java.util.List;

public class CatalogoLivros{
	List<Livro> catalogoLivros;
	public CatalogoLivros{
		this.catalogoLivros = new ArrayList<>();
	}
}
```


### Criando Métodos:

`adicionarLivro`:

```java
public void adicionarLivro(String titulo, String autor, int anoDePublicacao){
	this.catalogoLivros.add(new Livro(titulo,autor,anoDePublicacao))
}
```
`pesquisarPorAutor`:

```java
public List<Livro> pesquisarPorAutor(String autor){
	List<Livro> livrosPorAutor = new ArrayList<>();
	if(!catalogoLivros.isEmpty()){
		for(Livro l : catalogoLivros){
			if(l.getAutor().equalsIgnoreCase(autor)){
			livrosPorAutor.add(l);
			}
		}
	}
	return pesquisarPorAutor;
}
```

`pesquisarPorIntervalosAnos`:

```java
public List<Livro> pesquisarPorIntervalosAnos(int anoDePublicacao){
	List<Livro> livrosPorIntervalosAnos = new ArrayList<>();
	if(!catalogoLivros.isEmpty()){
		for(Livro l : catalogoLivros){
			if(l.getAnoDePublicacao.equalsIgnoreCase(anoDePublicacao)){
			livrosPorIntervalosAnos.add(l);
			}
		}
	}
	return livrosPorIntervalosAnos
}
```
# Exercícios 

## Fixando os Conhecimentos

**Exercícios:**

1. *Operações Básicas* com List
2. *Pesquisa* em List
3. *Ordenação* nas List

### 1. Operações Básicas com List


Crie uma classe chamada "CarrinhoDeCompras" que representa um carrinho de compras online. O carrinho deve ser implementado como uma lista de itens. Cada item é representado por uma classe chamada "Item" que possui atributos como nome, preço e quantidade. Implemente os seguintes métodos:

- `adicionarItem(String nome, double preco, int quantidade)`: Adiciona um item ao carrinho com o nome, preço e quantidade especificados.
- `removerItem(String nome)`: Remove um item do carrinho com base no seu nome.
- `calcularValorTotal()`: Calcula e retorna o valor total do carrinho, levando em consideração o preço e a quantidade de cada item.
- `exibirItens()`: Exibe todos os itens presentes no carrinho, mostrando seus nomes, preços e quantidades.

### 2.  Pesquisa em List

Crie uma classe chamada "SomaNumeros" que possui uma lista de números inteiros como atributo. Implemente os seguintes métodos:

- `adicionarNumero(int numero)`: Adiciona um número à lista de números.
- `calcularSoma()`: Calcula a soma de todos os números na lista e retorna o resultado.
- `encontrarMaiorNumero()`: Encontra o maior número na lista e retorna o valor.
- `encontrarMenorNumero()`: Encontra o menor número na lista e retorna o valor.

### 3. Ordenação em List

Crie uma classe chamada "OrdenacaoNumeros" que possui uma lista de números inteiros como atributo. Implemente os seguintes métodos:

- `adicionarNumero(int numero)`: Adiciona um número à lista.
- `ordenarAscendente()`: Ordena os números da lista em ordem ascendente usando a interface Comparable e a class Collections.
- `ordenarDescendente()`: Ordena os números da lista em ordem descendente usando um Comparable e a class Collections.
