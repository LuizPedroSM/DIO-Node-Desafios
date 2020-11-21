# 1 - Contagem repetida de números

## Desafio

Neste desafio sua tarefa será ler vários números e em seguida dizer quantas vezes cada número aparece, ou seja, deve-se escrever cada um dos valores distintos que aparecem na entrada por ordem crescente de valor.

## Entrada

A primeira linha de entrada contem um único inteiro N, que indica a quantidade de valores que serão lidos para X (1 ≤ N ≤ 2000) logo em seguida. Com certeza cada número não aparecerá mais do que 20 vezes na entrada de dados.

## Saída

Imprima a saída de acordo com o exemplo fornecido abaixo, indicando quantas vezes cada um deles aparece na entrada por ordem crescente de valor.

| Exemplo de Entrada | Exemplo de Saída      |
| ------------------ | --------------------- |
| 7                  | 4 aparece 1 vez(es)   |
| 8                  | 8 aparece 2 vez(es)   |
| 10                 | 10 aparece 3 vez(es)  |
| 8                  | 260 aparece 1 vez(es) |
| 260                |
| 4                  |
| 10                 |
| 10                 |

```javascript
let size = gets();
let numeros = [];
let numero = 0;
let counts = {};
if (size >= 1 && size <= 2000) {
  for (i = 0; i < size; i++) {
    numero = gets();
    numeros.push(numero);
  }
  numeros.forEach(i => {
    counts[i] = (counts[i] || 0) + 1;
  });
  for (var count in counts) {
    console.log(`${count} aparece ${counts[count]} vez(es)`);
  }
}
```
