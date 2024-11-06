## Web Components

Os **Web Components** são uma tecnologia que permite criar componentes reutilizáveis e encapsulados para aplicações web. Eles são parte do **DOM** (Document Object Model) e permitem criar elementos personalizados que podem ser usados de forma semelhante aos elementos HTML nativos. A principal vantagem dos Web Components é que eles permitem isolar a lógica e o estilo de um componente, evitando conflitos com o restante da aplicação.

### Principais Tecnologias de Web Components:

1. **Custom Elements**: Definem novos elementos HTML personalizados.
2. **Shadow DOM**: Cria um DOM encapsulado, onde estilos e scripts não afetam o documento externo.
3. **HTML Templates**: Permitem criar modelos de conteúdo reutilizáveis, que podem ser clonados para inserir no DOM.

### Vantagens:

- **Reutilização**: Componentes podem ser usados em diferentes partes de uma aplicação ou até em outras aplicações.
- **Encapsulamento**: A lógica e o estilo de um Web Component são isolados, evitando interferência com o restante da aplicação.
- **Compatibilidade**: Funcionam nativamente em navegadores modernos, sem necessidade de frameworks.

## Front-End

No desenvolvimento **front-end**, o foco é criar a interface que o usuário interage diretamente. Web Components desempenham um papel importante aqui, pois ajudam a modularizar e organizar o código em componentes menores e mais gerenciáveis.

### Relacionamento com Frameworks:

Web Components podem ser usados em conjunto com frameworks populares, como **React**, **Vue** e **Angular**, ou mesmo de forma independente. Eles oferecem uma solução nativa para modularização de código, mas frameworks ainda podem ser preferidos devido às suas facilidades no gerenciamento de estado e renderização reativa.

## Document Object Model (DOM)

O **DOM** é uma interface de programação para documentos HTML e XML. Ele representa a estrutura do documento como uma árvore de nós, onde cada nó é um elemento, texto ou atributo.

### Manipulação do DOM:

- Com JavaScript, é possível adicionar, remover ou modificar elementos no DOM.
- Bibliotecas como **jQuery** e frameworks modernos (React, Angular, etc.) ajudam a simplificar a manipulação do DOM.
- Através do **Shadow DOM**, é possível criar uma subárvore isolada no DOM, essencial para a criação de Web Components encapsulados.

### Exemplos de APIs para manipulação do DOM:

- `document.querySelector()`
- `document.createElement()`
- `appendChild()`
- `removeChild()`