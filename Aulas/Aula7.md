# Aula — Engenharia de Software: Modelo Cascata e Kanban

## Modelo Cascata: Abordagem Sequencial

O **Modelo Cascata** é um processo **linear e sequencial**. Cada fase deve ser concluída antes de iniciar a próxima.

### Etapas de uma metodologia Waterfall

1. **Requisitos**
2. **Sistema**
3. **Implementação**
4. **Testes**
5. **Verificação**
6. **Manutenção**

### Vantagens e Desvantagens do Modelo Cascata

| Vantagens | Desvantagens |
|---|---|
| Simplicidade e fácil entendimento | Rigidez e dificuldade em lidar com mudanças |
| Bem definido e com etapas claras | Longo tempo de entrega |
| Adequado para projetos com requisitos estáveis | Pouca interação com o cliente |

---

## Kanban: Sistema de Gestão Visual e Produtividade

**Metodologia de gestão visual** utilizada para otimizar fluxos de trabalho e aumentar a eficiência dos processos.

Foi criado na **década de 1940 pela Toyota** para melhorar a produção industrial, e posteriormente adaptado para diversas áreas, como desenvolvimento de software, gestão de projetos e processos administrativos.

### Elementos do Kanban

O Kanban utiliza um **quadro visual (Kanban Board)** dividido em colunas representando o fluxo de trabalho. Principais elementos:

- **Cartões (Tasks)**: representam as tarefas a serem realizadas.
- **Colunas (Stages)**: indicadores das etapas do processo (ex: "A Fazer", "Em Andamento", "Concluído"). Roadmap (roteiro): de cima para baixo, da direita para a esquerda.
- **Limite de WIP (Work in Progress)**: controla a quantidade de tarefas em progresso para evitar sobrecarga; também considera o tempo no fluxo (tempo do cartão em progresso).
- **Ciclos de Feedback**: revisões frequentes para melhoria contínua.

### Quadro Kanban — exemplo

Estrutura típica em colunas: **Item de Backlog → A Fazer → Fazendo → Feito**

**Backlog**: lista priorizada de itens de trabalho que precisam ser realizados dentro de um projeto.

### Vantagens e Desvantagens do Modelo Kanban

| Vantagens | Desvantagens |
|---|---|
| Flexibilidade e adaptabilidade a mudanças | Requer disciplina e comprometimento da equipe |
| Melhoria contínua do processo | Pode ser difícil de implementar em projetos complexos |
| Foco na entrega contínua de valor | Dependência da maturidade da equipe |

---

## Casos de Uso: Escolhendo cada Modelo

| Modelo Cascata | Modelo Kanban |
|---|---|
| Projetos governamentais | Manutenção e evolução de software |
| Software embarcado com especificações fixas | Equipes ágeis que buscam melhoria contínua |
| | Projetos com requisitos variáveis |

## Implementação Prática: Dicas e Melhores Práticas

**Modelo Cascata**
- Definição clara dos requisitos
- Documentação detalhada de todas as fases
- Gerenciamento rigoroso do cronograma

**Modelo Kanban**
- Visualização do fluxo de trabalho
- Limitação do trabalho em progresso
- Reuniões diárias de sincronização

---

## Ferramentas de Apoio: Gerenciamento de Projetos

- **Trello** — simples e intuitivo, ideal para equipes pequenas e freelancers.
- **Jira Software** — usado em desenvolvimento de software e equipes ágeis.
- **Taiga** — foco em metodologias ágeis, com interface simplificada.

## Benefícios do Kanban

- **Maior visibilidade**: permite que a equipe veja claramente o fluxo de trabalho.
- **Identificação de gargalos**: facilita a detecção de bloqueios e atrasos no processo.
- **Flexibilidade**: pode ser aplicado em diversas áreas e adaptado conforme necessário.
- **Aumento da produtividade**: otimiza a execução das tarefas, reduzindo desperdícios.
- **Entrega contínua**: ajuda a manter um fluxo constante de entregas sem sobrecarga.

## Exemplos práticos de quadro Kanban

- **Kanban Framework simples**: colunas *Backlog → To Do → Doing → Done*, com atividades numeradas migrando entre colunas conforme o progresso.
- **Kanban com Lead Time**: quadro mais detalhado, com colunas de "Valor de Negócio", "Em Análise", "Em Desenvolvimento" (subdividido em etapas: Planejado, A Fazer, Fazendo, Feito, Pronto), "Testes" e "Entregue", demonstrando o **Ponto de Comprometimento**, o **Trabalho em Progresso (WIP)** e o **Lead Time** (tempo total do início ao fim de uma tarefa).
- **Jira Software**: exemplo de Kanban Board real com colunas "To Do", "In Progress", "Code Review" (com limite de WIP definido, ex: Max 2) e "Done".

## Atividade prática proposta

Uso das ferramentas **Taiga** ou **Jira Software** para praticar a criação de um quadro Kanban.

## Referências bibliográficas

- ANDERSON, David J. *Kanban: Mudança Evolucionária de Sucesso para seu Negócio de Tecnologia*. São Paulo: Blue Hole Press, 2010.
- LACERDA, Rafael Tavares de Almeida; MENDONÇA, Marco Aurélio de Barros. *Aplicação do Kanban na Gestão de Projetos de Software*. Revista Produção Online, v. 10, n. 2, p. 438-459, 2010.