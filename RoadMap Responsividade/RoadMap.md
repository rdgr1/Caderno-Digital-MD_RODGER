## 🛠️ para Responsividade do Projeto

## 📌 1️⃣ Estratégia Geral

- **Mobile First:** Criar a base do layout para telas pequenas e depois adaptar para telas maiores.

- **Utilizar CSS Grid em layouts estruturais** (seções grandes).

- **Utilizar Flexbox para alinhar elementos menores** dentro dessas seções.
---  

## 📌 2️⃣ Onde usar Grid Layout? 🟢

Usaremos **CSS Grid** onde o layout precisa de **colunas e linhas bem definidas**, melhorando a organização do conteúdo.

🔹 **Seções onde Grid será aplicado:**

- ✅ `project-layout.component.scss` → Exibir projetos em colunas organizadas

- ✅ `sobre-mim.component.scss` → Estruturar a seção de "Sobre Mim" com texto e imagem lado a lado

- ✅ `card-projeto.component.scss` → Distribuir os cards dos projetos dinamicamente

- ✅ `formulario-layout.component.scss` → Organizar os campos do formulário de forma mais alinhada

📌 **Exemplo de estrutura com Grid:**

```scss

.container {

  display: grid;

  grid-template-columns: 1fr;

  gap: 20px;

  

  @media (min-width: 768px) {

    grid-template-columns: repeat(2, 1fr);

  }

  

  @media (min-width: 1024px) {

    grid-template-columns: repeat(3, 1fr);

  }

}

```

---  
## 📌 3️⃣ Onde usar Flexbox? 🔵

Usaremos **Flexbox** para alinhar elementos dentro de **containers menores**, onde a flexibilidade do conteúdo é necessária.

🔹 **Seções onde Flexbox será aplicado:**

- ✅ `nav-bar.component.scss` → Alinhamento horizontal da navbar e dos itens do menu

- ✅ `header-index.component.scss` → Para alinhar elementos do cabeçalho (logo, título, etc.)

- ✅ `card-projeto.component.scss` → Dentro de cada card, alinhar itens (imagem, título, botão)

- ✅ `formulario-layout.component.scss` → Alinhar rótulos e campos de entrada

📌 **Exemplo de estrutura com Flexbox:**

```scss

.container {

  display: flex;

  justify-content: center;

  align-items: center;

  gap: 20px;

}

```

---

## 📌 4️⃣ Ordem de Implementação 📝

1️⃣ **Navbar (`nav-bar.component.scss`)** → Corrigir layout e adicionar menu responsivo  

2️⃣ **Seção Sobre Mim (`sobre-mim.component.scss`)** → Ajustar texto + imagem com Grid  

3️⃣ **Seção Projetos (`project-layout.component.scss`)** → Criar estrutura dinâmica em Grid  

4️⃣ **Cards de Projetos (`card-projeto.component.scss`)** → Ajustar espaçamentos e alinhamento interno com Flexbox  

5️⃣ **Formulário de Contato (`formulario-layout.component.scss`)** → Melhorar layout para telas menores  

6️⃣ **Ajustes Finais & Testes** 🚀  

---  

## 📌 5️⃣ Checklist Final 🔎

✅ Mobile First aplicado corretamente  

✅ Grid Layout nas seções principais  

✅ Flexbox para alinhamento interno de elementos  

✅ Testar responsividade em diferentes tamanhos de tela  

✅ Ajustes finais de espaçamentos e overflow
