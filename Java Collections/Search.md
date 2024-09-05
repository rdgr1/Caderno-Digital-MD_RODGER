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