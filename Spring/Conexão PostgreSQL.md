Em um projeto Spring Boot toda a parte da configuração fica centralizada no arquivo `application.properties` inclusive configurações de banco. 
### Exemplo básico de um properties
```properties
#Opcional 
spring.jpa.show-sql=true
spring.jpa.hibernate.ddl-auto=update
#update Atualiza o esquema sem remover os dados 
#create Cria o esquema do zero a cada execução, apaga os dados existentes.
#validate Apenas valida o esquema de banco de dados
#Obrigatório de acordo com banco
spring.jpa.database-plataform=org.hibernate.dialect.PostgreSQLDialect
spring.datasource.driverClassName=org.postgresql.Driver
spring.datasource.url=jdbc:postgresql://localhost:5432/seu_db
spring.datasource.username=user
spring.datasource.password=**847
```
### Exemplo de uso do properties em uma aplicação:
```properties
server.port=808*1
spring.datasource.url=jdbc:postgresql://localhost:5***/m******
spring.datasource.username=postgres
spring.datasource.password=9****7
spring.jpa.hibernate.ddl-auto=create
```

## É necessário usar o driver como depêndencia no pom.xml
```xml
<dependecies>
	<dependency>
	<groupId>org.postgresql</groupId>
	<artifactId>postgresql</artifactId>
	<scope>runtime</scope>
	</dependency>
</dependencies>
```

