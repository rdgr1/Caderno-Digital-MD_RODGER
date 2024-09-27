Mockito é uma biblioteca popular em Java para testes unitários que permite criar objetos simulados (mocks) de classes. Ela facilita a criação de testes isolados, permitindo que você teste uma classe sem depender de suas dependências reais. Com o Mockito, você pode:

1. **Criar mocks**: Simular objetos e definir seu comportamento durante os testes.
2. **Verificar interações**: Checar se métodos foram chamados em mocks e quantas vezes.
3. **Estabelecer expectativas**: Definir como os mocks devem responder a chamadas de métodos específicas.

A biblioteca é especialmente útil em testes de código que interagem com serviços externos, como bancos de dados ou APIs, permitindo que você se concentre na lógica da classe sendo testada. É integrada facilmente com frameworks de teste como JUnit.

Exemplo no *pom.xml*:
#### Mockito Core
```xml
<!-- Mockito Core -->
<dependency>
    <groupId>org.mockito</groupId>
    <artifactId>mockito-core</artifactId>
    <version>5.13.0</version>
    <scope>test</scope>
</dependency>

```
#### Mockito JUnit Jupiter
```xml
<!-- Mockito JUnit Jupiter -->
<dependency>
    <groupId>org.mockito</groupId>
    <artifactId>mockito-junit-jupiter</artifactId>
    <version>5.13.0</version>
    <scope>test</scope>
</dependency>

```
### Exemplo de uso básico:
```java
@ExtendWith(MockitoExtension.class)
public class ListaTeste {
@Mock
private List<String> letras;

@Test
void adicionarItemNaLista(){
	//Mockando
	Mockito.when(letras.get(0).thenReturn("B"));
	//Utilizando o JUnit
	Assertions.assertEquals("B",letras.get(0));
}
}
```

## Mockando Objetos:

- Como mockar Objetos:

```java
@ExtendsWith(MockitoExtension.class)
public class CadastrarPessoaTeste{
	@Mock
	private ApiDosCorreios apiDosCorreios;
	@InjectMocks
	private CadastrarPessoa cadastrarPessoa;
	@Test
	void validarDadosDeCadastro(){
		cadastrarPessoa.cadastrarPessoa("Rodger","72132565",
LocalDate.now(), 45296265);
	}
}
```

## Espiando Objetos
### Porque espiar?
Para observar o comportamento de uma respectiva classe ou referência de uma classe.
##### Código de exemplo:
```java
//EnviarMensagem.java
public class EnviarMensagem{

private List<Mensagem> mensagens = new ArrayList<>();

public void adicionarMensagem(Mensagem mensagem) {
this.mensagens.add(mensagem);
}

public List<Mensagem> getMensagem(){
return Collections.unmodifiableList(this.mensagens);
	} 
}
```

```java
@ExtendWith(MockitoExtension.class)
public class EnviarMensagemTeste {

	@Spy
	private EnviarMensagem enviarMensagem;
	
}
```
## Capturando Objetos

```java
public class ServicoEmailTeste{

	@Mock 
	private PlataformaDeEnvio plataforma;
	@InjectMocks
	private ServicoEnvioEmail servico;
	@Captor
	private ArgumentCaptor<Email> captor;
	@Test
	void validarDadosEnviadosParaPlataforma(){
	String enderecoDeEmail = "email@example.com"
	String mensagem = "Olá mundo teste mensagem"
	boolean ehFormatoHtml = false;

	servico.enviaEmail(enderecoDeEmail,mensagem,  ehFormatoHtml);
	Mockito.verify(plataforma).enviarEmail(captor.capture());
Email emailCapturado = captor.getValue();

Assertions.assertEquals(enderecoDeEmail, emailCapturado.getEnderecoEmail());

Assertions.assertEquals(mensagem, emailCapturado.getMensagem());

Asseritons.assertEquals(Formato.TEXTO, emailCapturado.getFormato());
	}
}
```


## Manipulando Retornos 
```java
@ExtendWith(MockitoExtension.class)
public class CadastrarPessoaTeste {

    @Mock
    private ApiDosCorreios apiDosCorreios;

    @InjectMocks
    private CadastrarPessoa cadastrarPessoa;

    @Test
    void cadastrarPessoa() {

        DadosLocalizacao dadosLocalizacao = new DadosLocalizacao("MG", "Uberaba", "Rua Castro Alves", "Casa", "Nova Floresta");

        Mockito.when(apiDosCorreios.buscaDadosComBaseNoCep(anyString())).thenReturn(dadosLocalizacao);

        Pessoa jose = cadastrarPessoa.cadastrarPessoa("José", "28578527976", LocalDate.of(1947, 1, 15), "69317300");

        DadosLocalizacao enderecoJose = jose.getEndereco();
        assertEquals(dadosLocalizacao.getBairro(), enderecoJose.getBairro());
        assertEquals(dadosLocalizacao.getCidade(), enderecoJose.getCidade());
        assertEquals(dadosLocalizacao.getUf(), enderecoJose.getUf());
    }

    @Test
    void tentaCadastrarPessoaMasSistemaDosCorreiosFalha() {

        Mockito.when(apiDosCorreios.buscaDadosComBaseNoCep(anyString())).thenThrow(RuntimeException.class);

        Assertions.assertThrows(RuntimeException.class, () -> cadastrarPessoa.cadastrarPessoa("José", "28578527976", LocalDate.of(1947, 1, 15), "69317300"));
    }
```


## Mockando Métodos Estáticos

```java
@ExtendWith(MockitoExtension.class)
public class GeradorDeNumerosTeste {

    @Test
    void validaGeracaoListaDeNumeros() {
        MockedStatic<GeradorDeNumeros> gerador = Mockito.mockStatic(GeradorDeNumeros.class);

        List<Integer> integers = List.of(1, 2, 3, 4, 5, 6, 7, 8);

        gerador.when(() -> GeradorDeNumeros.geraNumerosAleatorios(anyInt()))
                .thenReturn(integers);

        Assertions.assertEquals(integers, GeradorDeNumeros.geraNumerosAleatorios(8));
}

    @Test
    void validaGeracaoListaDeNumerosSemInformarTamanho() {

        MockedStatic<GeradorDeNumeros> gerador = Mockito.mockStatic(GeradorDeNumeros.class);

        List<Integer> integers = List.of(10, 9, 8, 6);

        gerador.when(GeradorDeNumeros::geraNumerosAleatorios).thenReturn(integers);

        Assertions.assertEquals(integers, GeradorDeNumeros.geraNumerosAleatorios());
    }
}
```