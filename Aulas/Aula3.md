# Aula 3 — Mermaid e Diagramas UML (Sistema de Biblioteca)

## Contexto do sistema

O estudo de caso é um **Sistema de Biblioteca**, com a seguinte estrutura funcional:

- **Livros**: Cadastrar, Alterar, Excluir, Consultar
- **Usuários**: Cadastrar, Alterar, Consultar
- **Empréstimos**: Registrar empréstimo, Registrar devolução, Consultar empréstimos, Verificar disponibilidade

A aula usa esse sistema como base para ensinar quatro tipos de diagramas em Mermaid, mostrando como cada um representa uma visão diferente do mesmo sistema.

## 1. Diagrama de Caso de Uso (`flowchart`)

Representa **o que o sistema permite fazer** e quem interage com ele.

- **Atores**: Bibliotecário (cadastra e gerencia empréstimos) e Usuário (consulta livros, solicita empréstimos/devoluções).
- Usa `flowchart LR` (fluxo da esquerda para a direita).
- `subgraph Nome["Rótulo"]` cria um **agrupamento visual** (o "sistema"), não uma classe.
- `-->` representa uma **relação/fluxo** entre elementos (ex: ator → caso de uso).
- Casos de uso são escritos como `UC1(["Cadastrar livro"])`, onde `UC1` é apenas um **identificador interno** do elemento no código.
- `-.->|include|` indica que um caso de uso inclui outro (ex: Registrar empréstimo inclui Verificar disponibilidade).

## 2. Diagrama de Classes (`classDiagram`)

Representa **quais são os objetos/entidades do sistema** e como se relacionam.

- Classes principais: `Livro`, `Usuario`, `Emprestimo`, `Bibliotecario`.
- Cada classe tem **atributos** (ex: `+int idLivro`) e **métodos** (ex: `+cadastrar()`).
- O símbolo `+` indica que o atributo/método é **público**.
- Relações de multiplicidade, como:
  - `Usuario "1" --> "0..*" Emprestimo : realiza` → um usuário pode ter **de zero a vários** empréstimos.
  - `Livro "1" --> "0..*" Emprestimo : participa` → um livro pode aparecer em vários empréstimos ao longo do tempo.
- O `Emprestimo` é a entidade que conecta `Usuario`, `Livro` e `Bibliotecario`.

## 3. Diagrama de Atividades (`flowchart TD`)

Representa **o fluxo passo a passo** para realizar uma operação — no exemplo, registrar um empréstimo.

- `Inicio([Início])` e `Fim([Fim])` marcam início/fim do fluxo (formato oval).
- Retângulos `["texto"]` representam ações/etapas.
- Losangos `{"texto"}` representam **decisões** (pontos de ramificação), com rótulos nas setas (`-- Sim -->`, `-- Não -->`) indicando os caminhos possíveis.
- Fluxo resumido: identificar usuário → verificar usuário → identificar livro → verificar livro → verificar disponibilidade → registrar empréstimo → atualizar disponibilidade → finalizar.

## 4. Diagrama de Sequência (`sequenceDiagram`)

Representa **como os objetos se comunicam** durante uma operação, e em qual ordem.

- `actor` e `participant` definem quem participa da troca de mensagens (Bibliotecário, Sistema, Usuário, Livro, Empréstimo).
- `->>` representa uma **mensagem enviada** de um participante para outro (chamada síncrona).
- `-->>` representa uma **resposta/retorno** de mensagem.
- `alt ... else ... end` representa **alternativas condicionais** (ex: usuário cadastrado vs. não cadastrado; livro disponível vs. indisponível).

## Como os quatro diagramas se relacionam

| Diagrama | Pergunta que responde |
|---|---|
| Caso de Uso | O que o sistema permite fazer? |
| Classes | Quais são os objetos/entidades do sistema? |
| Atividades | Qual é o fluxo para realizar uma operação? |
| Sequência | Como os objetos se comunicam durante a operação? |

Juntos, eles cobrem visões complementares do mesmo sistema: **funcionalidade** (caso de uso), **estrutura de dados** (classes), **processo** (atividades) e **comunicação** (sequência).