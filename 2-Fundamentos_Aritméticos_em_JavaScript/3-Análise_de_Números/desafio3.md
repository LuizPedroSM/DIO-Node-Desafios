# 3 - Análise de Números

## Desafio

Você deve fazer a leitura de 5 valores inteiros. Em seguida mostre quantos valores informados são pares, quantos valores informados são ímpares, quantos valores informados são positivos e quantos valores informados são negativos.

## Entrada

Você receberá 5 valores inteiros.

## Saída

Exiba a mensagem conforme o exemplo de saída abaixo, sendo uma mensagem por linha e não esquecendo o final de linha após cada uma.

| Exemplo de Entrada | Exemplo de Saída        |
| ------------------ | ----------------------- |
| -5                 | 3 valor(es) par(es)     |
| 0                  | 2 valor(es) impar(es)   |
| -3                 | 1 valor(es) positivo(s) |
| -4                 | 3 valor(es) negativo(s) |
| 12                 |

## Respostas

```javascript
let entrada = 0,
  pares = 0,
  impares = 0,
  positivos = 0,
  negativos = 0;

for (i = 1; i <= 5; i++) {
  entrada = parseInt(gets());
  entrada & 1 ? impares++ : ~entrada & 1 && pares++;
  entrada > 0 ? positivos++ : entrada < 0 && negativos++;
}
console.log(
  `${pares} valor(es) par(es)`,
  "\n",
  `${impares} valor(es) impar(es)`
);
console.log(
  `${positivos} valor(es) positivo(s)`,
  "\n",
  `${negativos} valor(es) negativo(s)`
);
```
