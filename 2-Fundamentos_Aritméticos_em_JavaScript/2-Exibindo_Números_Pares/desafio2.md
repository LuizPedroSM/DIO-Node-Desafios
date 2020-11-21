# 2 - Exibindo Números Pares

## Desafios

Crie um programa que leia um número e mostre os números pares até esse número, inclusive ele mesmo.

## Entrada

Você receberá 1 valor inteiro N, onde N > 0.

## Saída

Exiba todos os números pares até o valor de entrada, sendo um em cada linha.

| Exemplo de Entrada | Exemplo de Saída |
| ------------------ | ---------------- |
| 6                  | 2                |
|                    | 4                |
|                    | 6                |

## Resposta

```javascript
let entrada = parseInt(gets());
for (i = 2; i <= entrada; i++) {
  if (~i & 1) console.log(i);
}
```
