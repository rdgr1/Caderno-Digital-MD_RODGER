# Introdução
Spring Security é apenas um grupo de filtros de servlet que ajudam você e adicionar autenticação e autorização ao seu aplicativo da web.

## Habilitando Segurança 
Em um projeto Spring Boot Web você precisa somente incluir a dependência no **pom.xml**
```xml
<dependency>  
    <groupId>org.springframework.boot</groupId>  
    <artifactId>spring-boot-starter-actuator</artifactId>  
</dependency>
```

## Autenticação Simples
Como sabemos por padrão o Spring Security habilita um usuário de nome user e gera uma senha aleatoriamente a cada inicialização. Para aplicações em produção esta não é uma abordagem um tanto aconselhável, e é por isso que vamos conhecer algumas configurações de segurança.

### No aplication.properties
O Spring Security verifica se existe alguma configuração de segurança no arquivo **aplication.properties**
```properties
spring.security.user.name=user
spring.security.user.password=user1234
spring.security.user.roles=USERS
```

