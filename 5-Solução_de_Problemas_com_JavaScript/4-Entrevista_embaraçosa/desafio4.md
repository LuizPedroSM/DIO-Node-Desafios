# 4 - Entrevista embaraçosa

## Desafio

A nutricionista Juliana Alcantra é uma excelente profissional de sua área. Em determinado dia, ela foi entrevistada ao vivo para um jornal da cidade. No entanto, ficou um pouco nervosa na hora, e diante da situação, sua fala ficou um pouco distorcida, repetindo o final de cada palavra após dizer a mesma. Para que isso não aconteça novamente, ela precisa da sua ajuda para escrever um programa que omita a parte repetida, de modo que as palavras sejam pronunciadas como deveriam ser.

Escreva um programa que, dada uma palavra errada, a mesma seja corrigida.

## Entrada

Haverá diversos casos de teste. Cada caso de teste é formado por uma palavra, de, no máximo, 30 caracteres, dita da forma errada. A entrada termina com fim de arquivo.

## Saída

Para cada caso de teste, escreva a palavra devidamente corrigida. Analise os exemplos para verificar o padrão, de modo a consertar todos os casos.

| Exemplo de Entrada | Exemplo de Saída |
| ------------------ | ---------------- |
| sanduicheiche      | sanduiche        |
| barrilarril        | barril           |
| ratoato            | rato             |
| sol                | sol              |
| coliseueu          | coliseu          |
| queijoijo          | queijo           |
| astroastro         | astro            |
| a                  | a                |

## Tentativa 1

```js
// Limpa de 1 para 1. Uma entrada uma saida. Não limpa continuamente caso a subString se repita
let line = gets();

function clean(word) {
  let rev = word
    .split("")
    .reverse()
    .join("");
  let rangeSize = parseInt(rev.length / 2);
  let range = Array(rangeSize)
    .fill(1)
    .map((x, y) => x + y);
  let j = 1;

  for (let i of range) {
    if (rev.slice(0, i) === rev.slice(i, i + j)) {
      rev = rev.slice(i);
      break;
    }
    j += 1;
  }
  console.log(
    rev
      .split("")
      .reverse()
      .join("")
  );
}

while (line !== "") {
  clean(line);
  line = gets();
}
```

## Tentativa 2

```js
let input = ``;
let lines = input.split("\n");
function clean(word) {
  let rev = word
    .split("")
    .reverse()
    .join("");
  let rangeSize = parseInt(rev.length / 2);
  let range = Array(rangeSize)
    .fill(1)
    .map((x, y) => x + y);
  let j = 1;

  for (let i of range) {
    //console.log(`subStrings = ${rev.slice(0,i)} ${rev.slice(i, i+j)}`);
    if (rev.slice(0, i) === rev.slice(i, i + j)) {
      rev = rev.slice(i);
      break;
    }
    j += 1;
  }
  let cleanWord = rev
    .split("")
    .reverse()
    .join("");
  return cleanWord;
}
lines.map(palavra => {
  let validWords = [];
  let isItClean = clean(palavra);
  let isItReallyClean = clean(isItClean);
  let size = palavra.length & 1 ? palavra.length + 1 : palavra.length;
  let limit =
    line.length & 1
      ? Math.ceil(line.length / 2) + 1
      : Math.ceil(line.length / 2);
  validWords.push(isItClean);
  while (isItClean !== isItReallyClean && isItReallyClean.length >= limit) {
    validWords.push(isItReallyClean);
    isItClean = clean(isItClean);
    isItReallyClean = clean(isItClean);
  }
  while (validWords.length) {
    console.log(validWords.pop());
  }
});
```

## Tentativa 3

```js
function clean(word) {
  let input = word
    .split("")
    .reverse()
    .join("");
  let size = input.length;
  let i = 1;
  let regex = new RegExp(input.slice(0, i), "g");
  while (input.match(regex).length > 1 && i <= size) {
    i += 1;
    regex = new RegExp(input.slice(0, i), "g");
  }
  let subString = input.slice(0, i - 1);
  input = input.replace(subString, "");
  console.log(
    input
      .split("")
      .reverse()
      .join("")
  );
}

let input = `aaaaaaaaaa
`;
let lines = input.split("\n");
lines.map(w => clean(w));
```
