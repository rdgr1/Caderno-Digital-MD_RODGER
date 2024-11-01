# Tutorial Rápido de Interface com Swing

  

Para criar uma interface gráfica em Java usando **Swing**, vamos explorar alguns conceitos básicos e componentes essenciais. Swing é uma biblioteca gráfica nativa do Java que facilita a criação de janelas, botões, campos de texto e outros elementos visuais.

  

## - 1. . Criando Janelas com JFrame

  

Para iniciar uma interface, criamos uma janela principal usando JFrame.

  

```java

public class MinhaJanela extends Jframe {

    public MinhaJanela(){

        setTitle("Minha aplicação Swing");

        setSize(400, 300);

        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

        setLocationRelativeTo(null); //Centraliza a Janela

    }

    public static void main(String[] args){

    SwingUtilities.invokeLater(() -> {

        MinhaJanela frame = new MinhaJanela();

        frame.setVisible(true);

        });

    }

}

```

  

### Organizando Componentes com JPanel e Layouts

  

O JPanel é usado para organizar componentes como botões e campos de texto dentro do JFrame. Usamos diferentes layouts (como FlowLayout, GridLayout, BorderLayout) para posicionar os componentes na tela.

  

```java

Jpanel panel = new Jpanel();

panel.setLayout(new Flatlayout());

  

add

  

add(label);

(textField);

add(panel);(buttom);

```

  
  
  

### Adicionando Componentes Básicos

  

Swing possui diversos componentes, como:

  

- **JLabel**: Exibe texto.

- **JTextField**: Campo para entrada de texto.

- **JPasswordField**: Campo para entrada de senha.

- **JButton:** Botão para executar ações.

  

**Exemplo**:

  

```java

JLabel label = new Jlabel("Usuário:");

JTextField textField = new JTextField(20);

JButton button = new Jbutton("Entrar");

  

panel.add(label);

panel.add(textField);

panel.add(buttom);

```

  

### Adicionando Ações aos Botões com ActionListener

  

Para responder a cliques em botões, usamos o ActionListener, que permite associar uma ação ao clique do usuário

  

```java

buttom.addActionListener(e -> {

    String usuario = textField.getText();

    JOptionPane.showMessageDialog(this,"Bem vindo" + usuario + "!")

});

```

  

### Usando Caixas de Diálogo com JOptionPane

  

O JOptionPane permite criar caixas de diálogo simples para exibir mensagens ou capturar entradas.

- Mostrar uma mensagem:

```java

JOptionPane.showMessageDialog(null,"Mensagem de boas-vindas!");

```

**Mostrar uma pergunta e capturar a resposta:**

```java

String resposta = JOptionPane.showInputDialog("Qual o seu nome?");

```

![[LogicScreen_Java.png]]

  

**Próximos Passos para o Projeto**

Para o projeto do Banco Malvader, vocês usarão esse conhecimento para criar menus e telas adicionais, conectando-as à lógica da aplicação. Experimente criar:

- Menus com Botões para as funcionalidades.

- Formulários de entrada para capturar dados dos usuários.

- Caixas de Diálogo para exibir mensagens e confirmações.

  

Pessoal, essas ferramentas vão permitir que vocês criem uma interface gráfica interativa para o sistema de banco, integrando funcionalidades conforme solicitado no projeto.

Vamos lá, vocês conseguem.

  

**F. Passo a Passo para Configuração**

- **1. Configuração da Conexão Java com MySQL**

- 1.    Baixe o Driver JDBC MySQL:

- 1.1.  Acesse o site oficial do MySQL e baixe o driver JDBC (arquivo .jar).

- 2.    Adicione o Driver ao Projeto:

- 2.1.  No ambiente de desenvolvimento (Eclipse), vá até as configurações do projeto e adicione o .jar do driver JDBC ao classpath do projeto.

- 3.    Configuração da Classe de Conexão (ConnectionFactory):

- 3.1.  Crie a classe ConnectionFactory no pacote dao.

- 3.2.  No método de conexão, utilize o seguinte código para estabelecer a conexão:
![[ConncetionFactory.png]]


- **2.**      **Implementação da Aplicação**

1. **Desenvolvimento dos Modelos (Pacote model)**:

- Defina classes de modelo (e.g., Funcionario, Cliente, Conta) que representem as tabelas no banco de dados.
- Cada classe deve conter atributos correspondentes às colunas e métodos getters e setters.

3. **Implementação dos DAOs (Pacote dao)**:

- Em cada DAO, crie métodos como save(), update(), delete(), e findById() para manipular as informações.
- Exemplo de método de inserção em FuncionarioDAO:

![[Pasted image 20241101202059.png]]

1.      **Criação da Interface Gráfica (Pacote view)**:

- Implemente telas Swing para cada funcionalidade (Cadastro, Consulta, Relatórios, etc.).
- Utilize o JFrame como janela principal e adicione componentes como JButton, JTextField, e JTable conforme necessário.

2.      **Desenvolvimento dos Controladores (Pacote controller)**:

- Em cada controlador, implemente a lógica de negócios que será usada para chamar métodos dos DAOs a partir da interface gráfica.
- Exemplo de método no FuncionarioController:

![[Pasted image 20241101202115.png]]

