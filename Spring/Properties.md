#### Convenção
Dentro do properties podemos além de colocar informações crendencias para conexão com o banco de dados ou saas pode fornecer dados credencias pré-estabelecidos e fora do escopo de funcionamento e regra de negócio da aplicação

Utilizando a notação `@Value`

*Exemplo*:
 Dentro de uma aplicação com sistema de mensagens por email automaticas precisamos do email e senha para o acesso e envio atráves do smtp de email podemos pré-estabecer essas informções e utilizar a notação pra buscar esses valores de forma isolada.

 **aplication.properties**:
```properties
 nome=Empresa Fictícia
 email=noreply.example@gmail.com
 telefones=1184709329,6198217634
```

Utilizando Nosso `@Bean` ou `@Component` e o injetando essa informações:
```java
import ...
@Component 
public class SistemaMensagem implements CommandLineRunner {
	@Value("${nome}")
	private String nome;
	@Value("${email}")
	private String email;
	@Value("${telefones})
	private List<Long> telefones;
}
```

