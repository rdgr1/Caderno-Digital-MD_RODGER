# Entendendo o POM
- *POM* - **Project Object Model** 
- **Unidade** fundamental de *trabalho*
- **Formato** *XML*
- **Detalha** o *projeto*
- **Maven** sempre procura pelo *pom.xml* para realizar sua **execução**
## Principais Contéudos do POM
- Nome do Projeto
- Dependências
- Módulos
- Configurações de build 
- Detalhes do projeto(nome,descrição,liçença,url)
- Configurações de ambiente(repositórios,tracking,profiles)
### Exemplo Básico de Pom.xml
```xml
<project>
	<modelVersion>4.0.0</modelVersion>
	<groupId>com.mycompany.app</groupId>
	<artifactId>my-app</artifactId>
	<version>1.0</version>
</project>
```
#### Repositórios
- São **locais** onde podemos encontrar **plugins** e **bibliotecas** que o *Maven* provê.
- Dois *tipos*: **Local e Remoto.**
#### Repositório Remoto
- É o **local** central utilizado pelo *Maven* para buscar os *artefatos.*
- Configurado automaticamente pelo *Super POM* para utilizar o **Maven Central.**

```xml
<repositories>
	<repository>
		<id>central</id>
		<name>Central Repository </name>
		<url>http://repo.maven.apache.org/maven2</url>
		<layout>default</layout>
		<snapshots>
			<enabled>false</enabled>
		</snapshots>
	<repository>
</repositories>
```

##### Configuração
- *Via* **settings.xml**
- *Localização*: **pasta_apache_maven/conf/settings.xml**

##### Repositório Local
- É o repositório na máquina utilizado pelo Maven para buscar os artefatos
- Estratégia de caching 
- Localizações 
- Windows: %USERPROFILE%\.m2\repository
- Linux? $HOME/.m2/repository
### Dependências 
```xml
<dependency>
	<groupId>org.hibernate</groupId>
	<artifactId>hibernate-search-orm</artifactId>
	<version>5.11.9.Final</version>
</dependency>
```
#### Propriedades
- ``groupId``: É como se fosse o **id** da organização. Segue as regras de nomes de **pacote Java**
- ``artifactId``: Nome do **projeto** em si 
- *Version*: Número da **versão** que será *utilizada*
- 