# Aula — Arquitetura de Alto Nível de Software (SWEBOK / Projeto de Software)

## SWEBOK na Engenharia de Software

O **SWEBOK** (Guide to the Software Engineering Body of Knowledge) é estruturado em **12 áreas principais**, que cobrem todo o ciclo de vida do desenvolvimento de software:

1. Engenharia de Requisitos — definição e análise das necessidades do sistema
2. **Projeto de Software** — estruturação do sistema antes da implementação *(foco desta aula)*
3. Construção de Software — codificação e escolha de ferramentas/frameworks
4. Testes de Software — verificação e validação do sistema
5. Manutenção de Software — correção de erros e evolução do sistema
6. Gerência de Configuração — controle de versões e mudanças no código
7. Gerência de Projetos — planejamento, controle e entrega do software
8. Processos de Software — modelos de desenvolvimento (Waterfall, Ágil, etc.)
9. Modelos de Software — representações gráficas (ex: UML)
10. Qualidade de Software — avaliação de fatores internos e externos
11. Prática Profissional — questões éticas e regulatórias
12. Aspectos Econômicos — custos e impacto financeiro no desenvolvimento

## O que é Arquitetura de Alto Nível de Software

É a **estrutura fundamental e macro do sistema**, definindo seus componentes principais, suas interações e os princípios que guiam seu desenvolvimento e evolução.

Foca em decisões estratégicas e de design de alto nível, como:
- a divisão do sistema em subsistemas;
- a comunicação entre eles (APIs, filas);
- a garantia de atributos de qualidade como escalabilidade, segurança e desempenho.

**Analogia**: é como observar a visão externa de um prédio antes de analisar os cômodos ou a instalação elétrica — quantos blocos existem, como eles se conectam e qual é a função de cada parte. Em software, essa arquitetura mostra os principais elementos do sistema e suas integrações, **sem detalhar código, classes ou lógica interna**.

## Objetivo da Arquitetura de Alto Nível

Tem como finalidade:
- fornecer visão estratégica do sistema;
- facilitar o entendimento geral da solução;
- apoiar decisões arquiteturais;
- identificar integrações externas;
- permitir que diferentes profissionais compreendam o sistema.

Normalmente responde a perguntas como:
- O sistema será web, mobile ou ambos?
- Existe API de comunicação?
- O sistema utiliza banco de dados?
- Há integração com serviços externos?
- O sistema está na nuvem ou localmente?

Essa visão é importante principalmente para **arquitetos de software, gestores de tecnologia, equipes de desenvolvimento e stakeholders** do projeto.

## Elementos comuns na Arquitetura de Alto Nível

Componentes que aparecem com frequência nessa visão:
- Cliente / Usuário
- Frontend (interface do sistema)
- Backend (serviços e regras de negócio)
- Banco de Dados
- Integrações externas (pagamento, e-mail, APIs externas)
- Serviços de infraestrutura (nuvem, CDN, autenticação)

Esses elementos aparecem apenas como **blocos principais**, sem detalhar como são implementados.

## Serviço de Infraestrutura: CDN (Content Delivery Network)

Uma **CDN** é uma rede de servidores distribuídos em diferentes regiões geográficas, com o objetivo de entregar conteúdos de um sistema/site de forma mais rápida aos usuários.

Em vez de todos os usuários acessarem diretamente o servidor principal, a CDN **armazena cópias de conteúdos estáticos** (imagens, CSS, JavaScript) em vários servidores espalhados pelo mundo. Assim, o conteúdo é entregue pelo servidor mais próximo do usuário.

**Exemplo — e-commerce:**
- *Sem CDN*: Usuário → Servidor principal → Imagem do produto (risco de sobrecarga com muitos acessos simultâneos)
- *Com CDN*: Usuário → Servidor CDN mais próximo → Imagem do produto (acesso mais rápido, servidor principal trabalha menos)

**Outros exemplos de uso**: streaming de vídeo, redes sociais, serviços de música, portais de notícias.

**Provedores conhecidos de CDN**: Cloudflare, Amazon CloudFront, Akamai, Google Cloud CDN.

## Exemplo prático — Arquitetura de Alto Nível de um E-commerce

Cenário: um sistema de loja virtual onde o usuário acessa produtos, adiciona itens ao carrinho, realiza pagamentos e recebe confirmação por e-mail.

**Principais blocos identificados:**

| Componente | Função |
|---|---|
| Cliente (Usuário) | Acessa o sistema via navegador ou aplicativo |
| Frontend | Interface visual — exibe produtos, carrinho e telas de compra |
| Backend (API) | Processa regras de negócio (cadastro, pedidos, validação de pagamento) |
| Banco de Dados | Armazena usuários, produtos, pedidos e estoque |
| Gateway de Pagamento | Sistema externo que processa pagamentos (cartão, PIX, boleto) |
| Serviço de E-mail | Envia confirmações ao cliente |

**Fluxo principal:**
```
Cliente → Frontend → Backend → Banco de Dados
Backend → Gateway de Pagamento
Backend → Serviço de E-mail
```

Esse fluxo pode ser representado com um diagrama de componentes (ex: em **PlantUML**), mostrando cliente, frontend, backend, banco de dados e serviços externos conectados por setas de comunicação — sem detalhar classes, tabelas ou algoritmos internos.

## Benefícios da Arquitetura de Alto Nível

- Facilita a compreensão inicial do sistema.
- Ajuda na comunicação entre equipes.
- Permite identificar dependências externas.
- Reduz a complexidade do projeto.
- Apoia o planejamento tecnológico.

É muito utilizada em **documentação arquitetural** e **apresentações de projeto**.

## Resumo geral

A Arquitetura de Alto Nível mostra:
- as grandes partes do sistema;
- como elas se relacionam;
- quais são os principais blocos tecnológicos;
- onde o sistema se integra com o mundo externo.

**Não entra em detalhes de código.** Analogia final: é como olhar o prédio por fora antes de analisar os cômodos.

## Referências bibliográficas

- SWEBOK. *Guide to the Software Engineering Body of Knowledge*, Version 3.0, IEEE Computer Society, 2014.
- SOMMERVILLE, Ian. *Engenharia de software*. 10. ed. São Paulo: Pearson, 2019.
- PRESSMAN, Roger S.; MAXIM, Bruce R. *Engenharia de software: uma abordagem profissional*. 8. ed. Porto Alegre: AMGH, 2016.