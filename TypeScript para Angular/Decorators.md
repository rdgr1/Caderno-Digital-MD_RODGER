Exemplo de uso básico de `Decorators` como **Classe**
```typescript
function ExibirNome(target: any){
	console.log(target);
}

@ExibirNome
class Funcionario{
}
``` 
Utilizando decorator para uma função que faz versionamento de uma API

```typescript
function apiVersion(version: string){
	return (target:any) => {
		Object.assing(target.prototype,{__version:version});
	};
}
@apiVersion("1.10")
class API{}
const api = new api
console.log(api.__version)
```

### Atributte Decorator
```typescript
/*Criando função*/
function minLength(length: number){
	return (target: any, key: string) => {
		let _value = target[key];
		const getter = () => _value;
		const setter = (value: string) => {
			if(value.length < length){
				throw new Error(`Tamanho menor do que ${length}`);
			}
			else{
				_value = value;
			}
		}
	}
} 
/*Criando a Classe*/
clas Api{
@minLength(3)
name: string;

constructor(name: string){
	this.name = name;
	}
}
const api = new Api("Produtos");
```

Com isso podemos definir exatamente como queremos que nosso objeto seja guardado na memória sobrescrevendo a forma que é lido `GETTER` e a forma que altera ou setado `SETTER`.
E é muito usado em frameworks

