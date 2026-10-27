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