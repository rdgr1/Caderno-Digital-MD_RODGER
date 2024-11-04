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
