# Definição:

Uma *classe* é definida por atributos e métodos. Já vimos que atributos são, em sua grande maioria, variáveis de diferentes tipos e valores. Os métodos, por sua vez correspondem a **funções** ou **sub-rotinas** disponíveis dentro de nossa classes.

## Critérios de nomeação de Métodos

- Deve ser nomeado como **verbo**
- Seguir o padrão *camelCase*.

Exemplo para nomenclatura de métodos:
```java
somar(int n1,int n2){}

abrirConexao(){}

concluirProcessamento() {}

findById(int id){}
```

>⚠️ Não existe em *Java* o conceito de métodos globais. Todos os *métodos* devem SEMPRE ser definidos dentro de uma classe.

## Critérios de definição de Métodos

Para definir métodos de forma eficaz em uma classe, considere os seguintes pontos:
1. **Proposta Principal:** Entenda claramente o propósito do método.
2. **Tipo de Retorno:** Determine se o método deve retornar um valor. User `void` se não houver retorno.
3. **Parâmetros:** Identifique quais argumentos o métodos precisa para funcionar.
4. **Exceções:** Avalie se o método pode gerar exceções e prepare o tratamento adequado.
5. **Visibilidade:** Defina a visibilidade do método (público, protegido, privado) conforme necessário.

*Exemplo:*
```java
public class Exemplo {
	// Método com retorno e parâmetros
	public int somar(int a, int b) {
		return a + b;
	}
}

	// Método sem retorno
	private void imprimirMensagem(String mensagem) {
		System.out.println(mensagem);
	}
```
