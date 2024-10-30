No ecossistema Spring, o conceito de _scope_ refere-se ao ciclo de vida e à visibilidade dos _beans_ (objetos gerenciados pelo Spring). Existem diferentes tipos de escopos que determinam como e quando os _beans_ são criados e compartilhados. Dois dos escopos mais comuns no Spring são o **Singleton** e o **Prototype**. Vou fazer um breve resumo sobre cada um deles:

### Singleton Scope:

- **Definição:** No _scope_ _singleton_, o Spring cria apenas uma única instância do _bean_ para todo o contêiner Spring. Ou seja, essa instância é compartilhada por todas as requisições que precisarem do _bean_ durante o ciclo de vida do aplicativo.
    
- **Comportamento:** Quando você define um _bean_ como _singleton_ (o que é o padrão no Spring), toda vez que você injeta ou solicita esse _bean_, a mesma instância será retornada.
    
- **Quando usar:** O escopo _singleton_ é útil quando o _bean_ não precisa ser recriado a cada requisição, como em casos onde o _bean_ é imutável ou mantém um estado compartilhado entre diferentes partes da aplicação.
    
    **Exemplo de uso:** Um _service_ que realiza operações sem manter estado (stateless), como serviços de autenticação ou de negócios que apenas processam dados sem alterar seu estado interno.
    

### Prototype Scope:

- **Definição:** No _scope_ _prototype_, o Spring cria uma nova instância do _bean_ sempre que ele é solicitado. Isso significa que toda vez que você faz uma injeção ou solicita esse _bean_, uma nova instância é criada.
    
- **Comportamento:** Diferentemente do _singleton_, o _bean_ com _scope_ _prototype_ não é compartilhado. Cada solicitação resulta em uma nova instância do objeto, e ele não é gerenciado pelo contêiner após sua criação.
    
- **Quando usar:** O _scope_ _prototype_ é ideal quando o _bean_ precisa ser mutável ou manter estados que são específicos para cada uso, como quando você precisa de um novo objeto a cada operação, ou quando há manipulação de estado interno que não deve ser compartilhado.
    
    **Exemplo de uso:** Objetos que representam uma sessão temporária de um processo ou que manipulam dados que variam ao longo do ciclo de vida da aplicação, como formulários de entrada de usuário.

### Resumo das Diferenças:

- **Singleton:** Uma instância compartilhada por todo o contêiner Spring. Criado uma única vez.
- **Prototype:** Uma nova instância é criada a cada solicitação.

### Exemplo 1: Singleton Scope (Padrão)

Por padrão, o escopo de um _bean_ no Spring é **Singleton**, então você não precisa explicitamente usar a anotação `@Scope` a menos que queira ser explícito sobre o escopo.
```java
import org.springframework.stereotype.Component;

@Component
public class MeuBeanSingleton {
    
    public MeuBeanSingleton() {
        System.out.println("Bean Singleton criado!");
    }
    
    public void executar() {
        System.out.println("Executando método no bean singleton.");
    }
}

```
**Explicação:**

- O Spring cria **uma única instância** da classe `MeuBeanSingleton` ao iniciar o contêiner.
- Mesmo que você injete esse _bean_ em múltiplas classes, será sempre a **mesma instância** sendo utilizada.
- O escopo _singleton_ é o comportamento padrão, então não é necessário adicionar a anotação `@Scope("singleton")` explicitamente.

### Exemplo 2: Prototype Scope

Para criar um _bean_ com escopo **Prototype**, ou seja, uma nova instância a cada solicitação, você precisa usar a anotação `@Scope` explicitamente.
```java
import org.springframework.context.annotation.Scope;
import org.springframework.stereotype.Component;

@Component
@Scope("prototype")
public class MeuBeanPrototype {
    
    public MeuBeanPrototype() {
        System.out.println("Bean Prototype criado!");
    }
    
    public void executar() {
        System.out.println("Executando método no bean prototype.");
    }
}
```
**Explicação:**

- A anotação `@Scope("prototype")` informa ao Spring que **uma nova instância** do `MeuBeanPrototype` deve ser criada sempre que for solicitada.
- Isso significa que, se você injetar esse _bean_ em diferentes classes ou chamá-lo várias vezes, cada vez será criada uma **nova instância**.