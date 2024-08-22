 - [x]  Dois parâmetros via terminal em inteiro
- [x] Obter a quantidade de interações e realizar a impressão no console
- [x] Exception se o primeiro parâmetro for maior que o segundo parâmetro, lançar exceção customizada chamada `ParametrosInvalidosException`
*Código base -->*
```java
public class Contador {
	public static void main(String[] args) {
		Scanner terminal = new Scanner(System.in);
		System.out.println("Digite o primeiro parâmetro");
		int parametroUm = terminal.??;
		System.out.println("Digite o segundo parâmetro");
		int parametroDois = terminal.??;
		
		try {
			//chamando o método contendo a lógica de contagem
			contar(parametroUm, parametroDois);
		
		}catch (? exception) {
				//imprimir a mensagem: O segundo parâmetro deve ser maior que o                    primeiro
		}
		
	}
	static void contar(int parametroUm, int parametroDois ) throws ParametrosInvalidosException {
		//validar se parametroUm é MAIOR que parametroDois e lançar a exceção
		
		int contagem = parametroDois - parametroUm;
		//realizar o for para imprimir os números com base na variável contagem
	}
}
```
[[Estruturas Excepcionais#Exceções#Exceções customizadas|Exceções Customizadas]] 
[[POO - Desafio]]
