- Conceito de ciclo de vida de construção
- Conceito e os comandos da ferramenta
- Composto por 3 ciclos de vida 
- Cada ciclo possui fases (Maven Phases)
- Cada fase possui objetivos (Maven Goals)

![[Pasted image 20240918135017.png]]

### Default  Lifecycle
- Principal ciclo
- Responsável pelo deploy local
- Composto por 23 fases

#### Principais Fases:
- validate
- compile 
- test-compile
- test
- integration-test
- package
- install 
- deploy

### Clean Lifecycle 
- Ciclo intermediário
- Responsável pela limpeza do projeto
- Composto por 3 fases
#### Fases
- pre-clean
- clean
- post-clean
### Site Lifecycle 
- Ciclo Final 
- Responsável pela criação do site documentação do projeto
- Composto por 4 fases
#### Fases
- pre-site 
- site 
- post-site
- site-deploy
