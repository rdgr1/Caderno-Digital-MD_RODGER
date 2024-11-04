## Anotações Utéis 
Anotações utéis para o tratamento de exceções -->
- `@ControllerAdvice`
	O *@ControllerAdvice* é uma anotação, para lidar com as exceções **globalmente**. utilizar em tudo que tiver `@RequestMapping` e `@Component`. 
- `@ExceptionHandler`
	O *@ExceptionHandler* é uma anotação, para tratar as exceções específicas e enviar as respostas personalizadas ao cliente. Ele segura as exceções, Muito Utilizado para erros como "**Nullable**","**Unique**" etc...

## Ná prática
#### Definindo Exceção para Erro Nulo
```java
public ProdutoModel save(ProdutoModel produtoModel){  
    if (produtoModel.getNome() == null)  
        throw new ProdutoNullException();  
    return  produtoRepository.save(produtoModel);  
}
```
#### Criando a Exceção Personalizada
```java
public class ProdutoNullException extends NullPointerException{
}
```
### Tratando a exceção globalmente e infomando com mensagem personalizada
`ProdutoControllerAdvice.class`
```java
//Tratando Globalmente na nossa Controller
@ControllerAdvice
public class ProdutoControllerAdvice extends ResponseEntityExceptionHandler{
	//Tratando a Exceção Personalizada
	@ExceptionHandler(ProdutoNullException.class)
	public ResponseEntity<Object> capturaErroNull(){
		//Utilizando Map pra Estrutura da Mensagem
		Map<String,Object> body = new HashMap<>();
		//Mensagem personalizada
		body.put("message":"Os campos não podem ser nulos!")
		return ResponseEntity.status(HttpStatus.BAD_REQUEST).body(body);
	}
}
```

### Definindo Exceção para erro no valor 
```java
public ProdutoModel save(ProdutoModel produtoModel) throws Exception{
	if(produtoModel.getNome == null){
		throws new ProdutoNullException();
	}
	else-if(produtoModel.getPreco > 0){
		throws new ProdutoPriceException();
	}
	return produtoRepository.save(produtoModel);
}
```
## Tratando a exceção especifica
```java
@ExceptionHandler(ProdutoPriceException.class)  
public ResponseEntity<Object> capturaErroPrice(){  
    Map<String,Object> body = new HashMap<>();  
    body.put("message","O valor do produto não pode ser negativo");  
        return ResponseEntity.status(HttpStatus.BAD_REQUEST).body(body); 
    }
```

