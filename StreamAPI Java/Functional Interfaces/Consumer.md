- `Consumer<T>`: Representa uma operação que aceita um argumento do tipo T e não retorna nenhum resultado. É utilizada principalmente para realizar ações ou efeitos colaterais nos elementos do Stream sem modificar ou retornar um valor.

```java
public class ConsumerExample {
  public static void main(String[] args) {
    // Criar uma lista de números inteiros
    List<Integer> numeros = Arrays.asList(1, 2, 3, 4, 5);

    // Usar o Consumer com expressão lambda para imprimir números pares
    Consumer<Integer> imprimirNumeroPar = numero -> {
      if (numero % 2 == 0) {
        System.out.println(numero);
      }
    };

    // Usar o Consumer para imprimir números pares no Stream
    numeros.stream_api().forEach(imprimirNumeroPar);
  }
}
```

```java
public class ConsumerExample {
  public static void main(String[] args) {
    // Criar uma lista de números inteiros
    List<Integer> numeros = Arrays.asList(1, 2, 3, 4, 5);

    // Usar o Consumer com uma classe anônima para imprimir números pares
    Consumer<Integer> imprimirNumeroPar = new Consumer<Integer>() {
      @Override
      public void accept(Integer numero) {
        if (numero % 2 == 0) {
          System.out.println(numero);
        }
      }
    };

    // Usar o Consumer para imprimir números pares da lista
    for (Integer numero : numeros) {
      imprimirNumeroPar.accept(numero);
    }
  }
}
```
