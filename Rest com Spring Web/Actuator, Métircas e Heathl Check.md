## Spring Boot Actuator
### Depêndencia do pom.xml
```xml
<dependency>  
    <groupId>org.springframework.boot</groupId>  
    <artifactId>spring-boot-starter-actuator</artifactId>  
</dependency>
```
### Como utilizar o Actuator?

Depois de adicionar a dependência, o Spring Boot Actuator estará disponível e você poderá acessar os endpoints predefinidos. Para usar os endpoints:

1. **Configuração no `application.properties` ou `application.yml`**: Por padrão, apenas o endpoint `/actuator/health` está habilitado. Se você quiser habilitar todos os endpoints, pode configurar da seguinte forma:
```properties
management.endpoints.web.exposure.include=*
```
2. **Requisições HTTP**: Assim que os endpoints estiverem habilitados, você pode fazer requisições para URI como:

- **`/actuator/health`**: Mostra o estado de saúde do aplicativo.
- **`/actuator/info`**: Exibe informações do projeto (precisa ser configurado com propriedades em `application.properties`).
- **`/actuator/metrics`**: Exibe métricas detalhadas do aplicativo.
- **`/actuator/env`**: Mostra as variáveis de ambiente e propriedades do aplicativo.

Exemplos de URI:
  ```bash
http://localhost:8080/actuator/health http://localhost:8080/actuator/metrics
```
### Configurações de Segurança

Por padrão, os endpoints do Actuator podem estar protegidos. Para abrir acesso em desenvolvimento, adicione a seguinte configuração:
```properties
management.endpoints.web.exposure.include=*
management.endpoint.health.show-details=always
```
E certifique-se de configurar a segurança de forma adequada em produção para proteger informações sensíveis.

### Exemplo de Resposta de `/actuator/health`

Uma chamada ao endpoint `/actuator/health` pode retornar:
```json
{
  "status": "UP"
}
```
Se você configurar detalhes adicionais de saúde, ele pode mostrar informações mais detalhadas sobre o status de componentes individuais do aplicativo.

