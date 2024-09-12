 `Supplier<T>`: Representa uma operação que não aceita nenhum argumento e retorna um resultado do tipo T. É comumente usada para criar ou fornecer novos objetos de um determinado tipo.

```java
public class SupplierExample {
  public static void main(String[] args) {
    // Usar o Supplier com expressão lambda para fornecer uma saudação personalizada
    Supplier<String> saudacao = () -> "Olá, seja bem-vindo(a)!";

    // Usar o Supplier para obter uma lista com 5 saudações
    List<String> listaSaudacoes = Stream.generate(saudacao)
        .limit(5)
        .collect(Collectors.toList());

    // Imprimir as saudações geradas
    listaSaudacoes.forEach(System.out::println);
  }
}
```

```java
public class SupplierExample {
  public static void main(String[] args) {
    // Usar o Supplier com uma classe anônima para fornecer uma saudação personalizada
    Supplier<String> saudacao = new Supplier<String>() {
      @Override
      public String get() {
        return "Olá, seja bem-vindo(a)!";
      }
    };

    // Usar o Supplier para obter uma lista com 5 saudações
    List<String> listaSaudacoes = new ArrayList<>();
    for (int i = 0; i < 5; i++) {
      listaSaudacoes.add(saudacao.get());
    }

    // Imprimir as saudações geradas
    for (String saudacaoGerada : listaSaudacoes) {
      System.out.println(saudacaoGerada);
    }
  }
}
```

