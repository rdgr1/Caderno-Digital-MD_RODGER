Aqui está um resumo em formato Markdown para potencializar o projeto **Banco Malvader**.

---

# Projeto Banco Malvader

## Objetivo do Projeto
Desenvolver uma aplicação bancária em Java chamada **Banco Malvader**, com interface gráfica utilizando **Swing** e persistência de dados em um banco **MySQL**. O projeto aplica conceitos de Programação Orientada a Objetos (POO) para gerenciamento de contas bancárias, autenticação de usuários e geração de relatórios financeiros.

## Funcionalidades

### Acesso e Autenticação
1. **Menu Principal**: 
   - Funcionário
   - Cliente
   - Sair
2. **Autenticação por Senha**:
   - Funcionário: Acesso ao menu de gerenciamento.
   - Cliente: Acesso ao menu de operações de conta.

### Menu Funcionário
- **Abertura de Conta**:
  - Tipos de Conta: Conta Poupança (CP) e Conta Corrente (CC)
  - Dados Necessários: Nome, CPF, data de nascimento, contato, endereço completo, senha e limite (para conta corrente).
- **Encerramento de Conta**:
  - Requer senha de administrador.
  - Busca e confirmação de encerramento.
- **Consulta de Dados**:
  - Consultar dados de contas, funcionários ou clientes.
- **Alteração de Dados**:
  - Permite editar dados de conta, funcionário e cliente.
- **Cadastro de Funcionários**:
  - Requer senha de administrador para adicionar novos funcionários.
- **Geração de Relatórios**:
  - Relatório geral de movimentações com exportação para Excel.

### Menu Cliente
- **Operações de Conta**:
  - Saldo, Depósito, Saque, Extrato e Consulta de Limite
  - Solicita senha para certas operações.

## Estrutura do Projeto

### Pacotes e Classes Principais

#### `dao`
- **ConnectionFactory**: Gerencia a conexão com o banco de dados MySQL.
- **FuncionarioDAO, ClienteDAO, etc.**: Manipula dados no banco.

#### `model`
- **Funcionario, Cliente, Conta**: Representam tabelas do banco.

#### `view`
- **LoginView, MenuFuncionarioView, MenuClienteView**: Interface gráfica das operações.
- **CadastroFuncionarioView, CadastroContaView**: Telas de cadastro e consulta.

#### `controller`
- **FuncionarioController, ClienteController, ContaController**: Lógica que conecta a interface gráfica com a lógica de negócios.

#### `util`
- **DBUtil**: Métodos utilitários para conectar e desconectar o banco de dados.

## Banco de Dados

### Estrutura das Tabelas

1. **usuario**: Dados básicos de usuários (id, nome, cpf, tipo, senha).
2. **funcionario e cliente**: Dados específicos de cada tipo de usuário.
3. **endereco**: Endereços vinculados a usuários.
4. **conta, conta_corrente, conta_poupanca**: Dados das contas, com atributos específicos por tipo.
5. **transacao**: Registro de saques, depósitos e outras transações.
6. **relatorio**: Registros de relatórios gerados pelos funcionários.

### Relacionamentos
- **1:N** entre `cliente` e `conta`.
- **1:N** entre `conta` e `transacao`.
- **1:1** entre `usuario` e `funcionario/cliente`.

## Interface Gráfica (Swing)

- **Tela de Login**: Autenticação inicial.
- **Menu Principal**: Acesso ao menu específico para funcionários ou clientes.
- **Menus específicos**: Cada menu possui opções exclusivas para o gerenciamento de contas, transações e relatórios.

## Implementação de Persistência de Dados

- **Classe `DataManager`**: Gerencia operações de leitura e gravação de dados.
- **BancoController**: Chamadas aos métodos de salvar e carregar dados para persistência entre execuções do programa.

---

Esse resumo destaca a organização e a estrutura do projeto, incluindo a aplicação dos conceitos de POO, persistência de dados com MySQL e desenvolvimento de interface gráfica com Swing.