# 4 - Contagem de Cédulas

## Desafio

Faça a leitura de um valor inteiro. Em seguida, calcule o menor número de notas possíveis (cédulas) onde o valor pode ser decomposto. As notas que você deve considerar são de 100, 50, 20, 10, 5, 2 e 1. Na sequência mostre o valor lido e a relação de notas necessárias.

## Entrada

Você receberá um valor inteiro N (0 < N < 1000000).

## Saída

Exiba o valor lido e a quantidade mínima de notas de cada tipo necessárias, seguindo o exemplo de saída abaixo. Após cada linha deve ser imprimido o fim de linha.

| Exemplo de Entrada | Exemplo de Saída          |
| ------------------ | ------------------------- |
| 576                | 576                       |
|                    | 5 nota(s) de R\$ 100,00   |
|                    | 1 nota(s) de R\$ 50,00    |
|                    | 1 nota(s) de R\$ 20,00    |
|                    | 0 nota(s) de R\$ 10,00    |
|                    | 1 nota(s) de R\$ 5,00     |
|                    | 0 nota(s) de R\$ 2,00     |
|                    | 1 nota(s) de R\$ 1,00     |
|                    |
| 11257              | 11257                     |
|                    | 112 nota(s) de R\$ 100,00 |
|                    | 1 nota(s) de R\$ 50,00    |
|                    | 0 nota(s) de R\$ 20,00    |
|                    | 0 nota(s) de R\$ 10,00    |
|                    | 1 nota(s) de R\$ 5,00     |
|                    | 1 nota(s) de R\$ 2,00     |
|                    | 0 nota(s) de R\$ 1,00     |
|                    |
| 503                | 503                       |
|                    | 5 nota(s) de R\$ 100,00   |
|                    | 0 nota(s) de R\$ 50,00    |
|                    | 0 nota(s) de R\$ 20,00    |
|                    | 0 nota(s) de R\$ 10,00    |
|                    | 0 nota(s) de R\$ 5,00     |
|                    | 1 nota(s) de R\$ 2,00     |
|                    | 1 nota(s) de R\$ 1,00     |

## Resposta

```javascript
let cem = 0,
  cinquenta = 0,
  vinte = 0,
  dez = 0,
  cinco = 0,
  dois = 0,
  um = 0,
  entrada = 0;
entrada = parseInt(gets());
console.log(entrada);
while (entrada !== 0) {
  if (entrada / 100 >= 1) {
    cem = Math.floor(entrada / 100);
    entrada = entrada - 100 * cem;
  } else if (entrada / 50 >= 1) {
    cinquenta = Math.floor(entrada / 50);
    entrada = entrada - 50 * cinquenta;
  } else if (entrada / 20 >= 1) {
    vinte = Math.floor(entrada / 20);
    entrada = entrada - 20 * vinte;
  } else if (entrada / 10 >= 1) {
    dez = Math.floor(entrada / 10);
    entrada = entrada - 10 * dez;
  } else if (entrada / 5 >= 1) {
    cinco = Math.floor(entrada / 5);
    entrada = entrada - 5 * cinco;
  } else if (entrada / 2 >= 1) {
    dois = Math.floor(entrada / 2);
    entrada = entrada - 2 * dois;
  } else if (entrada / 1 >= 1) {
    um = Math.floor(entrada / 1);
    entrada = entrada - 1 * um;
  } else {
    entrada = 0;
  }
}
console.log(`${cem} nota(s) de R$ 100,00`);
console.log(`${cinquenta} nota(s) de R$ 50,00`);
console.log(`${vinte} nota(s) de R$ 20,00`);
console.log(`${dez} nota(s) de R$ 10,00`);
console.log(`${cinco} nota(s) de R$ 5,00`);
console.log(`${dois} nota(s) de R$ 2,00`);
console.log(`${um} nota(s) de R$ 1,00`);
```
