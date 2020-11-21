# 1 - Quantidade de Números Positivos

## Desafio

Crie um programa que leia 6 valores. Você poderá receber valores negativos e/ou positivos como entrada, devendo desconsiderar os valores nulos. Em seguida, apresente a quantidade de valores positivos digitados.

## Entrada

Você receberá seis valores, negativos e/ou positivos.

## Saída

Exiba uma mensagem dizendo quantos valores positivos foram lidos assim como é exibido abaixo no exemplo de saída. Não esqueça da mensagem "valores positivos" ao final.

| Exemplo de Entrada | Exemplo de Saída    |
| ------------------ | ------------------- |
| 7                  | 4 valores positivos |
| -5                 |
| 6                  |
| -3.4               |
| 4.6                |
| 12                 |

```javascript
let entrada = 0.0;
let valores = [];

for (i = 1; i <= 6; i++) {
  entrada = parseFloat(gets());
  valores.push(entrada);
}
valoresPositivos = valores.reduce((contador, valor) => {
  if (valor <= 0) return contador;
  return contador + 1;
}, 0);

console.log(valoresPositivos + " valores positivos");
```
