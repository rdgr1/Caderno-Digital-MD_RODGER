### Tabelas: 
Ela é usada para *armazenar dados* de forma organizada.
Cada *tabela* em um banco de dados relacional tem um **nome único** e é dividida em *colunas e linhas*.

### Colunas:
Uma coluna é uma *estrutura* dentro de uma tabela que representa um atributo **especifíco** dos dados armazenados.
Cada coluna tem um **nome único** e um **tipo de dados** associado que define o **tipo de informação** que pode ser armazenado nela, como *números, textos, datas, etc.*

### Registros:
Um *registro*, também conhecido como **linha ou tupla**, é uma instância **individual** de dados em uma **tabela**.

### Tipo de dados
Os dados podem variar muito entre os diversos SGBD, os mais comuns são:
-  Inteiro(**Integer**)
- Decimal/Numérico(**Decimal/Numeric**)
- Caractere/Varchar(**Character/Numeric**)
- Data/Hora(**Date/Time**)
- Booleano(**Boolean**)
- Texto longo(**Text**)
### Comandos:

#### Create -->
```sql
CREATE TABLE {{nome}}
	({{coluna}}{{tipo}}{{opções}} COMMENT
	{{´COMENTARIO´}});
```

#### Opções -->
- **Retrições** de Valor:
- NOT NULL
- UNIQUE 
- DEFAULT 
- Chaves **primárias** e **estrangeiras**.
- Auto Incremento
### 
