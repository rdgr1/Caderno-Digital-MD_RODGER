### Níveis de Teste
- 1. *Unidade* - Testar partes isoladas do código, como funções ou métodos.
	- 2. *Integração* - Verificar se diferentes módulos ou componentes funcionam bem juntos.
		- 3. *Sistema* - Testar o sistema como um todo, em um ambiente que simula o uso real.
			- 4. *Regressão* - Garantir que mudanças no código (novas funcionalidades, correções) não introduzam novos defeitos.
				- 5. *Aceitação* -  Validar se o sistema atende aos requisitos e expectativas do cliente ou usuário final.
- ***Alpha***
	- **Fase:** Teste inicial feito antes de liberar o software ao público.
	- **Objetivo:** Identificar bugs e falhas grosseiras em um ambiente controlado.
	- **Quem participa:** Normalmente, apenas a equipe de desenvolvimento ou um grupo restrito de testadores internos.
	- **Exemplo:** Um software em versão Alpha pode ser instável e com funcionalidades incompletas, mas está em fase de testes internos.
- ***Beta***
	- - **Fase:** Lançamento após o Alpha, quando o software está mais estável e é oferecido a um grupo maior de usuários.
	- **Objetivo:** Testar o software em um ambiente mais real, com um público maior, para identificar problemas que não surgiram no Alpha.
	- **Quem participa:** Geralmente, usuários externos que aceitam participar do teste.
	- **Exemplo:** Um aplicativo de redes sociais pode liberar uma versão Beta para seus usuários antes do lançamento oficial, buscando feedback e relatórios de bugs.
- ***Cannary***
	-  **Fase:** Técnica de lançamento progressivo de software, onde novas versões são liberadas para um pequeno grupo de usuários antes de serem liberadas para todos.
	- **Objetivo:** Monitorar e identificar problemas em um grupo menor, antes de uma liberação ampla, minimizando o impacto de bugs.
	- **Quem participa:** Um subconjunto de usuários que recebem a atualização antecipada.
	- **Exemplo:** Um provedor de serviços de streaming pode lançar uma atualização de sua plataforma primeiro para 5% dos usuários antes de liberar para todos, monitorando o comportamento em tempo real.

## Técnicas de Teste
- Caixa **Branca**
	Conhecer o programa de forma estrutural, codando e entendendo a fundo seus conceitos 
	- Também conhecido como **Teste Estrutural**
	- Validar dados, controle, fluxos, chamadas
	- Garantir a qualidade da implementação
	- Níveis: *Unidade, Integração, Regressão*
- Caixa **Preta**
	Não conhecer oque acontece
	- **Teste Funcional**
	- Verificar Saídas usando vários tipos de entrada
	- Teste sem conhecer a estrutura interna do software
	- Níveis: *Integração, Sistema, Aceitação*
- Caixa **Cinza**
	Uma mescla entre o teste de caixa branca e preta 
	- Analisa parte lógica e também funcionalidade
	- Exemplo: Ter acesso a documentação do funcionamento do código
	- Engenharia Reversa