# 🛠️ Engenharia de Software III

### Atividades, resumos e projetos práticos da disciplina de Engenharia de Software III

![Status](https://img.shields.io/badge/status-em%20andamento-yellow?style=for-the-badge)
![Curso](https://img.shields.io/badge/curso-ADS-blue?style=for-the-badge)
![Turno](https://img.shields.io/badge/turno-manhã-8A2BE2?style=for-the-badge)
![Licença](https://img.shields.io/badge/licença-uso%20acadêmico-lightgrey?style=for-the-badge)

---

## 📖 Sobre o repositório

Este repositório reúne as **atividades práticas, resumos de aula e projetos** desenvolvidos na disciplina de **Engenharia de Software III**, ministrada pela **Profa. Me. Silvia Garcia**.

O conteúdo é baseado nas seguintes referências bibliográficas:

> 📘 VALENTE, M. T. *Engenharia de Software Moderna: Princípios e Práticas para Desenvolvimento de Software com Produtividade*. Independente, 2020.
>
> 📗 SWEBOK — *Guide to the Software Engineering Body of Knowledge*, Version 3.0/4.0, IEEE Computer Society. [swebok.org](http://www.swebok.org)

---

## 🗂️ Estrutura do repositório

```
📦 Eng.-de-Software-III
├── 📁 aulas/          → Resumos e materiais das aulas teóricas
├── 📁 atividades/     → Exercícios, formulários e estudos de caso práticos
└── 📁 assets/         → Imagens, diagramas (PNG) e demais recursos visuais
```

---

## 🧠 Conteúdos abordados

### 📚 Fundamentos
- Definição e histórico da Engenharia de Software
- Conferência da OTAN (1968)
- SWEBOK — 12 áreas de conhecimento
- Requisitos funcionais x não funcionais

### 🔄 Processos e metodologias
- Modelo Waterfall (cascata)
- Princípios ágeis e Scrum
- Gerência de Configuração
- Lei de Brooks

### ✅ Qualidade e manutenção
- Refatoração de código
- Testes de unidade e revisão de código
- Integração contínua
- Sistemas legados

### 🧩 Modelagem UML
- Diagrama de Casos de Uso
- Diagrama de Classes
- Diagrama de Sequência
- Diagrama de Atividades

---

## 🚑 Projeto Prático: SGEA — Sistema de Gerenciamento de Entregas Autônomas

Estudo de caso central da disciplina: uma startup de logística que opera uma frota de **Veículos Autônomos (VGAs)** para transporte de medicamentos em uma grande cidade, exigindo roteirização dinâmica, monitoramento em tempo real e conformidade regulatória.

### Requisitos documentados
- **RF-01** — Processar solicitação de entrega urgente
- **RNFR-01.1 a RNFR-01.5** — Desempenho, Confiabilidade, Segurança, Usabilidade e Escalabilidade

### Diagramas elaborados

| Diagrama | Descrição |
|---|---|
| 🧍 **Casos de Uso** | Atores (Solicitante, Operador, Motorista de Reserva, Administrador, Órgão Regulador etc.) e suas interações com o sistema |
| 🧱 **Classes** | Entidades `Cliente`, `Entrega`, `VeiculoAutonomo`, `Rota`, `Sensor`, `Alerta`, `Operador` e seus relacionamentos |
| 🔁 **Sequência** | Fluxo de uma entrega urgente: solicitação → alocação de VGA → roteirização → monitoramento |
| 🌳 **Atividades** | Tratamento de falha crítica em sensor: parada urgente, alerta e intervenção do motorista de reserva |

---

## 🧰 Ferramentas utilizadas

![Mermaid](https://img.shields.io/badge/Mermaid.js-FF3670?style=flat-square&logo=mermaid&logoColor=white)
![VSCode](https://img.shields.io/badge/VS%20Code-007ACC?style=flat-square&logo=visual-studio-code&logoColor=white)
![Markdown](https://img.shields.io/badge/Markdown-000000?style=flat-square&logo=markdown&logoColor=white)
![Microsoft Forms](https://img.shields.io/badge/Microsoft%20Forms-1560BD?style=flat-square&logo=microsoftoffice&logoColor=white)

- **Mermaid Live Editor** ([mermaid.live](https://mermaid.live)) — renderização dos diagramas a partir do código
- **DeepSeek Chat** — apoio na geração de código Mermaid
- **VS Code + extensão Mermaid Viewer** — pré-visualização local dos diagramas (`.md`/`.mmd`)
- **Microsoft Forms** — formulários de fixação de conteúdo

---

## Autor

**João Gabriel Rodrigues Lara**
Curso: Análise e Desenvolvimento de Sistemas — Turno Manhã

---

*Repositório de uso acadêmico — Disciplina de Engenharia de Software III*