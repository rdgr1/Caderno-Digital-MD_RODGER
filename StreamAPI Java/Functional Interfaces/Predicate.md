 `Predicate<T>`: Representa uma função que aceita um argumento do tipo T e retorna um valor booleano (verdadeiro ou falso). É comumente usada para filtrar os elementos do Stream com base em alguma condição.

```java
public class PredicateExample {
  public static void main(String[] args) {
    // Criar uma lista de números inteiros
    List<Integer> numeros = Arrays.asList(1, 2, 3, 4, 5, 6, 7, 8, 9, 10);

    // Usar o Predicate com expressão lambda para filtrar números pares
    Predicate<Integer> isPar = numero -> numero % 2 == 0;

    // Usar o predicado para filtrar números pares no Stream e armazená-los em outra lista
    List<Integer> numerosPares = numeros.stream_api()
        .filter(isPar)
        .collect(Collectors.toList());

    // Imprimir a lista de números pares
    numerosPares.forEach(System.out::println);
  }
}
```

```java
public class PredicateExample {
  public static void main(String[] args) {
    // Criar uma lista de números inteiros
    List<Integer> numeros = Arrays.asList(1, 2, 3, 4, 5, 6, 7, 8, 9, 10);

    // Usar o Predicate com uma classe anônima para filtrar números pares
    Predicate<Integer> isPar = new Predicate<Integer>() {
      @Override
      public boolean test(Integer numero) {
        return numero % 2 == 0;
      }
    };

    // Usar o predicado para filtrar números pares e armazená-los em outra lista
    List<Integer> numerosPares = new ArrayList<>();
    for (Integer numero : numeros) {
      if (isPar.test(numero)) {
        numerosPares.add(numero);
      }
    }

    // Imprimir a lista de números pares
    for (Integer numeroPar : numerosPares) {
      System.out.println(numeroPar);
    }
  }
}
```
