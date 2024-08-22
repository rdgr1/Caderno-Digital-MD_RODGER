Programação Orientada a Objetos **(POO)** é um paradigma que utiliza **"objetos"** para representar dados e comportamentos. Esses objetos combinam campos (ou atributos) e métodos (ou procedimentos). **A POO** é valorizada por sua capacidade de modelar o mundo real, como em exemplos como Conta Bancária, Aluno, ou Veículo. Ela facilita a reutilização de código e torna a representação do sistema mais intuitiva. As linguagens orientadas a objetos devem seguir os quatro pilares da **POO:** Encapsulamento, Herança, Polimorfismo e Abstração. 

- **Encapsulamento:** Nem tudo precisa estar visível, grande parte do nosso algoritmo pode ser distribuído em métodos com finalidades específicas que complementa uma ação em nossa aplicação.
    
    Exemplo: Ligar um veículo exige muitas etapas para a engenharia, mas o condutor só visualiza a ignição, dar a partida e a _“magia”_ acontece.
    
- **Herança:** Características e comportamentos comuns podem ser elevados e compartilhados através de uma hierarquia de objetos.
    
    Exemplo: Um Carro e uma Motocicleta possuem propriedades como placa, chassi, ano de fabricação e métodos como acelerar, frear. Logo para não ser um processo de codificação redundante, podemos desfrutar da herança criando uma classe **Veiculo** para que seja herdada por Carro e Motocicleta.
    
- **Abstração:** É a indisponibilidade para determinar a lógica de um ou vários comportamentos em um objeto.
    
    Exemplo: **Veículo** determina duas ações como acelerar e frear, logo estes comportamentos deverão ser _abstratos_ pois existem mais de uma maneira de se realizar a mesma operação. ver _Polimorfismo_.
    
- **Polimorfismo:** São as inúmeras maneiras de se realizar uma mesma ação.
    
    Exemplo: Veículo determina duas ações como acelerar e frear, primeiramente precisamos identificar se estaremos nos referindo a **Carro** ou **Motocicleta** para determinar a lógica de aceleração e frenagem dos respectivos veículos.

## Interface 

Em Java, uma interface é um tipo especial de referência que define um contrato para as classes que a implementam. Ela especifica um conjunto de métodos que a classe deve fornecer, sem definir como esses métodos serão implementados. As interfaces permitem a criação de código mais flexível e reutilizável, pois várias classes podem implementar a mesma interface de maneiras diferentes.

**Características principais das interfaces em Java:**

- **Métodos abstratos:** São métodos que não têm implementação na interface. As classes que implementam a interface devem fornecer a implementação desses métodos.
- **Métodos default e static:** Desde Java 8, interfaces podem ter métodos com implementação, chamados de métodos `default` e `static`.
- **Sem construtores:** Interfaces não podem ter construtores porque não podem ser instanciadas diretamente.
- **Herança múltipla:** Uma interface pode estender outras interfaces, permitindo a combinação de vários contratos.

**Benefícios das interfaces:**

- **Flexibilidade:** Permitem que diferentes classes ofereçam implementações variadas para os mesmos métodos.
- **Polimorfismo:** Facilitam o uso de objetos de diferentes classes de forma intercambiável se eles implementarem a mesma interface.