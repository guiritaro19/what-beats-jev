# What Beats — guia rápido

Este protótipo roda inteiro no navegador. Não usa n8n, servidor, banco ou chave de API.

## Onde está cada parte

- `index.html`: estrutura da tela, input, botão, placar e lista da sequência.
- `styles.css`: aparência minimalista, responsiva e em monospace.
- `app.js`: regras do jogo e controle do streak.

## Como o jogo decide

1. `target` guarda o item atual, começando em `rock`.
2. O jogador escreve uma palavra.
3. `normalize()` remove acentos, diferenças de maiúsculas e espaços extras.
4. `findTerm()` procura a palavra na lista `terms`.
5. A propriedade `beats` do item atual decide se a resposta é verdadeira. A lista deve representar relações causais plausíveis, não apenas uma comparação literal. Por isso `firefighter` vence `rock` nesta versão: ele pode quebrar, mover ou remover uma pedra usando ferramentas e força.
6. Se for válida, a palavra entra na sequência e vira o novo item.
7. Se não for válida, o jogo termina e a cadeia completa permanece visível.

## Regra de não repetição

Antes de aceitar uma resposta, o jogo compara a forma normalizada com todas as palavras já usadas. Assim, `Café`, `cafe` e ` café ` são tratados como a mesma entrada.

## Onde conectar o JEV depois

A função `play()` é o ponto de troca. Mais adiante, ela pode enviar `target` e a resposta para o JEV e esperar um JSON como:

```json
{
  "accepted": true,
  "emoji": "🔥",
  "next_item": "fire"
}
```

Por enquanto, a decisão local deixa o protótipo rápido e fácil de testar.

## Instrução recomendada para o JEV

Quando a decisão for migrada para o JEV, ele deve receber uma instrução semelhante a esta:

> Julgue se a resposta realmente supera o item atual em algum contexto real, físico, funcional, simbólico ou cultural plausível. Não exija que a resposta esteja em uma lista fixa. Considere relações indiretas válidas, como uma ferramenta, pessoa ou processo que consegue alterar, destruir, conter, remover ou neutralizar o item. Aceite `firefighter` contra `rock` porque um bombeiro pode removê-la ou quebrá-la com equipamento. Rejeite apenas respostas sem relação defensável. Responda `accepted`, `emoji` e uma justificativa curta.
