
## 1. Declaração da Classe
**Sintaxe:**
```java
public class NomeDaClasse {
    // Corpo da classe
}
``` 
**Descrição:** Define a estrutura de classe. `public` é um modificador de  acesso que torna a classe acessível de qualquer lugar

## 2. Modificadores de Acesso
- `public`: Acesso global. A classe é visível em qualquer outro pacote.
- `protected`: Acesso restrito a subclasses e classes no mesmo pacote.
- `default`: (sem modificador) Acesso apenas dentro do mesmo pacote.
- `private`: Não aplicável a classes top-level; usado para membros de classes.

## 3. Campos
**Sintaxe:**
```java
private int idade;
```
**Descrição:** Representam as propriedades ou estado dos objetos da classe. Normalmente são `private` para garantir o encapsulamento.

## 4. Contrutores
**Sintaxe:**
```java
public NomeDaClasse(){
    // Inicialização dos campos 
}
```
**Descrição:** Métodos especiais que são chamados quando um objeto é criado. Têm o mesmo nome da classe e não têm tipo de retorno.
## 5. Métodos
**Sintaxe:**
```java
public void exibirMensagem(){
    // Implementação de método
}
```
**Descrição:** Definem o comportamento da classe. Podem ser `public`, `private`, ou `protected` e podem retornar um valor ou `void`.

## 6. `this` e `super`
- `this`: Refere-se ao objeto atual. Usado para acessar membros da classe atual.
- `super`: Refere-se à superclasse imediata. Usado para acessar membros da superclasse e chamar seu construtor.

## 7. Herança
**Sintaxe:**
```java
public class SubClasse extends SuperClasse{
    // Corpo da subclassse
}
```
**Descrição:** Permite que uma classe (subclasse) herde propriedades e métodos de outra classe(superclasse).

## 8.Encapsulamento
**Descrição:** Prática de esconder os detalhes internos da classe e expor apenas o necessário, Normalmente os campos são privados e acessados através de métodos públicos.

## 9. Membros Estáticos
```java
public static int contador;
public static void metodoEstatico() {
    // Implementação do método estático
}
```
**Descrição:** Membros que pertencem à classe a não a uma instância específica. São acessíveis via `NomeDaClasse.membro`.

## 10. Classes Internas(Aninhadas)
**Sintaxe:**
```java
public class ClasseExterna{
    public class ClasseInterna{
        // Corpo da classe interna 
    }
}
```
**Descrição:** Classes definidas dentro de outra classe. Podem ser internas(têm acesso à instância da classe externa) ou estáticas (não tem acesso implicíto à instância da casse externa).
[[2 - Tipos e Variáveis]]
