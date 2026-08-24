# Engenharia de Software — PlantUML

> **Disciplina:** Engenharia de Software  
> **Tema:** PlantUML e Diagramas UML  
> **Professora:** Profa. Silvia Garcia

---

## 1. O que é PlantUML?

**PlantUML** é uma ferramenta open source utilizada para criar diagramas a partir de **texto simples**, utilizando uma linguagem de marcação própria.

É utilizada principalmente em:

- Documentação técnica;
- Engenharia de Software;
- Projetos ágeis.

### Vantagens

- **Simplicidade:** os diagramas são criados por meio de texto.
- **Integração:** pode ser utilizada com VS Code, IntelliJ e Obsidian.
- **Uso online e offline:** permite trabalhar com os diagramas em diferentes ambientes.

---

## 2. Principais Diagramas

A aula apresenta quatro tipos principais de diagramas que podem ser criados com PlantUML:

1. Diagrama de Casos de Uso;
2. Diagrama de Classes;
3. Diagrama de Sequência;
4. Diagrama de Atividades.

---

## 3. Diagrama de Casos de Uso

O **Diagrama de Casos de Uso** mostra:

- As funcionalidades do sistema;
- Os atores envolvidos;
- As interações entre atores e funcionalidades.

### Exemplo

Um sistema de pedidos pode possuir:

- **Cliente** → Realizar Pedido;
- **Admin** → Gerenciar Produtos.

### Ideia principal

> **Casos de Uso = quem faz o quê no sistema.**

---

## 4. Diagrama de Classes

O **Diagrama de Classes** representa a estrutura do sistema.

Ele apresenta:

- Classes;
- Atributos;
- Métodos;
- Relacionamentos.

### Exemplo

Uma classe `Produto` pode possuir:

**Atributos:**
- id;
- nome;
- preço.

**Método:**
- calcularDesconto().

Uma classe `Pedido` pode possuir:

**Atributos:**
- número;
- data.

**Método:**
- calcularTotal().

### Ideia principal

> **Classes = estrutura do sistema.**

---

## 5. Diagrama de Sequência

O **Diagrama de Sequência** representa a interação entre objetos **ao longo do tempo**.

### Exemplo de Login

1. Cliente solicita login.
2. Sistema recebe a solicitação.
3. Sistema consulta o Banco de Dados.
4. Banco de Dados verifica as credenciais.
5. Sistema informa ao Cliente que o acesso foi permitido.

### Ideia principal

> **Sequência = quem conversa com quem e em qual ordem.**

---

## 6. Diagrama de Atividades

O **Diagrama de Atividades** representa o **fluxo de atividades de um processo**.

Ele pode utilizar decisões para representar diferentes caminhos.

### Exemplo

**Receber Pedido**

↓

**Produto em estoque?**

- **Sim** → Separar Produto → Enviar para entrega.
- **Não** → Notificar Cliente.

### Ideia principal

> **Atividades = fluxo de um processo.**

---

# 7. Atividade Prática

A atividade apresenta o contexto de uma empresa de **e-commerce** que está desenvolvendo um sistema para gestão de pedidos.

O objetivo é representar diferentes aspectos do sistema utilizando PlantUML.

---

## 8. Tarefas da Atividade

### 8.1 Diagrama de Casos de Uso

Deve representar:

- Cliente realizando pedido;
- Sistema verificando pagamento;
- Admin gerenciando produtos.

### 8.2 Diagrama de Classes

Deve conter:

- Classe `Cliente`;
- Classe `Produto`;
- Classe `Pedido`;
- Atributos básicos;
- Relacionamentos entre as classes.

### 8.3 Diagrama de Atividades

Deve representar o fluxo:

**Cliente faz login**

↓

**Escolhe produtos**

↓

**Realiza pagamento**

↓

**Confirmação do pedido**

### Entrega

A atividade deve ser entregue no **Teams** em um **único arquivo PDF**, contendo os códigos e diagramas solicitados.

---

# 9. Resolução — Casos de Uso

A resolução apresenta três atores:

- **Cliente**
- **Admin**
- **Sistema de Pagamento**

### Fluxo principal

- Cliente escolhe produtos.
- Cliente realiza o pedido.
- O pedido envolve o pagamento.
- O Sistema de Pagamento verifica o pagamento.
- Admin gerencia os produtos.

---

# 10. Resolução — Diagrama de Classes

A resolução possui três classes principais.

## Cliente

### Atributos

- `id: int`
- `nome: String`
- `email: String`

### Método

- `realizarPedido()`

---

## Produto

### Atributos

- `id: int`
- `nome: String`
- `preco: double`
- `qtd: int`

### Método

- `aplicarDesconto()`

---

## Pedido

### Atributos

- `numero: int`
- `data: Date`
- `total: double`

### Métodos

- `calcularTotal()`
- `confirmarPedido()`

### Relacionamentos

- Um **Cliente** pode realizar vários **Pedidos**.
- Um **Pedido** pode conter vários **Produtos**.

---

# 11. Resolução — Diagrama de Atividades

O fluxo completo apresentado é:

**Cliente faz login**

↓

**Escolher produtos**

↓

**Adicionar ao carrinho**

↓

**Deseja finalizar?**

### Não

→ Continuar navegando.

### Sim

→ Efetuar pagamento.

↓

**Sistema verifica pagamento**

↓

**Pagamento aprovado?**

### Não

→ Notificar erro no pagamento.

### Sim

→ Gerar pedido.

↓

**Enviar confirmação ao cliente**

---

# 12. Resolução — Diagrama de Sequência

O diagrama apresenta quatro participantes:

- **Cliente**
- **Sistema**
- **Sistema de Pagamento**
- **Banco de Dados**

### Fluxo

1. Cliente realiza login.
2. Sistema valida o login.
3. Cliente realiza um pedido.
4. Sistema envia os dados do pagamento ao Sistema de Pagamento.
5. Sistema de Pagamento confirma o pagamento.
6. Sistema salva o pedido no Banco de Dados.
7. Banco de Dados confirma que o pedido foi salvo.
8. Sistema envia a confirmação do pedido ao Cliente.

---

# 13. Resumo dos Diagramas

| Diagrama | Principal objetivo |
|---|---|
| **Casos de Uso** | Mostrar atores e funcionalidades |
| **Classes** | Mostrar estrutura, atributos, métodos e relacionamentos |
| **Sequência** | Mostrar interações ao longo do tempo |
| **Atividades** | Mostrar o fluxo de um processo |

---

# 14. Como Memorizar

### Casos de Uso

**Quem faz o quê?**

### Classes

**Como o sistema é estruturado?**

### Sequência

**Quem conversa com quem e em qual ordem?**

### Atividades

**Qual é o fluxo do processo?**

---

## 15. Conceito Geral

O **PlantUML** permite transformar uma descrição textual em diagramas que ajudam a representar diferentes aspectos de um sistema.

    Descrição do Sistema
            ↓
         PlantUML
            ↓
         Diagramas
            ↓
    ┌───────────────┐
    │ Casos de Uso  │ → Funcionalidades e atores
    ├───────────────┤
    │ Classes       │ → Estrutura do sistema
    ├───────────────┤
    │ Sequência     │ → Interações no tempo
    ├───────────────┤
    │ Atividades    │ → Fluxo de processos
    └───────────────┘

---

## 16. Conclusão — PlantUML

O **PlantUML** é uma ferramenta textual utilizada para criar diagramas aplicados à **Engenharia de Software**.

Os principais diagramas estudados são:

- **Casos de Uso:** representam os atores e as funcionalidades do sistema.
- **Classes:** representam a estrutura do sistema, incluindo classes, atributos, métodos e relacionamentos.
- **Sequência:** representam as interações entre os componentes ao longo do tempo.
- **Atividades:** representam o fluxo de processos.

A atividade prática utiliza um sistema de **e-commerce** para aplicar esses conceitos, envolvendo **clientes, produtos, pedidos, pagamento e banco de dados**.