# 📅 Tech Conference 2025 Schedule

Tabela em HTML com a programação de uma conferência de tecnologia, organizada por horário e por trilha (*track*).

## 📚 Sobre o exercício

Este é um **exercício** de HTML feito para praticar a criação de tabelas com estrutura semântica e acessível: `caption`, `thead`, `tbody`, `th` com `scope` e células mescladas com `colspan`.

## 🧱 Estrutura da tabela

```text
table
├── caption: Schedule by Track and Time
├── thead
│   └── tr: Time | Track A | Track B | Track C
└── tbody
    ├── tr: 9:00 AM   (3 sessões)
    ├── tr: 10:00 AM  (3 sessões)
    ├── tr: 11:00 AM  (Break, colspan="3")
    ├── tr: 11:30 AM  (3 sessões)
    ├── tr: 12:30 PM  (Lunch Break, colspan="3")
    └── tr: 2:00 PM   (3 sessões)
```

## 🏷️ Elementos utilizados

| Elemento | Função neste exercício |
| --- | --- |
| `<table>` | Container da tabela |
| `<caption>` | Título da tabela ("Schedule by Track and Time") |
| `<thead>` | Agrupa a linha de cabeçalho (Time, Track A, Track B, Track C) |
| `<tbody>` | Agrupa as linhas com a programação do dia |
| `<tr>` | Cada linha da tabela |
| `<th scope="col">` | Cabeçalho de **coluna** (Time, Track A, Track B, Track C) |
| `<th scope="row">` | Cabeçalho de **linha** (os horários, como 9:00 AM) |
| `<td>` | Célula de dados, com o nome de cada sessão |
| `colspan="3"` | Faz a célula ocupar as 3 colunas de trilha (usado em "Break" e "Lunch Break") |

## 🗓️ Programação

| Horário | Track A | Track B | Track C |
| --- | --- | --- | --- |
| 9:00 AM | Keynote: Tech Future | Intro to Web Dev | UX for All |
| 10:00 AM | Accessibility Deep Dive | CSS for Beginners | Inclusive Design Principles |
| 11:00 AM | **Break** (todas as trilhas) | | |
| 11:30 AM | AR/VR in Education | JavaScript Fundamentals | Design Systems at Scale |
| 12:30 PM | **Lunch Break** (todas as trilhas) | | |
| 2:00 PM | Voice UI Workshop | Git & GitHub Essentials | Color & Contrast in UI |

## 💡 Conceitos praticados

- **`scope`:** informa se o `th` é cabeçalho de coluna (`col`) ou de linha (`row`). Leitores de tela usam isso para relacionar cada sessão ao seu horário e à sua trilha.
- **`colspan`:** nas linhas de intervalo, uma única célula atravessa as três colunas, já que não há sessões separadas por trilha.
- **`caption`:** dá um título à tabela, associado diretamente a ela.
- **`thead` e `tbody`:** separam o cabeçalho do corpo da tabela, deixando o HTML mais organizado e semântico.

## ▶️ Como usar

1. Baixe ou clone este repositório.
2. Abra o arquivo `index.html` no navegador.

## 🛠️ Tecnologias

- HTML5

## 👤 Autor

**Caio Rafael-dev**, estudante de Full Stack e InfoSec.





# ♿ Tech Conference 2025 Schedule: Acessibilidade

Este documento explica **como a tabela de programação da conferência foi pensada para ser acessível**: quais elementos e atributos do HTML ajudam pessoas que usam leitores de tela, navegação por teclado ou outras tecnologias assistivas.

> 📚 Este repositório é um **exercício** de HTML sobre tabelas acessíveis.

## 🎯 Por que acessibilidade em tabelas?

Uma tabela é visualmente fácil de entender: o olho cruza a linha com a coluna. Para quem usa leitor de tela, isso não é automático. O leitor precisa saber **quais células são cabeçalhos** e **a quais dados cada cabeçalho se refere**. Sem isso, a pessoa escuta apenas uma sequência solta de textos.

O HTML resolve isso com marcação semântica, sem precisar de JavaScript ou de atributos ARIA.

## ✅ Recursos de acessibilidade usados no código

### 1. `lang="en"` no `<html>`

```html
<html lang="en">
```

Informa o idioma da página. O leitor de tela escolhe a pronúncia correta, o que importa porque todo o conteúdo está em inglês.

### 2. `<title>` e `<h1>`

```html
<title>Tech Conference 2025 Schedule</title>
<h1>Tech Conference 2025 Schedule</h1>
```

O `title` identifica a página na aba e para leitores de tela. O `h1` dá o título principal e permite navegar pela estrutura da página por cabeçalhos.

### 3. `<caption>`

```html
<caption>Schedule by Track and Time</caption>
```

Dá um **nome** à tabela. Ao entrar nela, o leitor de tela anuncia esse título, e a pessoa já sabe o que vai encontrar antes de percorrer as células.

### 4. `<thead>` e `<tbody>`

```html
<thead> ... </thead>
<tbody> ... </tbody>
```

Separam o cabeçalho do corpo da tabela, deixando a estrutura explícita para tecnologias assistivas e para o navegador.

### 5. `<th>` com `scope`

```html
<!-- Cabeçalhos de coluna -->
<th scope="col">Track A</th>

<!-- Cabeçalhos de linha -->
<th scope="row">9:00 AM</th>
```

Este é o recurso mais importante da tabela:

| Atributo | Significado |
| --- | --- |
| `scope="col"` | O `th` é cabeçalho de **toda a coluna** abaixo dele |
| `scope="row"` | O `th` é cabeçalho de **toda a linha** ao lado dele |

Com isso, ao parar na célula "Voice UI Workshop", o leitor de tela pode anunciar algo como: *"2:00 PM, Track A, Voice UI Workshop"*. O horário e a trilha vêm dos cabeçalhos, sem que a pessoa precise voltar e contar colunas.

> 💡 Os horários (9:00 AM, 10:00 AM...) são `th`, e não `td`, justamente porque funcionam como **cabeçalho de cada linha**.

### 6. `colspan="3"` nas linhas de intervalo

```html
<tr>
  <th scope="row">11:00 AM</th>
  <td colspan="3">Break</td>
</tr>
```

Em vez de repetir "Break" em três células, uma só célula atravessa as três trilhas. Isso evita que o leitor de tela repita a mesma informação três vezes e deixa claro que o intervalo vale para **todas** as trilhas.

A tabela continua simples: as células mescladas ficam sempre sob o cabeçalho de linha de horário, então `scope` é suficiente.

### 7. Uma tabela só para dados

A tabela é usada para o que ela serve: **dados tabulares** (horário × trilha). Não é usada para montar layout de página, o que atrapalharia a leitura por tecnologias assistivas.

## 🔊 Como um leitor de tela percorre a tabela

1. Anuncia que encontrou uma tabela, com o título do `caption`: *"Schedule by Track and Time"*.
2. Informa o número de linhas e colunas.
3. A cada célula, lê o conteúdo junto com os cabeçalhos relacionados (`th`) definidos por `scope`.
4. Em "Break" e "Lunch Break", lê a célula mesclada como pertencente à linha do horário.

> ℹ️ O texto exato anunciado varia conforme o leitor (NVDA, JAWS, VoiceOver, TalkBack) e suas configurações.

## 🧪 Como testar

| Teste | Como fazer |
| --- | --- |
| Leitor de tela | NVDA (Windows), Orca (Linux), VoiceOver (macOS/iOS) ou TalkBack (Android). Navegue pelas células e ouça os cabeçalhos |
| Teclado | Use `Tab` e `Shift + Tab` para navegar na página |
| Árvore de acessibilidade | DevTools do navegador, aba **Accessibility** |
| Validação do HTML | <https://validator.w3.org/> |
| Auditoria automática | Lighthouse (DevTools, aba **Lighthouse**, categoria Accessibility) |

## 🔧 Possíveis melhorias

| Melhoria | Por quê |
| --- | --- |
| Trocar `&` por `&amp;` em "Git & GitHub Essentials" e "Color & Contrast in UI" | O `&` solto é HTML inválido e o validador reclama |
| Adicionar `<meta name="viewport" content="width=device-width, initial-scale=1.0">` | Boa experiência em celulares |
| Envolver o conteúdo em `<main>` | Permite que leitores de tela pulem direto para o conteúdo principal |
| Aplicar CSS com contraste adequado entre texto e fundo | Mínimo de 4,5:1 para texto normal (WCAG AA) |
| Evitar o uso apenas de cor para destacar os intervalos | Quem não enxerga cores não perde a informação |
| Fazer a tabela rolar na horizontal em telas pequenas, dentro de um container com `overflow-x: auto` | Evita que a página inteira quebre no celular |

## 📏 Referências

- WCAG 2.2: <https://www.w3.org/TR/WCAG22/>
- WAI Tutorials, tabelas: <https://www.w3.org/WAI/tutorials/tables/>
- MDN, elemento `<table>`: <https://developer.mozilla.org/pt-BR/docs/Web/HTML/Element/table>
- MDN, atributo `scope`: <https://developer.mozilla.org/pt-BR/docs/Web/HTML/Element/th#scope>

## 👤 Autor

**Caio Rafael-dev**, estudante de Full Stack e InfoSec.