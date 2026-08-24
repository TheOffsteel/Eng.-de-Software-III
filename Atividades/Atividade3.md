# Atividade — Sistema de Biblioteca em Mermaid (Entrega)

## Resumo

A atividade consistiu em executar os 4 diagramas Mermaid do **Sistema de Biblioteca** (Caso de Uso, Classes, Atividades e Sequência) e responder o questionário de fixação sobre a sintaxe e o significado de cada um.

---

## Diagramas executados

| # | Diagrama | Tipo Mermaid | Status |
|---|---|---|---|
| 1 | Caso de Uso | `flowchart LR` | ✅ Executado e PNG anexado |
| 2 | Classes | `classDiagram` | ✅ Executado e PNG anexado |
| 3 | Atividades — Registrar Empréstimo | `flowchart TD` | ✅ Executado e PNG anexado |
| 4 | Sequência — Registrar Empréstimo | `sequenceDiagram` | ✅ Executado e PNG anexado |

**O que cada diagrama mostrou na prática:**

- **Caso de Uso**: os atores `Bibliotecário` e `Usuário` conectados aos 11 casos de uso do sistema, agrupados visualmente dentro do `subgraph` "Sistema de Biblioteca"; a relação `UC8 -.->|include| UC11` ficou visível como uma ligação pontilhada entre "Registrar empréstimo" e "Verificar disponibilidade".
- **Classes**: as 4 entidades (`Livro`, `Usuario`, `Emprestimo`, `Bibliotecario`) renderizadas com seus atributos e métodos, e as setas de associação `1 --> 0..*` ligando `Usuario`, `Livro` e `Bibliotecario` a `Emprestimo`.
- **Atividades**: o fluxo de decisão do empréstimo, com os losangos de decisão (`Usuário cadastrado?`, `Livro cadastrado?`, `Livro disponível?`) direcionando para os diferentes desfechos (confirmação ou mensagens de erro), todos convergindo no nó `Fim`.
- **Sequência**: a troca de mensagens entre `Bibliotecário`, `Sistema`, `Usuário`, `Livro` e `Empréstimo`, com os blocos `alt/else` mostrando visualmente os dois pontos de decisão (usuário não cadastrado / livro indisponível).

---

## Questionário — Gabarito da entrega

| Nº | Pergunta (resumo) | Resposta marcada |
|---|---|---|
| 1 | Função de `subgraph Sistema["Sistema de Biblioteca"]` | **B** — Criar um agrupamento visual denominado "Sistema de Biblioteca" |
| 2 | O que `-->` representa (`Bibliotecario --> UC1`) | **C** — Relação ou fluxo entre dois elementos |
| 3 | O que representa `UC1` em `UC1(["Cadastrar livro"])` | **B** — Um identificador interno do elemento |
| 4 | Finalidade do símbolo `+` em `class Livro { +int idLivro ... }` | **A** — Indicar que o atributo ou método é público |
| 5 | Significado de `"0..*"` em `Usuario "1" --> "0..*" Emprestimo` | **C** — De zero a vários empréstimos |
| 6 | Finalidade de `C{"Usuário cadastrado?"}` com `-- Sim -->` / `-- Não -->` | **B** — Representar uma decisão com diferentes caminhos |
| 7 | Elemento que representa o início do processo | **C** — `([Início])` |
| 8 | O que representa `Bibliotecario->>Sistema: Solicitar empréstimo` | **B** — O Bibliotecário envia uma mensagem para o Sistema |
| 9 | Finalidade de `alt` e `else` no diagrama de sequência | **A** — Representar alternativas condicionais |
| 10 | Associação correta entre diagrama e sintaxe Mermaid | **B** — Caso de uso → `flowchart`; Classes → `classDiagram`; Atividades → `flowchart`; Sequência → `sequenceDiagram` |

**Resultado: 10/10 — todas as respostas corretas.**

---

## Conclusão

A entrega demonstra domínio dos quatro tipos de diagrama trabalhados na Aula 3 e de sua sintaxe básica em Mermaid:

- **Estrutural** (Classes) — entidades, atributos e relações.
- **Funcional** (Caso de Uso) — o que o sistema oferece a cada ator.
- **Comportamental — processo** (Atividades) — o passo a passo de uma operação.
- **Comportamental — comunicação** (Sequência) — a troca de mensagens entre os componentes ao longo do tempo.

Juntos, os quatro diagramas cobrem as quatro perguntas centrais da modelagem UML aplicadas ao Sistema de Biblioteca: **o quê, quem, como estruturado e como comunicado.**

[PDF da Atividade Preenchida](../Assets/PDFs/Biblioteca_Mermaid_ALUNOS%20-%20Entrega%20%20(1).pdf)