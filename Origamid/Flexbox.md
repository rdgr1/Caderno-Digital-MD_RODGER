### Flex Container
- *Display*
	Define o elemento como um flex container, tornando os seus filhos flex-itens. 
```css	
 display:flex;
//Torna o elemento um flex container automaticamente transformando         todos os seus filhos em flex-itens. 
``` 

- *Flex-Direction*
	Define a direção dos flex itens. Por padrão ele é row (linha), por isso quando o display: flex; é adicionado, os elementos ficam em linhas, um do lado do outro.

	A mudança de row pra column geralmente acontece qunado estamos definindo os estilos em media queries para mobile. Assim você garante que o conteúdo seja apresentado em coluna única.

```css
flex-direction:row;
// Os itens ficam em linha

flex-direction:reverse-row;
// Os itens ficam em linha reversa, ou seja 3,2,1.

flex-direction:column;
// Os itens ficam em uma unica coluna, um embaixo do outro.

flex-direction:column-reverse;
// Os itens ficam em uma unica coluna, um embaixo do outro, porem em        ordem reversa, ou seja 3,2,1.
```

- *Flex-Wrap*
Define se os itens devem quebrar ou não a linha. Por padrão eles não quebram linhas, isso faz com que os flex itens sejam compactados além do limite do conteúdo.

Essa é geralmente uma propriedade que é quase sempre definida como flex-wrap: wrap; Pois quando um dos flex itens atinge o limite do conteúdo, o último item passa para a coluna debaixo e assim por diante.

```css
flex-wrap: nowrap;
//Valor padrao
flex-wrap:wrap;
//Quebra a linha assim que um dos flex intens nao puder mais ser compactado
flex-wrap:wrap-reverse;
//Quebra as linhas na direcao contraria do wrap
```