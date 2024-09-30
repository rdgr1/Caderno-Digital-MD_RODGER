
- ### Oque é:
Framework open source desenvolvido para  a plataforma Java baseado nos padrões de projeto de inversão de controle e injeção de dependência.

Sua estrutura é composta por módulos afins de reduzir a complexidade no desenvolvimento aplicações simples ou corporativa

### Spring Módulos 

![[Pasted image 20240930154758.png]]

### Spring vs Java EE

Olhando um pouco a história, há muito, mas muito tempo atrás, O Java EE era realmente muito complicado e nem era necessário entrar numa discussão, usar o Spring era um caminho mais simples e mais fácil de evoluir, Ai chegou a versão 5 do Java EE e a discussão voltou a ficar um pouco mais quente.

### Inversão de Controle 

Inversion of Control ou IoC, trata-se de redirecionamento do fluxo de execução de um código retirando parcialmente o controle sobre ele e delegando para um container.
O principal propósito é minimizar o acoplamento do código.

### Injeção de Dependências 
Injeção de dependência é um padrão de desenvolvimento com a finalidade de manter o baixo nível de acoplamento entre módulos de um sistema.

### Beans 
Objeto que é instanciado (criado), montado e gerenciado por uma container através do princípio da inversão de controle.

### Singleton 
O contêiner do Spring IoC define apenas uma instância do objeto

### Prototype 
Será criado um novo objeto a cada solicitação ao container. 

### HTTP - Request

Um bean será criado para cada requisição HTTP.
*Os objetos existirão enquanto a requisição estiver em execução.*

### HTTP - Session 

Um bean será criado para a sessão de usuário.
*Precisamos acessar a mesma solicitação duas vezes para testar os escopos específicos da web.*

### HTTP - Global 

Ou Application Scope cria um bean para o ciclo de vida do contexto da aplicação.
*Objetos compartilhados por toda aplicação.*

### Autowired 
Uma *anotação* (indicação) onde deverá ocorrer uma injeção automática de dependência.
- **byName**: É buscado um método set que corresponde ao nome do Bean.
- **byType**: É considerado o tipo de classe para inclusão do Bean.
- **byConstrutor**: Usamos o construtor para incluir a dependência.

