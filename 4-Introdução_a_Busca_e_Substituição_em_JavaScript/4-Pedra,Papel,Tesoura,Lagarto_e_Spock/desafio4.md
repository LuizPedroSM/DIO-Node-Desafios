# 4 - Pedra, Papel, Tesoura, Lagarto e Spock

## Desafio

Pedra-papel-tesoura-lagarto-Spock é uma expansão do clássico método de seleção em jogo de pedra-papel-tesoura. Atua sob o mesmo princípio básico, mas inclui outras duas armas adicionais: o lagarto (formado pela mão igual a uma boca de fantoche) e Spock (formada pela saudação dos vulcanos em Star Trek). Isso reduz as chances de uma rodada terminar em um empate. O jogo foi inventado por Sam Kass e Karen Bryla, como "Rock Paper Scissors Lizard Spock". As regras de vantagem são as seguintes:

Tesoura corta papel
Papel cobre pedra
Pedra derruba lagarto
Lagarto adormece Spock
Spock derrete tesoura
Tesoura prende lagarto
Lagarto come papel
Papel refuta Spock
Spock vaporiza pedra
Pedra quebra tesoura
Um dia, duas amigas, Fernanda e Marcia, decidiram apostar quem pagaria um almoço para o outro, com esta brincadeira. Sua missão será fazer um algoritmo que, baseado no que eles escolherem, informe quem irá ganhar ou se dará empate.

## Entrada

Haverá diversos casos de teste. O primeiro número a ser lido será um inteiro, representando a quantidade de casos de teste. Cada caso de teste tem duas palavras, representando a escolha de Fernanda e de Marcia, respectivamente.

## Saída

Para cada caso de teste, imprima quem venceu, ou se houve empate.

| Exemplo de Entrada | Exemplo de Saída |
| ------------------ | ---------------- |
| 3                  |
| spock spock        | empate           |
| tesoura spock      | Marcia           |
| lagarto spock      | Fernanda         |

## Resposta

```javascript
let rounds = gets();

for (let i = 0; i < rounds; i++) {
  let moves = gets();
  let [player1, player2] = moves.split(" ");
  let result = game(player1, player2);
  // player1 = Fernanda; player2 = Marcia
  if (result == "player1") result = "fernanda";
  if (result == "player2") result = "marcia";
  console.log(result);
}

function game(player1, player2) {
  let result = "";
  if (player1 == "pedra") {
    if (player2 == "pedra") {
      result = "empate";
    }
    if (player2 == "papel") {
      result = "player2";
    }
    if (player2 == "tesoura") {
      result = "player1";
    }
    if (player2 == "spock") {
      result = "player2";
    }
    if (player2 == "lagarto") {
      result = "player1";
    }
  }
  if (player1 == "papel") {
    if (player2 == "pedra") {
      result = "player1";
    }
    if (player2 == "papel") {
      result = "empate";
    }
    if (player2 == "tesoura") {
      result = "player2";
    }
    if (player2 == "spock") {
      result = "player1";
    }
    if (player2 == "lagarto") {
      result = "player2";
    }
  }
  if (player1 == "tesoura") {
    if (player2 == "pedra") {
      result = "player2";
    }
    if (player2 == "papel") {
      result = "player1";
    }
    if (player2 == "tesoura") {
      result = "empate";
    }
    if (player2 == "spock") {
      result = "player2";
    }
    if (player2 == "lagarto") {
      result = "player1";
    }
  }
  if (player1 == "spock") {
    if (player2 == "pedra") {
      result = "player1";
    }
    if (player2 == "papel") {
      result = "player2";
    }
    if (player2 == "tesoura") {
      result = "player1";
    }
    if (player2 == "spock") {
      result = "empate";
    }
    if (player2 == "lagarto") {
      result = "player2";
    }
  }
  if (player1 == "lagarto") {
    if (player2 == "pedra") {
      result = "player2";
    }
    if (player2 == "papel") {
      result = "player1";
    }
    if (player2 == "tesoura") {
      result = "player2";
    }
    if (player2 == "spock") {
      result = "player1";
    }
    if (player2 == "lagarto") {
      result = "empate";
    }
  }
  return result;
}
```
