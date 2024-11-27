Os Flex itens são filhos diretos do Flex Container, lembrando que uma tag se torna um flex container a partir do momento que você definir display: flex

É possível que um Flex Item seja também um Flex Container, basta definir display: flex

- *Flex-Grow*
Define a habilidade de um flex item de crescer. Por padrão o valor é zero, assim os flex itens ocupam o tamanho máximo relacionado o contéudo interno deles ou o width definido

![[Pasted image 20241127150250.png]]
- *Flex-Basis*
Indica o tamanho inicial do flex item antes da distribuição do espaço restante.
Quando definimos o flex-grow: 1, e possuímos auto no basis, o valo restante para ocupar o container é distribuído ao redor do conteúdo do flex-item.

![[Pasted image 20241127150747.png]]

- *Flex*
Atalho para as propriedades flex-grow,flex-shrink e flex-basis. Geralmente você verá a propriedade flex nos flex itens ao invés de cada um dos valores separados.

![[Pasted image 20241127152909.png]]
- *Align-Self*
O align self serve para definirmos o alinhamento específico de um único flex item dentro do nosso container. Caso um valor seja atribuido, ele passara por cima do que for atrbuído no align-items do container
![[Pasted image 20241127153520.png]]