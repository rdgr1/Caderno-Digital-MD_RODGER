- `Function<T, R>`: Representa uma função que aceita um argumento do tipo T e retorna um resultado do tipo R. É utilizada para transformar ou mapear os elementos do Stream em outros valores ou tipos.

```java
public class FunctionExample {
  public static void main(String[] args) {
    // Criar uma lista de números inteiros
    List<Integer> numeros = Arrays.asList(1, 2, 3, 4, 5);

    // Usar a Function com expressão lambda para dobrar todos os números
    Function<Integer, Integer> dobrar = numero -> numero * 2;

    // Usar a função para dobrar todos os números no Stream e armazená-los em outra lista
    List<Integer> numerosDobrados = numeros.stream_api()
        .map(dobrar)
        .collect(Collectors.toList());

    // Imprimir a lista de números dobrados
    numerosDobrados.forEach(System.out::println);
  }
}
```

```java
public class FunctionExample {
  public static void main(String[] args) {
    // Criar uma lista de números inteiros
    List<Integer> numeros = Arrays.asList(1, 2, 3, 4, 5);

    // Usar a Function com uma classe anônima para dobrar todos os números
    Function<Integer, Integer> dobrar = new Function<Integer, Integer>() {
      @Override
      public Integer apply(Integer numero) {
        return numero * 2;
      }
    };

    // Usar a função para dobrar todos os números e armazená-los em outra lista
    List<Integer> numerosDobrados = new ArrayList<>();
    for (Integer numero : numeros) {
      numerosDobrados.add(dobrar.apply(numero));
    }

    // Imprimir a lista de números dobrados
    for (Integer numeroDobrado : numerosDobrados) {
      System.out.println(numeroDobrado);
    }
  }
}
```