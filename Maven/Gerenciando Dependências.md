## Tipos de dependência:
- **Direta:** dependências *declaradas* no **pom.xml.**
- **Transitiva:** dependências *obrigatórias* das dependências declaradas no **pom.xml.** 
### Escopos 
- Para lidar com problemas de escopo relacionados a transitividade, O Maven provê escopos para limitar a transitividade das dependências. Existem 6 tipos de escopos que podemos utilizar.
#### Classpath
- Runtime 
- Test 
- Compile 
##### Escopo compile 
- Escopo default 
- Disponível em todos os classpaths
- É transitivo
```xml
<dependency>
	<groupId>org.hibernate</groupId>
	<artifactId>hibernate-search-orm</artifactId>
	<version>5.11.9.Final</version>
	<scope>compile</scope>
</dependency>
```
##### Escopo provided 
- Indica que a dependência será fornecida em tempo de execução por uma implementação na JDK ou via container 
- Exemplos: Servlet API, Java EE APIs
- A dependência com esse escopo é adicionado no classpath usado para compilação (compile) e teste(test) mas não em runtime;
- Não é transitiva
```xml
<dependency>
	<groupId>org.hibernate</groupId>
	<artifactId>hibernate-search-orm</artifactId>
	<version>5.11.9.Final</version>
	<scope>provided</scope>
</dependency>
```
##### Escopo runtime 
- Indica que a dependência é necessária para execução e não para compilação
- Maven inclui no classpath dos escopos de runtime e test 
```xml
<dependency>
	<groupId>org.hibernate</groupId>
	<artifactId>hibernate-search-orm</artifactId>
	<version>5.11.9.Final</version>
	<scope>runtime</scope>
</dependency>
```
##### Escopo test 
- Disponível somente para compilação e execução de testes
- Não é transitivo
```xml
<dependency>
	<groupId>org.hibernate</groupId>
	<artifactId>hibernate-search-orm</artifactId>
	<version>5.11.9.Final</version>
	<scope>test</scope>
</dependency>
```

##### Escopo System
- Similar ao escopo provided exceto por ser necessário prover o JAR explicitamente
- A dependência com esse escopo é adicionado no classpath usado para compilação (compile) e teste(test) mas não em runtime;
- Não é transitiva 
```xml
<dependency>
	<groupId>org.hibernate</groupId>
	<artifactId>hibernate-search-orm</artifactId>
	<version>5.11.9.Final</version>
	<scope>system</scope>
	<systemPath>${project.basedir}/libs/custom-dependency-1.3.2.jar</systemPath>
</dependency>
```
