## Repository Pattern
**Repository** é um padrão de projeto similar ao DAO(Data Acess Object) no sentido de que seu objetivo é abstrair o acesso a dados de forma genérica a partir do seu modelo.

### Spring Data Jpa 
O projeto **Spring Data Jpa** facilita a implementação do padrão **Repository** através de AOP(Aspect Oriented Proggamming).

Utilizando-se apenas de uma interface, o Spring irá "gerar" dinamicamente a implementação dos métodos de acesso aos dados. Estender a Interface `JpaRepository` é opcional. mas a vantagem é ela já vem com vários métodos genéricos de CRUD e você não precisa redefinir todos eles.

Principais métodos disponibilizados pelo framework.
- `save`: Insere e atualiza os dados de uma entidade 
- `findById` : Retorna o objeto localizado pelo seu ID
- `existsById`: Retorna um boolean localizando o ID
- `findAll`: Retorna uma coleção contendo todos os registros da tabela no banco de dados 
- `delete` : Deleta um registro da respectiva base de dados.
- `count`: Retorna a quantidade de registros de uma tabela mapeada do banco de dados.

> :LiInfo:  **E a implementação?** O Spring Data JPA se encarrega se realizar a implementação através do padrão CRUD.
> 

#### Consultas Customizadas
Existem duas maneiras de realizar consultas customizadas, uma é conhecida como `QueryMethod` e a outra é `QueryOverride`.

##### Query Method
O Spring Data JPA se encarrega de interpretar a assinatura de um método (nome+parâmetros) para montar a **JQPL** correspondente.

Vamos um exemplo de um entidade que possui um endereço de email e sobrenome e gostaria de filtrar por estes dois atributos.
```java
public interface UserRepository extends Repository<User,Long> {
	List<User> findByEmailAddressAndLastName(String emailAdress, 
	String lastname);
}
```

##### Query Override

Vamos imaginar que você precisar montar uma query um tanto avançada mas ficaria inviável utilizar o padrão **QueryMethod**? Como nossos repositórios são interfaces não temos implementação de código, é ai que precisar definir a consulta de forma manual através da anotação `@Query`.

Os dois métodos realizam a mesma instrução SQL, consultando os usuários pelo seu campo **name** comparando com o operador **LIKE** do SQL.

```java
public interface UserRepository extends JpaRepository<User, Integer> {
  
  // Query Method - Retorna a lista de usuários contendo a parte do name
  List<User> findByNameContaining(String name);

  // Query Override - Retorna a lista de usuários contendo a parte do nome
  @Query("SELECT u FROM User u WHERE u.name LIKE %:name%")
  List<User> filtrarPorNome(@Param("name") String name);

  // Query Method - Retorna um usuário pelo campo username
  User findByUsername(String username);
}
```

