### Definição
**Spring Security** é uma biblioteca que fornece *proteção*, *autenticação*, *autorização* e *armazenamento* de senhas. 

### Autenticação
- Usuário e Senha
- OAuth2
- SAML2
- Outros

#### Autorização
Para autorização, o Spring Security se baseia nas Authorities do usuário que se autentica na aplicação

### Proteção 
- Cross Site Request Forgery (CSRF)
- Security HTTP Response Headers
- HTTP
- HTTP Firewall

#### Vantagens 
- Suporta autenticação e autorização
- Proteção contra ataques 
- Integração de API Servlet
- Integração opcional com Spring Web MVC

### Basic Authentication
A autenticação básica é um esquema de autenticação simples integrado ao protocolo HTTP.

Basic **username:password**
Basic **dXNlcm5hbWWU6cGFzc3dvcmQ=**


### JWT 
**JWT** (JSON Web Token) é um *método* para realizar autenticação entre duas partes por meio de um *token*.

### OAuth 2.0
OAuth 2.0 é um protocolo que permite aos usuários ter acesso limitado a recursos de um website sem precisar expor suas credenciais.
## Configurando Estratégias de autenticação
Para utilizar o Spring Security no Ambito de Rest com Spring Web, e necessário criar um pacote `config` que dentro teremos o `SecurityConfig` 

Configuração Inicial do Spring Security
```java
@Configuration // Anotação para indicar que esta é uma classe de configuração
public class SecurityConfig {

    @Bean // Anotação para definir o método como um bean gerenciado pelo Spring
    public SecurityFilterChain securityFilterChain(HttpSecurity http) throws Exception {
        // Configuração de segurança HTTP
        http.csrf().disable() // Desativa a proteção CSRF
            .authorizeHttpRequests(auth -> auth.anyRequest().authenticated()) // Exige autenticação para todas as requisições
            .httpBasic(); // Usa autenticação básica HTTP
        return http.build(); // Retorna a configuração construída
    }

    @Bean // Anotação para definir o método como um bean gerenciado pelo Spring
    public UserDetailsService userDetailsService() {
        // Configuração de autenticação em memória
        UserDetails user = User.builder() // Cria um usuário com as configurações abaixo
            .username("rod777") // Define o nome de usuário
            .password("{noop}12345") // Define a senha (com {noop} para indicar que não é codificada)
            .roles("USER") // Define o papel (role) do usuário
            .build(); // Constrói o objeto UserDetails
        return new InMemoryUserDetailsManager(user); // Retorna o gerenciador de usuários em memória com o usuário configurado
    }
}
```


