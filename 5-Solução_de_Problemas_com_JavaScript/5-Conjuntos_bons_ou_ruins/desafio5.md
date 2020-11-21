# 5 - Conjuntos bons ou ruins?

## Desafio

Nesse algoritmo você deverá descobrir se um conjunto de palavras é bom ou ruim. Por definição, um conjunto é bom quando nenhuma palavra desse conjunto é um prefixo de outra palavra. Caso contrário, é considerado um conjunto ruim.

Por exemplo, {dbc, dae, dbcde} é um conjunto ruim, pois dbc é um prefixo de dbcde. Quando duas palavras são idênticas, definimos como uma sendo prefixo da outra.

## Entrada

A entrada contém vários casos de teste. A primeira linha de cada caso de teste terá um inteiro N (1 ≤ N ≤ 10⁵), que representa a quantidade de palavras no conjunto. Segue então N linhas, cada uma tendo uma palavra de no máximo 100 letras minúsculas. A entrada termina quando N = 0 e não deve ser processada.

## Saída

Para cada caso de teste, você deverá imprimir "Conjunto Bom", ou "Conjunto Ruim", conforme explicado acima.

| Exemplo de Entrada | Exemplo de Saída |
| ------------------ | ---------------- |
| 3                  | Conjunto Ruim    |
| abc                | Conjunto Bom     |
| dae                |
| abcde              |
| 2                  |
| abc                |
| def                |
| 0                  |

## Resposta

```js
let input = parseInt(gets());
let list = [];
let exit = 0;

function prefix(prefix, word) {
  return word.startsWith(prefix);
}

do {
  for (let i = 0; i < input; i++) {
    let word = gets();
    list.map(w => {
      if (w.length < word.length) {
        prefix(w, word) && exit++;
      } else {
        prefix(word, w) && exit++;
      }
    });
    list.push(word);
  }
  if (exit > 0) {
    console.log(`Conjunto Ruim`);
  } else {
    console.log(`Conjunto Bom`);
  }
  exit = 0;
  list = [];
  input = parseInt(gets());
} while (input !== 0);
```
