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

- *Flex-Flow*
O flex-flow é um atalho para as propriedades flex-direction e flex-wrap.

```css
flex-flow: row nowrap;
// Coloca o conteudo em lnha sem quebrar linha.
flex-flow: row wrap;
// Coloca o conteudo em linha quebrando caso estoure a box.
flex-flow: column nowrap;
// Coloca o conteudo em coluna.
```

- *Jusitfy-Content*
Alinha os itens flex no container de acordo com a direção.
![[Pasted image 20241127144917.png]]
- *Align-Itens*
alinha os itens flex de acordo com o eixo do containter.
![[Pasted image 20241127145041.png]]
- *Align-Content*
Alinha as linhas do container em relação ao eixo vertical. A propriedade só funciona se exisitir mais de uma linha de flex-itens. Para isso flex-wrap precisar ser wrap.
Além disso o efeito apenas sera visualizado caso o container seja maior que soma das linhas dos itens 
![[Pasted image 20241127145608.png]]

