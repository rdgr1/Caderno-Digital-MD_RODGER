# Projeto: Sistema de Gerenciamento de Tarefas

Desenvolva um sistema de gerenciamento de tarefas em Java que permita aos usuários criar, listar, atualizar e excluir tarefas. O sistema deve incluir os seguintes componentes e funcionalidades:

## 1. Classe Tarefa

- Crie uma classe `Tarefa` com os seguintes atributos:
    - id (int)
    - titulo (String)
    - descricao (String)
    - dataCriacao (LocalDate)
    - status (enum: PENDENTE, EM_ANDAMENTO, CONCLUIDA)

## 2. Interface GerenciadorTarefas

- Crie uma interface `GerenciadorTarefas` com os seguintes métodos:
    - adicionarTarefa(Tarefa tarefa)
    - listarTarefas()
    - buscarTarefaPorId(int id)
    - atualizarTarefa(int id, Tarefa tarefaAtualizada)
    - removerTarefa(int id)

## 3. Implementação GerenciadorTarefasImpl

- Implemente a interface `GerenciadorTarefas` em uma classe `GerenciadorTarefasImpl`
- Use uma coleção apropriada (por exemplo, ArrayList ou HashMap) para armazenar as tarefas

## 4. Exceções Personalizadas

- Crie exceções personalizadas, como `TarefaNaoEncontradaException`

## 5. Utilização de Streams e Lambda

- Use Streams e expressões lambda para implementar funcionalidades como:
    - Filtrar tarefas por status
    - Ordenar tarefas por data de criação

## 6. Testes Unitários

- Escreva testes unitários para a classe `GerenciadorTarefasImpl` usando JUnit

## 7. Mock com Mockito (Opcional)

- Se quiser um desafio extra, crie uma classe `NotificadorTarefas` e use Mockito para simular suas interações nos testes

## 8. Interface de Usuário Simples

- Crie uma classe `InterfaceUsuario` com um menu baseado em console para interagir com o sistema

## Requisitos Adicionais

- Use convenções de nomenclatura Java
- Implemente tratamento adequado de exceções
- Documente seu código usando comentários Javadoc

## Desafio Extra

- Implemente persistência de dados usando arquivos ou um banco de dados simples

Ao concluir este projeto, você terá praticado conceitos importantes de Java, incluindo classes e objetos, interfaces, coleções, exceções, streams e lambda, além de testes unitários.s