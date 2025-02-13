## **boxing (autoboxing)**,*unboxing* e *casting*
### Tipos complexos de variáveis 

#### Tipos complexos (Wrappers)

| Primitivos | Wrappers  |
| ---------- | --------- |
| boolean    | Boolean   |
| byte       | Byte      |
| char       | Character |
| short      | Short     |
| int        | Integer   |
| long       | Long      |
| float      | Float     |
| double     | Double    |

## Porque usar Wrappers?
As classes **Wrappers** agrupam um valor primitivo dentro de um **Objeto**. E Ela fornece vários métodos auxiliares para converter para **String**,**Long**, e etc... Fazer um **casting**.

```java
public class Wrapper{
//Primitivo
	//private int codigo;
	private Integer codigo;
	//private long codigoMaior;
	private Long codigoMaior = 10000l;
	//private double valorDecimal;
	private Double valorDecimal;
	//private boolean status;
	private Boolean status;
	//private float valorDecimal;
	private Float valorDecimal;
	//private byte bi;
	private Byte bi;
	//private char letra;
	private Character letra;
	public static void main(String args[]){
		this.codigo.longValue();
	}
}
``` 

# Boxing (Autoboxing)
Boxing ou Autoboxing é a conversão de tipos primitivos para classes wrappers correspondente

Exemplos 
```java
Boolean a = true;
Byte b = 1;
Character c = 'c';
Short s = 1;
Integer i = 1;
Long l = 1L;
Float f = 1.0F;
Double d = 1.0;
``` 

