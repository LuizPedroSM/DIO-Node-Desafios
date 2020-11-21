# 1 - Coração das cartas

## Desafio

Marcos decidiu abandonar o bar da faculdade onde jogava truco para dedicar-se ao mundo da programação. Para que isso fosse mais fácil, decidiu criar um novo jogo de cartas.

O coração das cartas, como Marcos apelidou o jogo, é individual e jogado com três pilhas, inicialmente com o mesmo número de cartas. Cada carta tem um valor numérico inteiro de 0 até 9. O jogador pode, a qualquer momento ver o valor de qualquer carta, mas só pode jogar com as cartas que estão no topo das pilhas. Em cada rodada, o jogador pode remover qualquer combinação de cartas que estejam no topo da pilha (pode escolher 1, 2 ou até 3 cartas) cuja soma dos valores seja múltiplo de 3. O jogo é ganho quando todas as cartas forem removidas das pilhas. Se alguma carta não puder ser removida, perde-se o jogo.

## Entrada

A entrada é composta por várias instâncias Cada instância é iniciada por um inteiro N (0 ≤ N ≤ 100), que identifica o número de cartas em cada pilha. A entrada termina quando N = 0. Cada uma das N linhas seguintes contém três inteiros A, B e C, que descrevem os valores numéricos das cartas em um nível da pilha (0 ≤ A, B, C ≤ 9). As pilhas são descritas do topo até o fundo.

## Saída

Para cada instância, imprima uma linha contendo o número 1 se o jogador pode ganhar a instância do jogo ou o número 0 se o jogo for impossível.

| Exemplo de Entrada | Exemplo de Saída |
| ------------------ | ---------------- |
| 2                  | 1                |
| 1 1 1              | 0                |
| 2 0 4              |
| 3                  |
| 1 0 0              |
| 0 1 0              |
| 0 0 0              |
| 0                  |

## Tentativa

```js
function check(pilhas) {
  let test = 0;
  pilhas.map(p => (isNaN(p) || p > 9) && (test = null));
  if (test === null) return null;
  let test0 = pilhas[0];
  let test01 = pilhas[0] + pilhas[1];
  let test12 = pilhas[1] + pilhas[2];
  let test123 = pilhas[0] + pilhas[1] + pilhas[2];

  if (test0 % 3 === 0 && test0 !== 0) {
    return 1;
  } else if (test01 % 3 === 0 && test01 !== 0) {
    return 1;
  } else if (test12 % 3 === 0 && test12 !== 0) {
    return 1;
  } else if (test123 % 3 === 0 && test123 !== 0) {
    return 1;
  } else {
    return 0;
  }
}

let N = parseInt(gets());
let result = 0;
while (N != 0) {
  for (let i = 0; i < N; i++) {
    let pilhas = gets()
      .split(" ")
      .map(Number);
    result += check(pilhas);
  }
  if (result === N) {
    console.log(1);
  } else if (result === null) {
    console.log(null);
  } else {
    console.log(0);
  }
  N = gets();
}
```
