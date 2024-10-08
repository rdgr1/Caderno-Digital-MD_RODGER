- Rest com Spring MVC
- Spring Security
- Actuator, Métricas e Health Check
- Spring Boot Test

### Estilo Arquitetura Rest

Um estilo arquitetural é um conceito organizacional, central de um sistema.

*Arquitetura REST*
- 1. Transferência de Estado Representacional
(**Representational State Transfer**).

- 2. Comunicação entre aplicações. 

- 3. Flexibilidade.

### REST e RESTful
- 1. **REST**: representa um apanhado de princípios de arquitetura
- 2. **RESTful**: representa a condição de um sistema específico em aplicar os conceitos REST

### End Points
- Ponto de extremidade 
- Endpoint vs API

### Controle de Exceções 
#### @ControllerAdvice 
O *@ControllerAdvice* é uma anotação, para lidar com as exceções globalmente.

#### @ExceptionHandler
O *@ExceptionHandler* é uma anotação usada para tratar as exceções específicas e enviar as respostas personalizadas ao cliente.

O **Spring Boot Actuator** é um módulo que fornece funcionalidades de monitoramento e gerenciamento para aplicações Spring Boot. Ele expõe endpoints que permitem obter informações sobre o estado da aplicação em execução, métricas, verificações de saúde, logs, além de permitir a interação com a aplicação (como o shutdown).

### Principais funcionalidades:
- **Métricas**: Exposição de métricas detalhadas sobre o uso de memória, threads, execução de consultas SQL, chamadas HTTP, entre outras.
- **Health Checks**: Verifica o estado de saúde da aplicação e de suas dependências, como conexões com banco de dados, serviços externos, etc.
- **Endpoints**: Fornece vários endpoints, como:
  - `/actuator/health`: Verifica o status de saúde da aplicação.
  - `/actuator/metrics`: Exibe métricas da aplicação.
  - `/actuator/env`: Mostra as variáveis de ambiente.
  - `/actuator/loggers`: Permite configurar dinamicamente o nível de logging.
  
### Configuração:
- Adicione a dependência ao **Actuator** no `pom.xml`:
  ```xml
  <dependency>
      <groupId>org.springframework.boot</groupId>
      <artifactId>spring-boot-starter-actuator</artifactId>
  </dependency>
  ```
- Você pode habilitar ou desabilitar endpoints específicos no arquivo `application.properties` ou `application.yml`:
```properties
management.endpoints.web.exposure.include=health,metrics
```

### Segurança:
- Por padrão, muitos endpoints estão desativados para garantir a segurança da aplicação. É recomendável habilitar a segurança, especialmente em produção, para proteger esses endpoints de acessos não autorizados.

O **Spring Boot Actuator** é útil para monitoramento em produção, pois oferece insights essenciais sobre o desempenho e a saúde da aplicação de forma simples e eficiente.

### Spring Boot Admin 
Spring Boot Admin é um projeto da codecentric para Gerenciar e monitorar aplicações Spring boot 

