### 1. **Desafio de Cores Favoritas**

**Descrição:** Crie uma aplicação onde o usuário pode armazenar suas cores favoritas em uma lista.

- **Passos:**
    1. Permita ao usuário adicionar novas cores.
    2. Remova cores específicas que o usuário não gosta mais.
    3. Exiba as cores na ordem de inserção.
    4. Exiba as cores em ordem alfabética.
- **Dicas:**
    - Use `LinkedList<String>` para manter a ordem de inserção.
    - Para organizar, utilize `Collections.sort()`.

### 2. **Temperaturas Anuais**

**Descrição:** Crie um programa que armazena as temperaturas médias de cada mês do ano.

- **Passos:**
    1. Armazene as temperaturas em um `List<Double>`.
    2. Calcule e exiba a média das temperaturas.
    3. Exiba apenas os meses em que a temperatura foi acima da média.
- **Dicas:**
    - Use uma lista simples (`ArrayList`) e um loop para calcular a média.

### 3. **Lista de Livros Favoritos**

**Descrição:** Crie um programa que permita ao usuário gerenciar uma lista de seus livros favoritos.

- **Passos:**
    1. Permita adicionar livros, com nome e autor.
    2. Exiba todos os livros na ordem de inserção.
    3. Organize e exiba os livros por nome e, depois, por autor.
- **Dicas:**
    - Crie uma classe `Livro` e use `ArrayList<Livro>`.
    - Utilize `Comparator` para ordenação.

### 4. **Desafio de Notas de Estudantes**

**Descrição:** Crie uma aplicação para gerenciar as notas de estudantes.

- **Passos:**
    1. Armazene o nome do estudante e suas respectivas notas em um `Map<String, List<Double>>`.
    2. Permita adicionar, remover e atualizar notas de estudantes.
    3. Exiba a média das notas de cada estudante.
    4. Liste os estudantes em ordem alfabética.
- **Dicas:**
    - Use `HashMap` para associar o nome do estudante à lista de notas.

### 5. **Desafio de Comparação de Produtos**

**Descrição:** Crie um sistema para gerenciar produtos em um estoque, permitindo comparar preços e quantidade.

- **Passos:**
    1. Crie uma classe `Produto` com `nome`, `preço` e `quantidade`.
    2. Armazene os produtos em um `Set<Produto>`, garantindo que não haja duplicatas.
    3. Organize os produtos por preço, do menor para o maior.
    4. Exiba os produtos que possuem estoque abaixo de um limite fornecido pelo usuário.
- **Dicas:**
    - Use `TreeSet<Produto>` e implemente `Comparable<Produto>` para ordenar por preço.