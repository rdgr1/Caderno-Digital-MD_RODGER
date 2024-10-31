## Introdução
O Spring Data JPA adiciona uma camada sobre o JPA. Isso significa que todos os recursos definidos pela especificação JPA, especialmente os mapeamentos de entidades e os recursos de perssitência baseado em interfaces e anotações. Por isso o Spring Data JPA adiciona seus próprios recursos, como uma implementação sem código por padrão de repositório e a criação de consultas de banco de dados a partir de nomes e métodos.

A partir de agora nossa interação com banco de dados será através de herança de interfaces e declaração de métodos com anotações

Existem algumas interfaces e anotações que são super relevantes de se explorar como:

###### Interfaces:
- CrudRepository
- JPARepository
- PagingAndSortingRepository
###### Anotações:
@Query
@Param

### Exemplo simples de Mapeamento sem JPA Framework
- #### UserModel.java
```java
//Definindo nossa entidade
@Entity
//Definindo nome da nossa tabela
@Table(name="TB-USER")
public class UserModel {
//Definindo nosso id e suas estratégia de geração
	@Id
	@GeneratedValue(strategy=GenerationType.IDENTITY)
	//Utilizando a anotação column para especificar o nome da coluna.
	@Column(name="user-id")
	private Integer id;
	//Definindo com o column limite de caracteres e que os campos não 
	//devem ser nulos.
	@Column(length=50,nullable=false)
	private String name;
	@Column(length=20,nullable=false)
	private String username;
	@Column(length=100,nullable=false)
	private String password;
}
```
### Uso com Repository
```java
public interface UserRepository extends JpaRepository<User,Integer>{
}
```

