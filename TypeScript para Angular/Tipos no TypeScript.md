### Tipos Primitivo:
- **Boolean**
- **Number**
- **String**

### Exemplos:
```typescript
let ligado:boolean = false;
let numero:number = 10;
let nome:string = "Rodger";
```

### Tipo Especiais:
- **Null**
- **Undefined**
### Exemplos:
```typescript
// Só recebem eles msm como valor;
let nulo: null = null;
let indefinido: undefined = undefined;
```

### Tipos Abrangentes: 
- ***Any***
- ***Void***
### Exemplos:
```typescript 
// Criação de Variavéis sem Retorno
let retorno:void
// Aceitar qualquer valor e pode ter Qualquer Retorno
let alguma:any = 0;
```

### Tipo Objeto
```typescript
// Objeto sem previsibilidade
let produto:object ={
name: "Rodger",
age: 21,
cidade: "BSB",
};
// Objeto Mais Tipado com previsibilidade
type ProdutoLoja ={
name: string;
value: number;
description: string;
};
// Instanciando o Objeto
let produto1 : ProdutoLoja ={
name: "Coquinha Gelada",
value: 20,
description: "Estupidamente no Ponto",
};
```

### Arrays:
No typescript existem duas formas de declarar arrays ->
```typescript
// Forma 1:
let dados: string[] = ["Irineu","Piriney","SaxoWaldisney"];
// Forma 2:
let dados2: Array<string> = ["Rodger","Chimbinha","Niltin"];
```

### Array Multi Types:
Declarando um array com multi tipos:
```typescript
let infos: (string | number)[]= ["Rodger",77,"Niltin",54];
```

### Tuplas: 
