## Progamação Orientada a Objetos

### Conceito: 
POO é um **paradigma de progamação** baseado no conceito de "**objetos**", que podem conter dados na forma de **campos**, também conhecidos como atributos, e códigos, na forma de **procedimentos**, também conhecidos como *métodos.*

Oque precisamos entender, é que cada vez mais as linguagens se adequam ao cenário real, proporcionando assim que o programador desenvolva algoritimos mais próximos de fluxos comportamentais, logo tudo ao nosso redor é representado como **Objeto.**

> Enquanto a progamação estruturada é voltada a procedimentos e funções definidas pelo usuário, a progamação orientada a objetos é voltada a conceitos como o de classes e objetos.

### Classes :
Toda a estrutura do código na linguagem Java é distribuído em arquivos com extensão **.java** denominados de **classe.**

As classes existentes em nosso projeto serão composta por:

**Identificador**, **Características** e **Comportamentos.**

- **Classe** (class): A estrutura e ou representação que direciona a criação dos objetos de mesmo tipo.
- **Identificador** (identity): Propósito existencial aos objetos que serão criados. 
- **Comportamentos**(states): Também conhecido como **atributos** ou **propriedades**, é toda informação que representa o estado do objeto.

Algumas convenções, as nossas classes são classificadas como:

- **Classe de modelo (model)**: classes que representem estrutura de domínio da aplicação, exemplo: Cliente, Pedido, Nota Fiscal e etc.

- **Classe de serviço (service)**: classes que contém regras de negócio e validação de nosso sistema.

- **Classe de repositório (repository)**: classes que contém uma integração com banco de dados.

- **Classe de controle (controller)**: classes que possuem a finalidade de disponibilizar alguma comunicação externa à nossa aplicação, tipo http web ou webservices.

- **Classe utilitária (util)**: classe que contém recursos comuns à toda nossa aplicação.

![[Pasted image 20240822133124.png]]

## Pacotes 

### Nomenclatura:

Vamos imaginar que sua empresa se chama **Power Soft** e ela está desenvolvendo softwares comercial, governamental, e um software livre ou de código aberto. 
- **Comercial** : com.powersoft
- **Governamental** : gov.powersoft
- **Código** **aberto**: org.powersoft

Podemos organizar ainda mais um pouco as nossas classes mediante a proposta de sua existência:

- **model** : Classes que representam a camada e modelo da aplicação :
  Cliente, Pedido, NotaFiscal, Usuario
  - **repository** : Classes ou interfaces que possuem finalidade de interagir com tabelas no banco de dados : ClientRepository
  - **service**: Classes que contém regras de negócio do sistema : ClientService
   possui o método validar o CPF do cliente cadastrado
   - **controller**: Classes que possuem a finalidade de disponibilizar os nossos recursos da aplicação para outras aplicações via padrão HTTP
   - **view**: Classes que possuem alguma interação com interface gráfica acessada pelo usuário

## Visibilidade de Recursos

### Conceito
Em Java, a visibilidade controla o acesso a atributos e métodos de uma classe. Isso é definido pelos modificadores de acesso, que ajudam a proteger e gerenciar como os membros da classe são acessados.

### Modificadores de Acesso

1. **`public`**
   - **Acesso:** Qualquer classe pode acessar.
   - **Uso:** Atributos e métodos que precisam ser acessíveis globalmente.
   - **Exemplo:**
     ```java
     public class Example {
         public int value;
         public void display() { ... }
     }
     ```

2. **`protected`**
   - **Acesso:** Classes no mesmo pacote e subclasses em outros pacotes podem acessar.
   - **Uso:** Atributos e métodos que precisam ser acessíveis em subclasses.
   - **Exemplo:**
     ```java
     public class Example {
         protected int value;
         protected void display() { ... }
     }
     ```

3. **`default` (sem modificador)**
   - **Acesso:** Apenas classes no mesmo pacote podem acessar.
   - **Uso:** Atributos e métodos que devem ser restritos ao pacote.
   - **Exemplo:**
     ```java
     class Example {
         int value; // default
         void display() { ... } // default
     }
     ```

4. **`private`**
   - **Acesso:** Apenas a própria classe pode acessar.
   - **Uso:** Atributos e métodos que devem ser encapsulados e não expostos externamente.
   - **Exemplo:**
     ```java
     public class Example {
         private int value;
         private void display() { ... }
         public void setValue(int v) { value = v; }
     }
     ```

### Encapsulamento
O encapsulamento usa a visibilidade para proteger os dados e expor apenas o necessário através de métodos públicos.

- **Exemplo de Encapsulamento:**
  ```java
  public class Person {
      private String name;
      private int age;
      
      public String getName() { return name; }
      public void setName(String name) { this.name = name; }
      public int getAge() { return age; }
      public void setAge(int age) { if (age > 0) this.age = age; }
  }
```


## Getter and Setters

Seguindo a convensão Java Beans

Os métodos "Getters" e "Setters" são utilizados para buscar valores de atributos ou definir novos valores de atributos de instâncias de classes.

O método **Getter** retorna o valor do atributo especificado.

O método **Setter** define outro novo valor para o atributo especificado.

Vemos o código abaixo da criação de um objeto Aluno com nome e idade:


```java
/arquivo Aluno.java
public class Aluno {
	String nome;
	int idade;
}

//arquivo Escola.java
public class Escola {
	public static void main(String[] args) {
		Aluno felipe = new Aluno();
		felipe.nome="Felipe";
		felipe.idade = 8;
		
		System.out.println("O aluno " + felipe.nome + " tem " + felipe.idade + "           anos ");
		//RESULTADO NO CONSOLE
		//O aluno Felipe tem 8 anos 		
	}
}
```

Seguindo a convenção Java Beans, uma classe que contém esta estrutura de estados deverá seguir as regras abaixo:

- Os atributos precisam ter o modificador de acesso `private`. Ex.: private String nome;

- Como agora os atributos estarão somente a nível de classe, precisaremos dos métodos **get**X e **set**X, Ex.: getNome() e setNome(String novoNome);

- O método **get** é responsável por obter o valor atual do atributo, logo ele precisa ser `public` retornar um tipo correspondente ao valor, Ex.: `public String getNome() {}`;

- O método **set** é responsável por definir ou modificador o valor de um atributo em um objeto, logo ele também precisa ser `public`, receber um parâmetro do mesmo tipo da variável mas não retorna nenhum valor void. Ex.: `public void setNome(String newNome)`;

```java
//arquivo Aluno.java
public class Aluno {
	private String nome;
	private int idade;
	
	public String getNome() {
		return nome;
	}
	public void setNome(String newNome) {
		nome = newNome;
	}
	public int getIdade() {
		return idade;
	}
	public void setIdade(int newIdade) {
		this.idade = newIdade;
	}
}
//arquivo Escola.java
public class Escola {
	public static void main(String[] args) {
		Aluno felipe = new Aluno();
		felipe.setNome("Felipe");
		felipe.setIdade(8);
		
		System.out.println("O aluno " + felipe.getNome() + " tem " + felipe.getIdade() + " anos ");	
	}
}
```

A proposta do código acima é a mesma que o código anterior, a diferença é que adotamos a convenção Java Beans para definir e obter as características dos nossos objetos.

Uso do `this` no método `set`. É muito comum vermos nossos métodos de definição ter a seguinte sintaxe:

```java
//arquivo Aluno.java
private String nome;

public void setNome(String nome) {
	this.nome = nome;
}
```

## Construtores

Sabemos que para criar um objeto na linguagem Java utilizamos a seguinte estrutura de código:

```java
Classe novoObjeto = new Classe();
```

Desta forma será criado um novo objeto na memória, este recurso também é conhecido como instanciar um novo objeto.

Muitas das vezes já queremos que na criação (instanciação) de um objeto, a linguagem já solicite para quem for criar este novo objeto defina algumas propriedades essenciais. Abaixo iremos ilustrar uma classe Pessoa onde a mesma terá os atributos: Nome, CPF, Endereço.

```java
public class Pessoa {
	private String nome;
	private String cpf;
	private String endereco;
	
	public String getNome() {
		return nome;
	}
	public String getCpf() {
		return cpf;
	}
	public String getEndereco() {
		return endereco;
	}
	public void setEndereco(String endereco) {
		this.endereco = endereco;
	}
	//...
	//setters de nome e cpf ?
}
```

Criaremos uma Pessoa mas como não temos o setter para nome e cpf, este objeto não tem como receber estes valores.

```java
public class SistemaCadastro {
	public static void main(String[] args) {
		//criamos uma pessoa no sistema
		Pessoa marcos = new Pessoa();
		
		//definimos o endereço de marcos
		marcos.setEndereco("RUA DAS MARIAS");
		
		//e como definir o nome e cpf do marcos ?
		
		//imprimindo o marcos sem o nome e cpf
		
		System.out.println(marcos.getNome() + "-" + marcos.getCpf());
	}
}
```

Entrando em cena o construtor para criar nossos objetos já com valores requeridos na momento da criação\instanciação (`new`).

```java
public class Pessoa {
	private String nome;
	private String cpf;
	private String endereco;
	
	// método construtor
	// o nome deverá ser igual ao nome da classe
	public Pessoa (String cpf, String nome) {
		this.cpf = cpf;
		this.nome = nome;
	}
	
	//...
	//getters
	//setters
}
```

Alterando o nosso sistema para agora criar o objeto com informações já requeridas conforme definição da ordem dos parâmetros do construtor.

```java
public class SistemaCadastro {
	public static void main(String[] args) {
		//criamos uma pessoa no sistema
		Pessoa marcos = new Pessoa("06724506716","MARCOS SILVA");
		
		//continua ...
		
	}
}
```

## Enums 

Enum é um tipo especial de classe onde os objetos são previamente criados, imutáveis e disponíveis por toda aplicação.

Usamos Enum quando o nosso modelo de negócio contém objetos de mesmo contexto que já existem de pré-estabelecida com a certeza de não haver tanta alteração de valores.

**Exemplos:**

**Grau de Escolaridade**: Analfabeto, Fundamental, Médio, Superior

**Estado Civil**: Solteiro, Casado, Divorciado, Viúvo

**Estados Brasileiros**: São Paulo, Rio de Janeiro, Piauí, Maranhão.

Não confunda uma lista de constantes com enum.

Enquanto que uma constante é uma variável de tipo com valor imutável, um enum é um conjunto de objetos já pré-definidos na aplicação.

Como um enum é um conjunto de objetos, logo, estes objetos podem conter atributos e métodos. Veja o exemplo de um enum para disponibilizar os quatro estados brasileiros citados acima, contendo informações de: Nome, Sigla e um método que pega o nome do de cada estado e já retorna para tudo maiúsculo.

```java
// Criando o enum EstadoBrasileiro para ser usado em toda a aplicação.
public enum EstadoBrasileiro {
	SAO_PAULO ("SP","São Paulo"),
	RIO_JANEIRO ("RJ", "Rio de Janeiro"),
	PIAUI ("PI", "Piauí"),
	MARANHAO ("MA","Maranhão") ;
	
	private String nome;
	private String sigla;
	
	private EstadoBrasileiro(String sigla, String nome) {
		this.sigla = sigla;
		this.nome = nome;
	}
	public String getSigla() {
		return sigla;
	}
	public String getNome() {
		return nome;
	}
	public String getNomeMaiusculo() {
		return nome.toUpperCase();
	}
	
}
```

Boas práticas para criar objetos Enum

- As opções (objetos) devem ser descritos em caixa alta separados por underline (**_**_),_ ex.: OPCAO_UM, OPCAO_DOIS

- Após as opções deve-se encerrar com ponto e vírgula (**;**)

- Um enum é como uma classe, logo poderá ter atributos e métodos tranquilamente

- Os valores dos atributos devem já ser definidos após cada opção dentro de parênteses como se fosse um `new`

- O construtor deve ser privado

- Não é comum um enum possuir o recurso `setter` (alteração de propriedade), somente os métodos `getters` correspondentes.

Agora **NÃO** precisaremos criar objetos que representam cada estado toda vez que precisarmos destas informações, basta usar o **enum** acima e escolher a opção (objeto) já pré-definido em qualquer parte do nosso sistema.

```java
// qualquer classe do sistema poderá obter os objetos de EstadoBrasileiro
public class SistemaIbge {
	public static void main(String[] args) {
		//imprimindo os estados existentes no enum
		for(EstadoBrasileiro uf: EstadoBrasileiro.values() ) {
		   System.out.println(uf.getSigla() + "-" + uf.getNomeMaiusculo());
		}
		
		//selecionando um estado a partir das opções disponíveis
		EstadoBrasileiro ufSelecionado = EstadoBrasileiro.PIAUI;
		
		System.out.println("O estado selecionado foi: " + ufSelecionado.getNome());
	}
}
```

[[Pilares da Progamação Orientada a Objetos em Java]] 