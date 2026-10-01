# What Beats? — JEV Version

## Português

**What Beats? — JEV Version** é um jogo experimental de associação livre. O jogador começa com uma pedra e escreve qualquer coisa que possa vencê-la. O JEV julga a relação entre o item atual e a resposta usando associações físicas, funcionais, simbólicas, culturais ou ficcionais.

Quando a resposta é aceita, ela substitui o item atual e a sequência continua. O jogo registra o streak e mostra a cadeia completa de palavras até a derrota. Respostas repetidas não são permitidas.

Além de julgar se a resposta vence, o JEV escolhe uma categoria visual específica para representá-la. Assim, ferramentas, pessoas, animais, clima, espaço, comida e conceitos recebem símbolos diferentes sem depender de uma lista fixa de palavras.

O projeto usa uma interface minimalista inspirada no construtivismo russo, com tipografia monospace, composição assimétrica, blocos de cor e transições GSAP entre os emojis e as palavras.

### Como executar

```bash
node server.cjs
```

Abra `http://localhost:4175` no navegador.

Configure a chave localmente em `.env`:

```env
OPENROUTER_API_KEY=sua-chave
```

O arquivo `.env` está no `.gitignore` e nunca deve ser enviado ao GitHub.

## English

**What Beats? — JEV Version** is an experimental free-association game. The player starts with a rock and types anything that could beat it. JEV evaluates the relationship between the current item and the answer through physical, functional, symbolic, cultural, fictional, or contextual associations.

When an answer is accepted, it replaces the current item and the chain continues. The game tracks the streak and displays the complete word chain until the player loses. Repeated answers are rejected.

In addition to judging whether the answer wins, JEV selects a specific visual category to represent it. Tools, people, animals, weather, space, food, and abstract concepts can therefore receive different symbols without relying on a fixed word list.

The project uses a minimal interface inspired by Russian Constructivism, with monospace typography, asymmetrical composition, bold color blocks, and GSAP transitions between emojis and words.

### Running locally

```bash
node server.cjs
```

Open `http://localhost:4175` in your browser.

Set the key locally in `.env`:

```env
OPENROUTER_API_KEY=your-key
```

The `.env` file is ignored by Git and must never be uploaded to GitHub.

## Skills and tools used

- **Creative Web Skill** — art direction, typography, layout, interaction, responsive behavior, and purposeful motion.
- **GSAP** — entrance transitions for the current emoji, word state, and input area.
- **Postman Lite** — safe validation of the OpenRouter JEV endpoint and prompt experiments without exposing credentials.
- **Computer Use** — local browser testing and GitHub repository publishing through the authenticated browser session.
- **OpenRouter / JEV 1.13** — semantic judgment of answers and selection of a concrete visual category.
- **Vanilla JavaScript** — game state, streak, duplicate prevention, chain history, and local server communication.

## Security

The OpenRouter key is used only by the local server. It is never placed in frontend code, committed to Git, or uploaded to GitHub.
