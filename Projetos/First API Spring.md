### Project Presentation: 
- Spring Boot 3  e Java 17
- Spring Web MVC
- Spring Data JPA 
- Spring Validation
- Spring Hateoas

- CRUD 

#### Modelo de Maturidade de *Richardson*
 >`O Modelo de Maturidade de Richardson, também conhecido como Maturidade REST, é uma forma de avaliar o quão bem uma API Web adere aos princípios REST (Representational State Transfer). O modelo é dividido em quatro níveis:`
 
 O modelo é **dividido** em *quatro níveis*:

- **Nível 0 - O uso de um único endpoint**: A API é um simples serviço HTTP que utiliza apenas um único endpoint, geralmente um POST. As requisições e respostas não seguem um padrão REST.
    
- **Nível 1 - Uso de múltiplos endpoints**: A API expõe diferentes endpoints, mas ainda não utiliza métodos HTTP de forma adequada. Por exemplo, todos os tipos de operação podem ser realizados com POST, sem distinção clara.
    
- **Nível 2 - Uso correto dos métodos HTTP**: A API faz uso dos métodos HTTP (GET, POST, PUT, DELETE) de maneira apropriada, permitindo que os clientes realizem operações CRUD (Create, Read, Update, Delete) de forma mais semântica.
    
- **Nível 3 - HATEOAS (Hypermedia as the Engine of Application State)**: A API não apenas utiliza métodos HTTP corretamente, mas também fornece links (hyperlinks) nos recursos retornados, permitindo que os clientes naveguem pela API de forma dinâmica, conforme as ações disponíveis.