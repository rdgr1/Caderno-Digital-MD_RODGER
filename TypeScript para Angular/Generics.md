## Case:
```typescript
function concatArray(...itens: any):any[]{
	return new Array().concat(...itens);
}
const numArray = concatArray<number[]>([1,5],[3])
const strArray = concatArray<string[]>(["Niltin","ZéCa"])

numArray.push("Saitama");
console.log(numArray);
console.log(strArray);
```

Para não o ocorrer a injeção de tipo não explicitos ou erros usamos o generic types que são chamados como no exemplo abaixo substituindo o tipo any

```typescript
function concatArray<T>(...itens:T[]): T[]{
	return new Array().concat(...itens);
}
const numArray = concatArray<number[]>([1,5],[3]);
const stgArray = concatArray<string[]>(["Niltin do vrau","zeno"],["Epicuro"])
```

Como estavamos usando um tipo any os arrays quando utilizados pelo metodos aceitavam qualquer tipo de tipo mesmo sendo declarado um array de um tipo, com uso de generics é possivel forçar que o array so receba dados do seu tipo de criação.

