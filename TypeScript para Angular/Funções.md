
#### Declarando Função:
Existem duas *formas* de declaração uma forma explícita e uma não explícita.
```typescript
//As funções tem parâmetros tipados e seu retorno se quiser a forma
//explicíta.
function addNumber(x: number+y: number) : number{
	return x + y;
//Declarando função do tipo string.
function helloName(name:string){
	return `Hello ${name}`;
}
```

### Associando a uma variavel:
Quando uma *função* for associada a uma variável ela deve ser do mesmo tipo exemplo.
```typescript
//Forma errada tipando a variável como string e tendo retorno number.
let som : string = addNumber(4,7);
//Forma correta utilizando mesmo tipo da função.
let som : number = addNumber(4,7);
```

## Declarando um função multitipos:
Declarando um *função* com um parâmetro que pode receber dois tipos.
```typescript
//Função com retorno obrigatório number ou string de forma não explícita.
function CalltoPhone(phone: number | string){
	return phone;
}
//Função com retorno obrigatótio number ou string explícita.
function CalltoPhone(phone: number | string): number | string{
	return phone;
}
//Função com parâmetro multitipos e com retorno de qualquer tipo.
function CalltoPhone(phone: number | string): any{
	return phone;
}
```
## Funções Assíncronas
Uma *função* assíncrona é uma função que opera de forma não bloqueante, permitindo que o código continue sendo executado enquanto espera por uma operação (como uma chamada de API, leitura de arquivo, etc.).
*Declarando* uma ***Função assíncrona***:
```typescript
//Sempre que declarada um função assíncrona deve ser explícitada
//uma promisse.
async function getDatabase(id : number): Promise<string>{
	return'Rodger';
}
//Função com promise multitipos.
async function getDatabase(id : number): Promise<string | number>{
	return'Rodger';
}
```
