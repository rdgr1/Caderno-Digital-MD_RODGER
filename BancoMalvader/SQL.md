A implementação do projeto do Banco Malvader em SQL pode ser feita com base na estrutura de tabelas e relacionamentos descritos. Abaixo, apresento o script SQL completo para criar as tabelas no MySQL, incluindo as chaves primárias, estrangeiras e tipos de dados apropriados:

```sql
-- Tabela usuario: Armazena dados comuns para usuários do sistema (funcionários e clientes)
CREATE TABLE usuario (
    id_usuario INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    cpf VARCHAR(11) NOT NULL UNIQUE,
    data_nascimento DATE NOT NULL,
    telefone VARCHAR(15),
    tipo_usuario ENUM('FUNCIONARIO', 'CLIENTE') NOT NULL,
    senha VARCHAR(50) NOT NULL
);

-- Tabela funcionario: Armazena dados específicos dos funcionários
CREATE TABLE funcionario (
    id_funcionario INT AUTO_INCREMENT PRIMARY KEY,
    codigo_funcionario VARCHAR(20) NOT NULL UNIQUE,
    cargo VARCHAR(50) NOT NULL,
    id_usuario INT NOT NULL,
    FOREIGN KEY (id_usuario) REFERENCES usuario(id_usuario)
);

-- Tabela cliente: Armazena dados específicos dos clientes
CREATE TABLE cliente (
    id_cliente INT AUTO_INCREMENT PRIMARY KEY,
    id_usuario INT NOT NULL,
    FOREIGN KEY (id_usuario) REFERENCES usuario(id_usuario)
);

-- Tabela endereco: Armazena endereços dos usuários (clientes e funcionários)
CREATE TABLE endereco (
    id_endereco INT AUTO_INCREMENT PRIMARY KEY,
    cep VARCHAR(10) NOT NULL,
    local VARCHAR(100) NOT NULL,
    numero_casa INT NOT NULL,
    bairro VARCHAR(50),
    cidade VARCHAR(50),
    estado VARCHAR(2),
    id_usuario INT NOT NULL,
    FOREIGN KEY (id_usuario) REFERENCES usuario(id_usuario)
);

-- Tabela conta: Tabela base para contas bancárias, tanto para poupança quanto para conta corrente
CREATE TABLE conta (
    id_conta INT AUTO_INCREMENT PRIMARY KEY,
    numero_conta VARCHAR(20) NOT NULL UNIQUE,
    agencia VARCHAR(10) NOT NULL,
    saldo DECIMAL(15, 2) DEFAULT 0.00,
    tipo_conta ENUM('POUPANCA', 'CORRENTE') NOT NULL,
    id_cliente INT NOT NULL,
    FOREIGN KEY (id_cliente) REFERENCES cliente(id_cliente)
);

-- Tabela conta_corrente: Armazena dados específicos de contas correntes
CREATE TABLE conta_corrente (
    id_conta_corrente INT AUTO_INCREMENT PRIMARY KEY,
    limite DECIMAL(15, 2) NOT NULL,
    data_vencimento DATE,
    id_conta INT NOT NULL,
    FOREIGN KEY (id_conta) REFERENCES conta(id_conta)
);

-- Tabela conta_poupanca: Armazena dados específicos de contas poupança
CREATE TABLE conta_poupanca (
    id_conta_poupanca INT AUTO_INCREMENT PRIMARY KEY,
    taxa_rendimento DECIMAL(5, 2) NOT NULL,
    id_conta INT NOT NULL,
    FOREIGN KEY (id_conta) REFERENCES conta(id_conta)
);

-- Tabela transacao: Armazena transações realizadas nas contas (saques, depósitos, etc.)
CREATE TABLE transacao (
    id_transacao INT AUTO_INCREMENT PRIMARY KEY,
    tipo_transacao ENUM('DEPOSITO', 'SAQUE', 'TRANSFERENCIA') NOT NULL,
    valor DECIMAL(15, 2) NOT NULL,
    data_hora TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    id_conta INT NOT NULL,
    FOREIGN KEY (id_conta) REFERENCES conta(id_conta)
);

-- Tabela relatorio: Armazena relatórios gerados pelos funcionários
CREATE TABLE relatorio (
    id_relatorio INT AUTO_INCREMENT PRIMARY KEY,
    tipo_relatorio VARCHAR(50) NOT NULL,
    data_geracao TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    conteudo TEXT,
    id_funcionario INT NOT NULL,
    FOREIGN KEY (id_funcionario) REFERENCES funcionario(id_funcionario)
);
```

### Explicação das Estruturas e Relacionamentos

1. **usuario**: Base para qualquer usuário (cliente ou funcionário) com dados comuns.
2. **funcionario**: Associada à `usuario`, com informações específicas de funcionários.
3. **cliente**: Associada à `usuario`, representando os clientes.
4. **endereco**: Dados de endereço associados ao usuário.
5. **conta**: Representa contas bancárias, podendo ser de tipo `POUPANCA` ou `CORRENTE`.
6. **conta_corrente** e **conta_poupanca**: Guardam dados específicos de contas correntes e poupança, respectivamente.
7. **transacao**: Registra todas as movimentações de uma conta.
8. **relatorio**: Armazena relatórios criados por funcionários.

Essas tabelas e seus relacionamentos foram estruturados para refletir o modelo orientado a objetos e as funcionalidades descritas, permitindo que o sistema de banco mantenha a integridade dos dados e atenda aos requisitos.