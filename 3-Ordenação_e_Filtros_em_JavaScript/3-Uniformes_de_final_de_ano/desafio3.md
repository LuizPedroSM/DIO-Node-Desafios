# 3 - Uniformes de final de ano

## Desafio

O professor Girafales organizou a confecção de um uniforme para as turmas da escola para comemorar o final do ano. Após algumas conversas, ficou decidido com os alunos que eles poderiam escolher a cor do uniforme entre branco ou vermelho. Assim sendo, Girafales precisa de sua ajuda para organizar as listas de quem quer o uniforme em cada uma das turmas, relacionando estas camisetas pela cor, tamanho (P, M ou G) e por último pelo nome.

## Entrada

Cada caso de teste inicia com um valor N, (1 ≤ N ≤ 60) inteiro e positivo, que indica a quantidade de uniformes a serem feitas para aquela turma. As próximas N\*2 linhas contém informações de cada um dos uniformes (serão duas linhas de informação para cada uniforme). A primeira linha irá conter o nome do estudante e a segunda linha irá conter a cor do uniforme ("branco" ou "vermelho") seguido por um espaço e pelo tamanho do uniforme "P" "M" ou "G". A entrada termina quando o valor de N for igual a zero (0) e esta valor não deverá ser processado.

## Saída

Para cada caso de entrada deverão ser impressas as informações ordenadas pela cor em ordem ascendente, seguido pelos tamanhos em ordem descendente e por último por ordem ascendente de nome, conforme o exemplo abaixo.

| Exemplo de Entrada | Exemplo de Saída              |
| ------------------ | ----------------------------- |
| 9                  |                               |
| Maria Jose         | branco P Cezar Torres Mo      |
| branco P           | branco P Maria Jose           |
| Mangojata Mancuda  | branco M JuJu Mentina         |
| vermelho P         | branco G Adabi Finho          |
| Cezar Torres Mo    | branco G Severina Rigudinha   |
| branco P           | vermelho P Amaro Dinha        |
| Baka Lhau          | vermelho P Baka Lhau          |
| vermelho P         | vermelho P Carlos Chade Losna |
| JuJu Mentina       | vermelho P Mangojata Mancuda  |
| branco M           |
| Amaro Dinha        |
| vermelho P         |
| Adabi Finho        |
| branco G           |
| Severina Rigudinha |
| branco G           |
| Carlos Chade Losna |
| vermelho P         |
| 0                  |                               |

## Resposta

```javascript
let totalItems = gets();
let list = [];

for (var i = 0; i < totalItems * 2; i++) {
  let itens = gets();

  if (typeof itens === "string") {
    if (~i & 1) {
      let aluno = { name: itens, color: 0, size: 0 };
      list.push(aluno);
    } else {
      let item = itens.split(" ");
      list[list.length - 1].color = item[0];
      list[list.length - 1].size = item[1];
    }
  }
}
list.sort((a, b) => {
  if (a.color < b.color) return -1;
  if (a.color > b.color) return 1;

  if (a.size > b.size) return -1;
  if (a.size < b.size) return 1;

  if (a.name < b.name) return -1;
  if (a.name > b.name) return 1;
});
list.map(aluno => console.log(aluno.color, aluno.size, aluno.name));
```
