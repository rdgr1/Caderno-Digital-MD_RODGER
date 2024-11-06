## Oque é ORM ?
Object-Relational-Mapping, é um recurso para aproximar o paradigma da orientação a objetos ao contexto de banco de dados relacional.

O uso da ORM é realizado atráves do mapeamento de objeto para uma tabela por uma biblioteca ou framework.

### Definição de JPA:
JPA é uma especificação baseada em interfaces, que atráves de um framework realiza operações de persistência de objetos em Java.

#### Mapeamento
Para realização do mapeamento é necessário o uso de algumas anotações de mapeamento *JPA*:
- Identificação
- Definição
- Relacionamento 
- Herança
- Persistências
```java
// Definindo nossa Entidade
@Entity
// Definindo como tabela e seu nome
@Table(name="TB-EXAMPLE")
public class UserModel implementes Serializable {
	//Anotação do Lombok para recursos de Database.
	@Data
	//Verifica se os mecanismos de serialização estão funcionando.
	@Serial
	private static final long serialVersionUID = 1L;
	//Cria o nosso id e defini que ele dever automaticamente gerado.
	@Id
	@GeneretadeValue(strategy=GenerationType.AUTO)
	private UUID userID;
	//Podemos definir com essa anotação o nome específico de uma coluna.
	@Column(name="user_name")
	private String name;
	private String email;
	
}
```
