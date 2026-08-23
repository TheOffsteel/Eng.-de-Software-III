# Resumo da Aula — Engenharia de Software III
**Revisão Prática | Profa. Me. Silvia Garcia**

## Livros de Referência
- **VALENTE, M. T.** *Engenharia de Software Moderna: Princípios e Práticas para Desenvolvimento de Software com Produtividade*. Independente, 2020.
- **SWEBOK** — *Guide to the Software Engineering Body of Knowledge*, Version 3.0, IEEE Computer Society, 2014. Disponível em: www.swebok.org

## SWEBOK na Engenharia de Software
O SWEBOK organiza o conhecimento da área em **12 áreas principais**, cobrindo todo o ciclo de vida do desenvolvimento:

1. **Engenharia de Requisitos** — definição e análise das necessidades do sistema
2. **Projeto de Software** — estruturação do sistema antes da implementação
3. **Construção de Software** — codificação e escolha de ferramentas/frameworks
4. **Testes de Software** — verificação e validação do sistema
5. **Manutenção de Software** — correção de erros e evolução
6. **Gerência de Configuração** — controle de versões e mudanças no código
7. **Gerência de Projetos** — planejamento, controle e entrega
8. **Processos de Software** — modelos de desenvolvimento (Waterfall, Ágil etc.)
9. **Modelos de Software** — representações gráficas (ex.: UML)
10. **Qualidade de Software** — avaliação de fatores internos e externos
11. **Prática Profissional** — questões éticas e regulatórias
12. **Aspectos Econômicos** — custos e impacto financeiro

## Estudo de Caso: Sistema de Gerenciamento de Entregas Autônomas (SGEA)

### Contexto
Uma startup de logística pretende desenvolver o **SGEA**, sistema que opera uma frota de **veículos terrestres autônomos (VGAs)** dedicados ao transporte de medicamentos e insumos de saúde em uma grande cidade. O sistema deve coordenar todo o ciclo — da solicitação até a confirmação de recebimento — incluindo roteirização dinâmica, monitoramento em tempo real e conformidade regulatória (temperatura controlada, rastreabilidade, segurança).

### Atores Envolvidos
| Ator | Papel |
|---|---|
| **Solicitante** | Paciente, farmácia, hospital ou clínica que requisita a entrega |
| **Operador da Central** | Supervisiona a frota, intervém em anomalias e gerencia exceções |
| **Motorista de Reserva** | Intervém manualmente em situações não previstas (operação semiautônoma) |
| **Administrador do Sistema** | Configurações, cadastro de veículos e regras de negócio |
| **Órgão Regulador (Anvisa/ANATEL)** | Recebe dados de rastreabilidade e condições de armazenamento |
| **Sistema de Trânsito Municipal** | Fonte de dados sobre tráfego, interdições e clima |
| **Sistema de Farmácias** | ERP das farmácias parceiras que fornecem os medicamentos |

### Testes com Veículos Autônomos no Mundo
- **China e Ásia**: implementação acelerada em cenários urbanos reais; Cingapura testa ônibus autônomos.
- **EUA**: Amazon (Zoox) testa veículos sem volante ou pedais.
- **Europa**: testes avançados em rodovias.
- **Inovações**: testes virtuais e simulações de colisão (crash tests autônomos).

### Testes no Brasil
Sem regulamentação definitiva para uso comercial autônomo total, mas com projetos-piloto:
- **São Carlos (USP)** — pesquisas em robótica
- **Vitória (UFES)** — Projeto IARA (*Intelligent Autonomous Robotic Automobile*)
- **Recife** — testes com ônibus autônomo

Desafios atuais: sinalização, mapeamento 3D e infraestrutura 5G.

### Características de Complexidade do Sistema
- **Dinamicidade**: rotas ajustadas em tempo real (trânsito, clima, urgência)
- **Regulamentação**: registro de temperatura durante o trajeto e assinatura digital do recebedor para medicamentos controlados
- **Segurança física e cibernética**: prevenção de roubos, autenticação do destinatário, proteção contra ataques
- **Interoperabilidade**: integração com sistemas legados de farmácias, órgãos reguladores e prefeitura
- **Confiabilidade**: tolerância a falhas de comunicação, decisões autônomas com supervisão humana

### Stakeholders e Preocupações
| Stakeholder | Principais preocupações |
|---|---|
| Solicitante | Facilidade de uso, prazo confiável, acompanhamento, integridade do medicamento |
| Operador da Central | Visão consolidada da frota, alertas de anomalias, controle remoto |
| Motorista de Reserva | Chamados claros, acesso rápido ao veículo/carga, procedimentos de segurança |
| Administrador | Configuração de parâmetros, gestão de usuários/veículos, auditoria de logs |
| Órgão Regulador | Dados precisos de rastreamento/temperatura, conformidade com RDC Anvisa |
| Parceiros (Farmácias) | Integração simples, visibilidade do status, condições adequadas |
| Segurança Pública | Mecanismos anticrime, comunicação com a polícia em incidentes |

## Atividade Prática Proposta
Com base no contexto do SGEA, os alunos devem:
1. Preencher tabelas de **Requisitos Funcionais (RF)** e **Requisitos Não Funcionais (RNFR)**, indicando natureza (usabilidade, confiabilidade, segurança, desempenho, escalabilidade) e tipo (obrigatório/desejável).
2. Elaborar quatro diagramas UML:
   - **Casos de Uso** — atores identificados e ao menos 5 casos de uso significativos
   - **Classes** — entidades principais (VeiculoAutonomo, Entrega, Rota, Sensor, Alerta, Operador, Cliente) com atributos e relacionamentos
   - **Sequência** — cenário crítico: solicitação de entrega urgente, alocação de VGA, roteirização dinâmica e início do monitoramento
   - **Atividades** — cenário de anomalia grave: falha em sensor, parada urgente do veículo e apoio humano

## Ferramentas para Criação dos Diagramas
- **DeepSeek** (chat.deepseek.com) — geração do código Mermaid dos diagramas
- **Mermaid Live Editor** (mermaid.live) — colar o código e visualizar o diagrama renderizado (opção "Edit in Playground")
- **VS Code**: instalar a extensão **Mermaid Viewer** (ou **Mermaid Preview**), criar arquivo `.md` ou `.mmd` com o código Mermaid e usar o botão "Preview Diagram" (ícone M) para visualizar

## Entrega no Classroom
Arquivo em **PDF** contendo:
- Título do projeto: *Sistema Autônomo de Entregas de Medicamentos*
- Nome completo do aluno
- Período (Manhã ou Noite)
- Tabelas de Requisitos Funcionais e Não Funcionais
- Diagramas: Casos de Uso / Classes / Atividades / Sequência

## Referências Bibliográficas
- VALENTE, M. T. *Engenharia de Software Moderna: Princípios e Práticas para Desenvolvimento de Software com Produtividade*. Independente, 2020.
- SWEBOK. *Guide to the Software Engineering Body of Knowledge*, Version 3.0, IEEE Computer Society, 2014. Disponível em: www.swebok.org