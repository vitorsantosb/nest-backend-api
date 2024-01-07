# TypeScript


> [!IMPORTANT]
> Ficar atendo nas configurações do TypeScript qual versão do Node.js ele está convertendo o código, para versões mais antigas ou versões mais novas. dentro do arquivo ```tsconfig.json```
> para obter a versão correta a se usa com a versão do node instalada na maquina acessar o site: https://github.com/microsoft/TypeScript/wiki/Node-Target-Mapping


Principais diferenças entre Node.js e TypeScript

```Tipagem em Javascript: JavaScript trabalha com tipagem dinâmica ou seja você pode realizar atualizações em varias em tempo de execução da aplicação```

```Tipagem em TypeScript: O TypeScript trabalha com a tipagem estática ou seja que toda variavel deve ter seu valor declaro, e seu valor não pode ser modificado em runtime(tempo de execução).```

Inferência - Quando o TypeScript consegue determinar o tipo de forma automática o tipo de variável baseado em como a função foi feita!

> [!IMPORTANT]
> Garantir sempre que o valor a ser retornado por uma função seja do tipo esperado, verificar sempre qual é o retorno do valor em uma constante.

```ts
type Usuario = {
  name: string;
  anoQueNasceu: number;
}

function calcularIdadeDoUsuario(usuario: Usuario) {
  if(usuario.anoQueNasceu >= 2023){
    return 'Ano de nascimento invalido'
  }
  return 2023 - usuario.anoQueNasceu;
}

const idade = calcularIdadeDoUsuario({ anoQueNasceu: 1994, name: 'Shado'});
```


TypeScript trabalha com interfaces -
```ts
export interface name {
  readonly _id: string,
  readonly email: string,
  readonly password: string,
  name: string,
}
```

