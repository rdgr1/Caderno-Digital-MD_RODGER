Typescript é nada mais que um superSET do Javascript faz tudo que o mesmo faz e mais algumas coisas
## Inicializar Projeto Node na Raiz
Para criar o package.json -->
```bash 
npm init -y
```

### Olá Mundo
```typescript
console.log("olá mundo")
```

### Rodando no Terminal: 
#### Shell
```bash
comando para executar:
node src/index.ts
exemplo de resposta:
ola mundo
```

### Conversão de Type para JavaScript
#### Shell

```bash 
npx tsc src/index.ts
```

## Para Criação do Arquivo TSConfig 
#### Shell
Para criação do arquivo config e para não ter ficar compilando,transcrevendo o type para JS para execução deve ser criar um arquivo Ts Config.
```shell
npx tsc --init
```

Para mais informações sobre o escopo do arquivo TSConfgi
- [[https://www.typescriptlang.org/tsconfig/ | TSConfig DOCS]]
