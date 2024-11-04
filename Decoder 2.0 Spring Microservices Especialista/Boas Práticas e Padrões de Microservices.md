## Evolução Arquitetural 
- Sistema Monolítico
	*Frontend* + *Backend*
- Arquitetura de Microservices
	**Frontend** - *microserviceA* + *microserviceX* + *microserviceB* + *microservice?*
- MicroFrontend + Microservice
	**micro-frontends + microservices**

Arquitetura de Microservices é uma solução as limitações dos sistemas monolíticos.
### Principais Benefícios dos Microservices
- ==Manutenibilidade :LiSettings:==
- ==Alta Disponibilidade:LiWifi:==
- ==Flexibilidade Tecnológica:LiShuffle:== 
- ==Independência das Equipes:RaDoubleTeam:== 
- ==Melhor Performance:RaFastShip:==
- ==Divisão da Complexidade do Negócio:LiNetwork:==
- ==Isolamento a Falhas:LiBadgeX:== 
- ==Alta Escalabilidade:LiArrowUp:== 
- ==Baixo Acoplamento:LiArrowBigDown:== 
- ==Melhor Testabilidade:LiTestTubeDiagonal:== 
- ==Agilidade nas Mudanças:LiAlarmPlus:== 
- ==Isolamento Modelagem de Dados:SiBytedance:==
- ==Aumento Resiliência:SiUndertale:==
#### Arquitetura de Microservices é um modo flexível e sustentável
Modelo que mais facilmente é capaz de acompanhar as frenéticas mudanças dis negócios e as modernizações tecnológicas.

#### Boas práticas e Padrões na modelagem de uma Arquitetura de Microservices com Spring 
##### Modelagem na Pŕatica 
	- Sistema EAD Educação a Distância:
### Microservices de Negócios
	- Divisão de Negócios em Microservices

##### Sistema EAD Domain
1. **User Service** 
2. **Notification Service**
3. **Payment Service**
4. **Course Service**
---
![[Pasted image 20241104135834.png]]

### Modelando o padrão API Gateway
![[Pasted image 20241104141400.png]]

![[Pasted image 20241104141516.png]]
O API Gateway vai ser um centralizador de todas as requisições.
![[Pasted image 20241104141810.png]]

### Spring Cloud Gateway
-  Inserido na versão 5 do Spring Framework
- Baseado no projeto Reactor
- Suporta Progamação Reativa
- Servlet Container: Servidor Netty
- Roteamento para APIs, definição de filtros de predicados
- Integração com Service Registry para registros e descoberta de serviços 
- Limitação de taxa de solicitção
![[Pasted image 20241104142342.png]]*Service Registry*  também é uma Microservice de Configuração assim como o API Gateway, suprindo as preocupações transversais ele utiliza o padrão `Service Registry Data`.
![[Pasted image 20241104142458.png]]
Utilizando o Spring Cloud Netflix Eureka e utilizar seu painel para observalidade dos microservices e seu uso e junto com LoadBalancer fazer o balanceamento de recursos dos microserviços.
![[Pasted image 20241104142936.png]]
O padrão Global Configuration também é responsavel por serviços transversais respectivos a eles assim como service registry
![[Pasted image 20241104143710.png]]

![[Pasted image 20241104144417.png]]
### Spring Cloud Config
- Suporte para configuração externa em uma arquitetura de Microservices
- Utiliza do Git para armazenamento e versionamento das propriedades
- APIs para consultas de propriedade
- Suporta uso de @Value 
- Config Server para gerenciar configurações de múltiplos ambientes
- Criptografia e Descriptografia de  valores de propriedades

## Padroẽs de Observalidade em Microservices
![[Pasted image 20241104144921.png]]
Todos os logs irão para uma base de dados específica para melhor controle e observabilidade do nosso sistema ou aplicação
![[Pasted image 20241104145221.png]]
Utilizaremos Logback/Log4js com spring para esse controle
![[Pasted image 20241104145317.png]]
Utilizaremos a plataforma elastic para armazenamento de logs e utilizarmo da elastic search.
![[Pasted image 20241104145537.png]]
Utilizaremos Spring Actuator para observabilidade de métricas e health dos nosso microserviços
![[Pasted image 20241104145831.png]]
e para o rastreamento dos serviços com id macro e micro dentro da arquitetura garantindo uma boa rastreabilidade
![[Pasted image 20241104150030.png]]
Benefícios do Spring Observability
![[Pasted image 20241104150109.png]]
Para evitar possíveis falhas em cascata no contexto de comunicação sincrona entre os microservices utilizaremos circuit breaker para maior **Resiliência de Microserviço**.
![[Pasted image 20241104150516.png]]
e dentro do ecossistema spring utiliaremos o Spring Circuit Breaker para essa função.
![[Pasted image 20241104150528.png]]
### Padrões de Autenticação e Autorização em Microservices
## Modelo 1 
![[Pasted image 20241104150812.png]]
## Modelo 2:
![[Pasted image 20241104150936.png]]
Contamos com Spring Security para esse dois modelos 
![[Pasted image 20241104151234.png]]
### Spring Security 
#### Benefícios:
- Projeot que fornece autenticação e autorização para aplicações Java
- Suporte parar implementação de Basic Authentication em memória e em database, JWT e OAuth

# Arquitetura Completa 
![[Pasted image 20241104151537.png]]
### Padrões dentro da Arquitetura:
- **API Gateway**
- **Registry Descovery**
- **Global Configurate**
- **Observabilidade**
- **Resiliência**
- **Autenticação e Autorização**

### Overview de Projetos Spring Inclusos nos Padrões
![[Pasted image 20241104152007.png]]

