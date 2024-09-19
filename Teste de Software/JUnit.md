- Framework de Testes
- JUnit é uma framework de teste unitário para Java, amplamente utilizada para verificar se as partes individuais de um software funcionam conforme esperado. Ele permite que desenvolvedores escrevam e executem testes automatizados para garantir que métodos e classes funcionem corretamente. JUnit segue uma abordagem de *test-first* (primeiro o teste), incentivando a prática de TDD (Desenvolvimento Orientado a Testes).

Principais funcionalidades:
- **Anotações** como `@Test`, `@Before`, `@After`, que ajudam a estruturar e configurar os testes.
- **Assertivas** (`assertEquals`, `assertTrue`, etc.) para verificar resultados esperados.
- **Test Suites**, para agrupar vários testes em um só.

JUnit é integrado em muitas IDEs e ferramentas de build, como Maven e Gradle, facilitando a automação de testes.

Exemplo de uso do JUnit no Maven: 
```xml
<dependencies>  
    <dependency>  
    <groupId>org.junit.jupiter</groupId>  
    <artifactId>junit-jupiter-engine</artifactId>  
    <version>5.11.0</version>  
    <scope>test</scope>  
    </dependency>  
</dependencies>
```

## JUnit na prática:
**Código** a ser *testado* -->
```java
import java.time.LocalDate;  
import java.time.temporal.ChronoUnit;  
  
public class Pessoa {  
    private String nome;  
    private LocalDate dataNascimento;  
  
    public Pessoa(String nome, LocalDate dataNascimento) {  
        this.nome = nome;  
        this.dataNascimento = dataNascimento;  
    }  
  
    public String getNome() {  
        return nome;  
    }  
  
    public LocalDate getDataNascimento() {  
        return dataNascimento;  
    }  
  
    public int getIdade(){  
        return (int) ChronoUnit.YEARS.between(this.dataNascimento, LocalDate.now());  
    }  
  
    @Override  
    public String toString() {  
        return "Pessoa{" +  
                "nome='" + nome + '\'' +  
                ", dataNascimento=" + dataNascimento +  
                '}';  
    }  
}
```

**Exemplo básico** do *JUnit* dentro da pasta test:

```java
import org.junit.jupiter.api.Assertions;  
import org.junit.jupiter.api.Test;  
  
import java.time.LocalDate;  
  
public class PessoaTest {  
    @Test //Anotação Primordial para Testar
    void validarCalculodeIdade(){  
Pessoa pessoa = new Pessoa("irineu", LocalDate.of(2020,1,1));  // Criação de um cenário
Assertions.assertEquals(4,pessoa.getIdade());  
} // Assertions executa as validações
}
```

### After e Before
- *@BeforeAll* - Execução única no inicio do teste
- *@AfterAll* - Execução única no final do teste
- *@BeforeEach* - Antes de cada teste existente na classe
- *@AfterEach* - Depois de cada teste existente na classe

## Assumptions:

- Assumptions são condições que precisam ser verdadeiras para que um teste seja executado.
- Se a _assumption_ falhar, o teste é **ignorado** ao invés de ser marcado como falho.
- São úteis quando você deseja executar testes apenas em determinadas circunstâncias, como em um ambiente específico (por exemplo, sistema operacional ou configuração).
- Em JUnit, o método `Assume.assumeTrue()` é usado para definir essas condições.

### Testes condicionais:

- Testes condicionais, ou _conditional testing_, permitem que testes sejam executados com base em condições específicas.
- Eles são usados para evitar falhas em testes que não devem rodar em certos contextos, como em determinadas versões de software ou com configurações específicas.
- Também podem ser implementados com anotações específicas como `@EnabledOnOs` ou `@DisabledIfEnvironmentVariable` em JUnit 5.

### Testando Exceptions
No JUnit, você pode testar se uma exceção específica é lançada pelo seu código. Existem duas abordagens principais para isso:

### 1. **Usando `assertThrows()` (JUnit 5)**:
- A forma mais moderna de testar exceções em JUnit 5 é com o método `assertThrows()`. Ele verifica se uma exceção esperada é lançada quando o código dentro do teste é executado.

```java
@Test
void shouldThrowException() {
    Exception exception = assertThrows(IllegalArgumentException.class, () -> {
        // Código que deve lançar a exceção
        someMethodThatThrowsException();
    });

    // Verifica a mensagem da exceção (opcional)
    assertEquals("Mensagem de erro esperada", exception.getMessage());
}
```

### 2. **Usando a anotação `@Test(expected)` (JUnit 4)**:
- Em JUnit 4, você pode usar o parâmetro `expected` da anotação `@Test` para verificar se uma exceção específica foi lançada.

```java
@Test(expected = IllegalArgumentException.class)
public void shouldThrowException() {
    someMethodThatThrowsException();
}
```

### Ordenando Testes

#### Escolhendo a ordem do teste
```java
@TestMethodOrder(MethodOrderer.OrderAnnotation.class)
public class EscolhendoAOrdemDoTeste{
	@Order(1)
	@Test
	void validarFluxoA(){
		Assertions.assertTrue(true):
	}
	@Order(2)
	@Test
	void validarFluxoB(){
		Assertions.assertTrue(true):
	}
	@Order(3)
	@Test
	void validarFluxoA(){
		Assertions.assertTrue(true):
	}
}
```

#### Por ordem alfabética de acordo o nome 
```java
@TestMethodOrder(MethodOrderer.MethodName.class)
public class EscolhendoAOrdemDoTeste{
	@Test
	void validarFluxoA(){
		Assertions.assertTrue(true):
	}
	@Test
	void validarFluxoB(){
		Assertions.assertTrue(true):
	}
	@Test
	void validarFluxoA(){
		Assertions.assertTrue(true):
	}
}
```

#### Forma Aleatória:
```java
@TestMethodOrder(MethodOrderer.Random.class)
public class EscolhendoAOrdemDoTeste{
	@Test
	void validarFluxoA(){
		Assertions.assertTrue(true):
	}
	@Test
	void validarFluxoB(){
		Assertions.assertTrue(true):
	}
	@Test
	void validarFluxoA(){
		Assertions.assertTrue(true):
	}
}
```

### Por nomeação personalizada
```java
@TestMethodOrder(MethodOrderer.DisplayName.class)
public class EscolhendoAOrdemDoTeste{
	@DisplayName("A")
	@Test
	void validarFluxoA(){
		Assertions.assertTrue(true):
	}
	@DisplayName("B")
	@Test
	void validarFluxoB(){
		Assertions.assertTrue(true):
	}
	@DisplayName("C")
	@Test
	void validarFluxoA(){
		Assertions.assertTrue(true):
	}
}
```

### Recursos de Teste  dentro do Inteliij
[[https://www.jetbrains.com/help/idea/test-in-ide.html|Fórum  Jet Brains Sobre o Assunto]]

![[Pasted image 20240919165323.png]]

### Economize tempo automatizando 
- Ferramentas de cobertura de código
(Jacoco)
- Automatize a execução dos seus testes
