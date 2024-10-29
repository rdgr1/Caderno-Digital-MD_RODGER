#### Interface X *Tipos*
As duas também aceitam multitipos.
#### Declarando *Tipo*:
Utilizado para tipar um objeto.
```typescript
type robot = {
id: number;
name: string;
}
// Com propriedas apenas de leitura.
type robot = {
readonly id: number;
name: string;
}
```
#### Declarando Interface:
Utilizado para tipar classes.
```typescript
interface robot2{
id: number;
name: string;
}
// Com propriedades apenas de leitura.
interface robot2{
readonly id: number;
name: string;
}


