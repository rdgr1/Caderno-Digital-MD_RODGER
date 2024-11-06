## Endpoint x API
**Endpoint** - é um ponto de extremidade de uma API onde outros podem ter acesso aos recursos a serem disponibilizados. 

### Para o funcionamento dos Endpoints
## Criar a Model
```java
//Anotação do Lombok para Criação Autómatica de Requisitos para um DATA
@Data
//Definindo a Entidade
@Entity
@Table(name="TB_EXAMPLE")
public class ProdutoExample{
//Denominando o Id
@Id
//Geração Automática de ID
@GeneratedValue(strategy= GenerationType.AUTO)
private Long id;
//Definindo Validação de Atributos sem DTO
@Column(nullable=false,unique=true)
private String name;
@Column(nullable=false)
private double preco;
private String descricao;
}
```

### Criar o Repository para Salvamento  na Base de Dados
```java
public interface ExampleRepository extends
JpaRepository<ProdutoExample,Long>
{
}
```

### Cria nossa Camada de Serviço 
```java
@Service
public class ExampleService{
	//Injentando Repository pra salvar no Banco de Dados
	@AutoWired
	ExampleRepository exampleRepository;
	//Método Salvar
	public ProdutoExample save(ProdutoExample pe){
		return exampleRepository.save(pe);
	}
	//Método Find By Id
	public ProdutoExample findById(Long id){
		return exampleRepository.findById(id);
	}
	//Método para Listar Todos
	public ProdutoExample listAll(){
		return exampleRepository.findAll();
	}
}
```

### Criar Nossa Controller 
```java
@RestController
@ResquestMapping(name="/example")
public class exampleController{
	@AutoWired
	ExampleService exampleService;

	@PostMapping
	public ResponseEntity<ExampleModel>(@RequestBody ExampleModel exampleModel){
	return ReponseEntity.status(HttpStatus.OK).body(exampleService.save(exampleModel))
	}
}
```

