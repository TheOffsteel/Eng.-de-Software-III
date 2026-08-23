# Resumo — Sistema Autônomo de Entrega de Medicamentos (SGEA)

## Contexto
O documento apresenta um exercício de engenharia de requisitos e modelagem UML para um sistema de entrega autônoma de medicamentos por Veículos Autônomos (VGA). O trabalho cobre a especificação de requisitos funcionais e não funcionais, além de quatro diagramas UML/mermaid que descrevem a arquitetura e o comportamento do sistema.

## 1. Requisitos

### Requisito Funcional (RF-01)
**Processar solicitação de entrega urgente**: o sistema permite que o Solicitante registre uma entrega urgente informando medicamento, endereços de origem/destino e prioridade. O sistema deve então:
- Alocar automaticamente o VGA disponível mais próximo;
- Calcular rota dinâmica considerando trânsito, interdições e clima em tempo real;
- Monitorar continuamente localização, temperatura e status até a confirmação de recebimento.

### Requisitos Não Funcionais associados
| Código | Natureza | Tipo | Resumo |
|---|---|---|---|
| RNFR-01.1 | Desempenho | Obrigatório | Alocação de VGA e cálculo de rota inicial em até 5 segundos |
| RNFR-01.2 | Confiabilidade | Obrigatório | Disponibilidade mínima de 99,5% nos módulos de alocação/roteirização, com tolerância a falhas de comunicação |
| RNFR-01.3 | Segurança | Obrigatório | Dados de rastreamento, temperatura e identificação transmitidos com criptografia (TLS 1.2+) |
| RNFR-01.4 | Usabilidade | Obrigatório | Alertas de entregas urgentes exibidos com destaque visual/sonoro em até 2 segundos |
| RNFR-01.5 | Escalabilidade | Desejável | Suporte a pelo menos 500 solicitações urgentes simultâneas sem degradação perceptível |

## 2. Diagramas Apresentados

### a) Diagrama de Casos de Uso
Mapeia os atores e suas interações com o sistema:
- **Solicitante**: solicitar entrega, acompanhar entrega, confirmar recebimento;
- **Operador da Central**: monitorar frota, gerenciar anomalias;
- **Motorista de Reserva**: atender intervenção manual;
- **Administrador do Sistema**: configurar sistema, cadastrar veículos;
- **Órgão Regulador**: receber dados de rastreabilidade;
- **Sistema de Trânsito Municipal**: fornecer dados de trânsito;
- **Sistema de Farmácias**: confirmar disponibilidade de medicamento.

### b) Diagrama de Classes
Modela as principais entidades e seus relacionamentos:
- **Cliente** → solicita → **Entrega**
- **Entrega** → atribuída a → **VeiculoAutonomo**
- **VeiculoAutonomo** → segue → **Rota**; → possui → **Sensor**
- **Sensor** → gera → **Alerta**
- **Operador** → trata → **Alerta**

Cada classe define atributos e métodos principais (ex.: `VeiculoAutonomo` tem `alocar()`, `iniciarRota()`, `pararEmergencia()`).

### c) Diagrama de Sequência
Descreve o fluxo de uma solicitação de entrega urgente entre **Cliente**, **Sistema SGEA**, **VeiculoAutonomo (VGA)** e **Sensor**:
1. Cliente solicita entrega urgente;
2. Sistema valida a solicitação;
3. Sistema aloca o VGA disponível e recebe confirmação;
4. Sistema calcula a rota dinâmica e a envia ao VGA;
5. VGA inicia monitoramento via Sensor, que envia dados em tempo real;
6. Sistema notifica o Cliente que a entrega está em andamento.

### d) Diagrama de Atividades
Representa o fluxo de tratamento de falhas detectadas por sensores:
1. Sensor detecta falha crítica;
2. Sistema avalia se a falha compromete a segurança:
   - **Se sim**: aciona parada urgente, dispara alerta crítico, notifica o Operador, que aciona um Motorista de Reserva. O motorista se desloca, avalia o veículo e decide se o VGA pode retomar operação autônoma ou se precisa ser rebocado com transferência de carga;
   - **Se não**: registra alerta de baixa severidade e a rota continua normalmente.
3. Fluxo se encerra em ambos os casos.

## Conclusão
O material integra requisitos de negócio (desempenho, segurança, confiabilidade, usabilidade e escalabilidade) com modelagem visual (casos de uso, classes, sequência e atividades), demonstrando como uma entrega urgente é processada de ponta a ponta — desde a solicitação do cliente até o tratamento de falhas críticas em campo.

[PDF da Atividade Preenchida](../Assets/Sistema%20Autônomo%20de%20Entrega%20de%20Medicamentos%20-%20Entrega.pdf)