Perfeito! Dado que você já tem os DAOs e os models prontos, vamos focar na criação das `Controllers` e `Views`, organizando-os para interagir adequadamente com seus DAOs e modelos. Vou propor uma estrutura de `Controller` e `View` que se conecta aos DAOs e realiza operações de acordo com o seu projeto.

Para um sistema de banco, podemos considerar que as `Controllers` principais seriam:

1. **UsuarioController**: Gerencia autenticação e acesso.
2. **FuncionarioController**: Gerencia funcionalidades relacionadas a funcionários, como cadastro de clientes, contas, e consultas.
3. **ClienteController**: Gerencia operações específicas de clientes, como depósito, saque, consulta de saldo e extrato.
4. **RelatorioController**: Gerencia geração e exibição de relatórios financeiros.

As **Views** serão telas com interface `Swing` que chamam os métodos das `Controllers`. As principais `Views` podem incluir:

1. **LoginView**: Tela de login para usuários.
2. **FuncionarioView**: Menu principal para funcionários, com opções de cadastro e consulta.
3. **ClienteView**: Menu principal para clientes, com opções de depósito, saque, saldo, etc.
4. **CadastroClienteView**, **CadastroContaView**, etc.: Telas de formulários específicos para cadastro.
5. **RelatorioView**: Tela de geração e exibição de relatórios.

Vou te guiar na criação básica de cada `Controller` e uma estrutura de `View` com `Swing`.

---

### 1. `UsuarioController` para Autenticação

A `UsuarioController` será responsável pela autenticação e validação de acesso.

#### `UsuarioController`

```java
package org.swing.controller;

import org.swing.dao.UsuarioDAO;
import org.swing.model.Usuario;

public class UsuarioController {
    private final UsuarioDAO usuarioDAO;

    public UsuarioController() {
        this.usuarioDAO = new UsuarioDAO();
    }

    public Usuario autenticar(String cpf, String senha) {
        try {
            Usuario usuario = usuarioDAO.buscarUsuarioPorCpf(cpf);
            if (usuario != null && usuario.getSenha().equals(senha)) {
                return usuario;
            }
        } catch (Exception e) {
            e.printStackTrace();
        }
        return null;
    }
}
```

---

### 2. `FuncionarioController` para Gestão de Funcionários e Contas

A `FuncionarioController` será responsável pelas operações relacionadas a funcionários, como abrir contas, gerenciar clientes, etc.

#### `FuncionarioController`

```java
package org.swing.controller;

import org.swing.dao.ClienteDAO;
import org.swing.dao.FuncionarioDAO;
import org.swing.dao.ContaDAO;
import org.swing.model.Cliente;
import org.swing.model.Funcionario;
import org.swing.model.Conta;

import java.util.List;

public class FuncionarioController {
    private final FuncionarioDAO funcionarioDAO;
    private final ClienteDAO clienteDAO;
    private final ContaDAO contaDAO;

    public FuncionarioController() {
        this.funcionarioDAO = new FuncionarioDAO();
        this.clienteDAO = new ClienteDAO();
        this.contaDAO = new ContaDAO();
    }

    public boolean cadastrarCliente(Cliente cliente) {
        try {
            clienteDAO.save(cliente);
            return true;
        } catch (Exception e) {
            e.printStackTrace();
            return false;
        }
    }

    public boolean abrirConta(Conta conta) {
        try {
            contaDAO.save(conta);
            return true;
        } catch (Exception e) {
            e.printStackTrace();
            return false;
        }
    }

    public List<Cliente> listarClientes() {
        return clienteDAO.findAll();
    }

    public List<Funcionario> listarFuncionarios() {
        return funcionarioDAO.findAll();
    }
}
```

---

### 3. `ClienteController` para Operações de Conta

A `ClienteController` gerencia operações como depósito, saque, consulta de saldo, etc.

#### `ClienteController`

```java
package org.swing.controller;

import org.swing.dao.ContaDAO;
import org.swing.dao.TransacaoDAO;
import org.swing.model.Conta;
import org.swing.model.Transacao;

public class ClienteController {
    private final ContaDAO contaDAO;
    private final TransacaoDAO transacaoDAO;

    public ClienteController() {
        this.contaDAO = new ContaDAO();
        this.transacaoDAO = new TransacaoDAO();
    }

    public double consultarSaldo(int contaId) {
        Conta conta = contaDAO.findById(contaId);
        return conta != null ? conta.getSaldo() : 0.0;
    }

    public boolean depositar(int contaId, double valor) {
        try {
            Conta conta = contaDAO.findById(contaId);
            if (conta != null) {
                conta.depositar(valor);
                contaDAO.update(conta);
                
                Transacao transacao = new Transacao("DEPOSITO", valor, conta);
                transacaoDAO.save(transacao);

                return true;
            }
        } catch (Exception e) {
            e.printStackTrace();
        }
        return false;
    }

    public boolean sacar(int contaId, double valor) {
        try {
            Conta conta = contaDAO.findById(contaId);
            if (conta != null && conta.getSaldo() >= valor) {
                conta.sacar(valor);
                contaDAO.update(conta);

                Transacao transacao = new Transacao("SAQUE", valor, conta);
                transacaoDAO.save(transacao);

                return true;
            }
        } catch (Exception e) {
            e.printStackTrace();
        }
        return false;
    }
}
```

---

### 4. `RelatorioController` para Geração de Relatórios

A `RelatorioController` gerencia a geração de relatórios financeiros e interage com o DAO de `Relatorio`.

#### `RelatorioController`

```java
package org.swing.controller;

import org.swing.dao.RelatorioDAO;
import org.swing.model.Relatorio;

import java.util.List;

public class RelatorioController {
    private final RelatorioDAO relatorioDAO;

    public RelatorioController() {
        this.relatorioDAO = new RelatorioDAO();
    }

    public List<Relatorio> gerarRelatorios() {
        return relatorioDAO.findAll();
    }

    public boolean gerarRelatorioMovimentacoes(String tipoRelatorio, String conteudo) {
        try {
            Relatorio relatorio = new Relatorio(tipoRelatorio, conteudo);
            relatorioDAO.save(relatorio);
            return true;
        } catch (Exception e) {
            e.printStackTrace();
            return false;
        }
    }
}
```

---

### 5. Exemplo de `View` com Swing: `LoginView`

Agora, vamos criar uma `View` simples usando `Swing` para o login.

#### `LoginView`

```java
package org.swing.view;

import org.swing.controller.UsuarioController;
import org.swing.model.Usuario;

import javax.swing.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class LoginView extends JFrame {
    private final UsuarioController usuarioController = new UsuarioController();

    public LoginView() {
        setTitle("Login");
        setSize(300, 200);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setLocationRelativeTo(null);

        JPanel panel = new JPanel();
        add(panel);
        placeComponents(panel);

        setVisible(true);
    }

    private void placeComponents(JPanel panel) {
        panel.setLayout(null);

        JLabel userLabel = new JLabel("CPF:");
        userLabel.setBounds(10, 20, 80, 25);
        panel.add(userLabel);

        JTextField userText = new JTextField(20);
        userText.setBounds(100, 20, 165, 25);
        panel.add(userText);

        JLabel passwordLabel = new JLabel("Senha:");
        passwordLabel.setBounds(10, 50, 80, 25);
        panel.add(passwordLabel);

        JPasswordField passwordText = new JPasswordField(20);
        passwordText.setBounds(100, 50, 165, 25);
        panel.add(passwordText);

        JButton loginButton = new JButton("Login");
        loginButton.setBounds(10, 80, 80, 25);
        panel.add(loginButton);

        loginButton.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                String cpf = userText.getText();
                String senha = new String(passwordText.getPassword());
                
                Usuario usuario = usuarioController.autenticar(cpf, senha);
                if (usuario != null) {
                    JOptionPane.showMessageDialog(null, "Login bem-sucedido!");
                    // Aqui você pode abrir a próxima tela baseada no tipo de usuário
                } else {
                    JOptionPane.showMessageDialog(null, "CPF ou senha incorretos!");
                }
            }
        });
    }

    public static void main(String[] args) {
        new LoginView();
    }
}
```

---

Este é o ponto de partida para suas `Controllers` e `Views`. Você pode expandir cada `View` e adicionar as funcionalidades de acordo com as operações definidas no projeto, como visualização de saldo, depósito, saque, cadastro de cliente e contas. Cada operação na `View` pode chamar métodos da `Controller` para interagir com os DAOs e o banco de dados.