# Banco Malvader - Checklist de Implementação

## 1. Configuração Inicial
- [x] Instalar e configurar o **JDK** e **MySQL**.
- [x] Baixar e adicionar o driver **JDBC MySQL** ao projeto.
- [x] Criar o banco de dados e tabelas no MySQL conforme estrutura fornecida.
- [x] Configurar a classe de conexão (`ConnectionFactory`) no pacote `dao`.

---

## 2. Estrutura do Banco de Dados (Tabelas)
### Tabela `usuario`
- [x] Coluna `id_usuario` (PK, INT, AUTO_INCREMENT)
- [x] Coluna `nome` (VARCHAR, 100)
- [x] Coluna `cpf` (VARCHAR, 11)
- [x] Coluna `data_nascimento` (DATE)
- [x] Coluna `telefone` (VARCHAR, 15)
- [x] Coluna `tipo_usuario` (ENUM: 'FUNCIONARIO', 'CLIENTE')
- [x] Coluna `senha` (VARCHAR, 50)

### Tabela `funcionario`
- [x] Coluna `id_funcionario` (PK, INT, AUTO_INCREMENT)
- [x] Coluna `codigo_funcionario` (VARCHAR, 20)
- [x] Coluna `cargo` (VARCHAR, 50)
- [x] Coluna `id_usuario` (FK, INT)

### Tabela `cliente`
- [x] Coluna `id_cliente` (PK, INT, AUTO_INCREMENT)
- [x] Coluna `id_usuario` (FK, INT)

### Tabela `endereco`
- [x] Coluna `id_endereco` (PK, INT, AUTO_INCREMENT)
- [x] Coluna `cep` (VARCHAR, 10)
- [x] Coluna `local` (VARCHAR, 100)
- [x] Coluna `numero_casa` (INT)
- [x] Coluna `bairro` (VARCHAR, 50)
- [x] Coluna `cidade` (VARCHAR, 50)
- [x] Coluna `estado` (VARCHAR, 2)
- [x] Coluna `id_usuario` (FK, INT)

### Tabela `conta`
- [x] Coluna `id_conta` (PK, INT, AUTO_INCREMENT)
- [x] Coluna `numero_conta` (VARCHAR, 20)
- [x] Coluna `agencia` (VARCHAR, 10)
- [x] Coluna `saldo` (DECIMAL, 15,2)
- [x] Coluna `tipo_conta` (ENUM: 'POUPANCA', 'CORRENTE')
- [x] Coluna `id_cliente` (FK, INT)

### Tabela `conta_corrente`
- [x] Coluna `id_conta_corrente` (PK, INT, AUTO_INCREMENT)
- [x] Coluna `limite` (DECIMAL, 15,2)
- [x] Coluna `data_vencimento` (DATE)
- [x] Coluna `id_conta` (FK, INT)

### Tabela `conta_poupanca`
- [x] Coluna `id_conta_poupanca` (PK, INT, AUTO_INCREMENT)
- [x] Coluna `taxa_rendimento` (DECIMAL, 5,2)
- [x] Coluna `id_conta` (FK, INT)

### Tabela `transacao`
- [x] Coluna `id_transacao` (PK, INT, AUTO_INCREMENT)
- [x] Coluna `tipo_transacao` (ENUM: 'DEPOSITO', 'SAQUE', 'TRANSFERENCIA')
- [x] Coluna `valor` (DECIMAL, 15,2)
- [x] Coluna `data_hora` (TIMESTAMP)
- [x] Coluna `id_conta` (FK, INT)

### Tabela `relatorio`
- [x] Coluna `id_relatorio` (PK, INT, AUTO_INCREMENT)
- [x] Coluna `tipo_relatorio` (VARCHAR, 50)
- [x] Coluna `data_geracao` (TIMESTAMP)
- [x] Coluna `conteudo` (TEXT)
- [x] Coluna `id_funcionario` (FK, INT)

---

## 3. Implementação das Classes Modelo (Models)
### Classe `Usuario` (abstrata)
- [x] Atributos: `id`, `nome`, `cpf`, `dataNascimento`, `telefone`, `endereco`
- [x] Métodos: `login(senha)`, `logout()`, `consultarDados()`

### Classe `Funcionario` (herda de `Usuario`)
- [x] Atributos: `codigoFuncionario`, `cargo`, `senha`
- [x] Métodos: `abrirConta()`, `encerrarConta()`, `consultarDadosConta()`, `consultarDadosCliente()`, `alterarDadosConta()`, `alterarDadosCliente()`, `cadastrarFuncionario()`, `gerarRelatorioMovimentacao()`

### Classe `Cliente` (herda de `Usuario`)
- [x] Atributos: `senha`
- [x] Métodos: `consultarSaldo()`, `depositar()`, `sacar()`, `consultarExtrato()`, `consultarLimite()`

### Classe `Endereco`
- [x] Atributos: `cep`, `local`, `numeroCasa`, `bairro`, `cidade`, `estado`
- [x] Método: `toString()`

### Classe `Conta` (abstrata)
- [x] Atributos: `numero`, `agencia`, `saldo`, `cliente`
- [x] Métodos: `depositar()`, `sacar()`, `consultarSaldo()`

### Classe `ContaPoupanca` (herda de `Conta`)
- [x] Atributos: `taxaRendimento`
- [x] Método: `calcularRendimento()`

### Classe `ContaCorrente` (herda de `Conta`)
- [x] Atributos: `limite`, `dataVencimento`
- [x] Método: `consultarLimite()`

### Classe `Relatorio`
- [x] Atributos: `tipo`, `dataGeracao`, `dados`
- [x] Métodos: `gerarRelatorioGeral()`, `exportarParaExcel()`

### Classe `ConexaoBanco`
- [ ] Atributos: `url`, `usuario`, `senha`
- [ ] Métodos: `conectar()`, `desconectar()`

---

## 4. Implementação dos DAOs (Data Access Objects)
### Classe `ConnectionFactory`
- [x] Método para estabelecer e fechar conexão com MySQL.

### FuncionarioDAO, ClienteDAO, ContaDAO, etc.
- [x] Métodos `save()`, `update()`, `delete()`, `findById()` e outros conforme necessidade.

---

## 5. Desenvolvimento dos Controladores (Controllers)
### `BancoController`
- [ ] Métodos para `abrirConta()`, `encerrarConta()`, `consultarConta()`, `salvarDados()`, `carregarDados()`

### `FuncionarioController`
- [x] Métodos para operações de funcionário, como `consultarDadosConta()`, `consultarDadosCliente()`, `alterarDadosConta()`, `alterarDadosCliente()`, `cadastrarFuncionario()`, `gerarRelatorioMovimentacao()`

### `ClienteController`
- [ ] Métodos para operações de cliente, como `consultarSaldo()`, `depositar()`, `sacar()`, `consultarExtrato()`, `consultarLimite()`

---

## 6. Implementação da Interface Gráfica (Swing)
### Tela de Login
- [ ] Implementar `LoginView` com campos de entrada e botões para acesso de funcionários e clientes.

### Menu Funcionário
- [ ] Implementar `MenuFuncionarioView` com botões para Abertura de Conta, Encerramento de Conta, Consulta de Dados, Alteração de Dados, Cadastro de Funcionário, Geração de Relatórios e Sair.

### Menu Cliente
- [ ] Implementar `MenuClienteView` com botões para Saldo, Depósito, Saque, Extrato, Consultar Limite e Sair.

### Telas de Formulário e Visualização
- [ ] `CadastroFuncionarioView`
- [ ] `CadastroContaView`
- [ ] Demais formulários e telas conforme especificações do projeto.

---

## 7. Funcionalidades e Persistência de Dados
- [ ] Implementar lógica de negócios para verificar saldo, cálculo de rendimento, limites de saque e persistência dos dados.

---

## 8. Relatórios e Exportação de Dados
- [ ] Implementar geração de relatórios de movimentações financeiras.
- [ ] Implementar exportação para Excel.

---

## 9. Testes e Depuração
- [ ] Testar autenticação, menus, abertura e encerramento de contas.
- [ ] Verificar transações bancárias (saldo, depósito, saque).
- [ ] Testar geração e exportação de relatórios.

---

## 10. Documentação e Apresentação
- [ ] Documentar classes e fluxo do sistema.
- [ ] Revisar código e adicionar comentários.
- [ ] Preparar uma apresentação do sistema.

