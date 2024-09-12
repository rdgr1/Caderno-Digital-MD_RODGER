 `BinaryOperator<T>`: Representa uma operação que combina dois argumentos do tipo T e retorna um resultado do mesmo tipo T. É usada para realizar operações de redução em pares de elementos, como somar números ou combinar objetos.

```java
public class BinaryOperatorExample {
  public static void main(String[] args) {
    // Criar uma lista de números inteiros
    List<Integer> numeros = Arrays.asList(1, 2, 3, 4, 5);

    // Usar o BinaryOperator com expressão lambda para somar dois números inteiros
    BinaryOperator<Integer> somar = (num1, num2) -> num1 + num2;

    // Usar o BinaryOperator para somar todos os números no Stream
    int resultado = numeros.stream_api()
        .reduce(0, somar);

    // Imprimir o resultado da soma
    System.out.println("A soma dos números é: " + resultado);
  }
}
```

```java
public class BinaryOperatorExample {
  public static void main(String[] args) {
    // Criar uma lista de números inteiros
    List<Integer> numeros = Arrays.asList(1, 2, 3, 4, 5);

    // Usar o BinaryOperator com classe anônima para somar dois números inteiros
    BinaryOperator<Integer> somar = new BinaryOperator<Integer>() {
      @Override
      public Integer apply(Integer num1, Integer num2) {
        return num1 + num2;
      }
    };

    // Usar o BinaryOperator para somar todos os números no Stream
    int resultado = numeros.stream_api()
        .reduce(0, somar);

    // Imprimir o resultado da soma
    System.out.println("A soma dos números é: " + resultado);
  }
}
```

> _Classe Anônima_: A classe anônima em Java é uma classe não recebeu um nome e é tanto declarado e instanciado em uma única instrução. Você deve considerar o uso de uma classe anônima sempre que você precisa para criar uma classe que será instanciado apenas uma vez.