# Documentação do Projeto — Engenharia de Software

**Grupo 7 — Ponto e Vírgula**

## 1. Identificação da equipe

| Campo | Valor |
| :--- | :--- |
| Nome da equipe | UniBank |
| Grupo | 7 |
| Integrantes | Antônio Couto de Carvalho Júnior, Miguel Venâncio Bertol, Gustavo Bueno Ferreira, Igor Reis Braziel |

## 2. Ideias iniciais de software

Na etapa de formação das equipes, foram levantadas duas ideias de software pelo grupo:

- Sistema de gestão financeira integrado via Open Finance
- Monitoramento de fornecedores e mercado do setor agropecuário

A equipe optou por seguir com a primeira ideia, detalhada a seguir.

## 3. Definição do produto

A equipe optou por desenvolver um sistema de gestão financeira pessoal integrado via Open Finance, consolidando as duas ideias iniciais em um único produto focado em finanças.

### 3.1 Contexto e problema

| Item | Descrição |
| :--- | :--- |
| Contexto | Pessoas que desejam centralizar e acompanhar sua vida financeira em um único sistema. |
| Problema | Descentralização dos dados financeiros, o que dificulta a tomada de decisões financeiras. |
| Justificativa | Gestão financeira é um problema inerentemente complexo, com o aumento de opções de instituições financeiras e o volume de dados atrelados a um só indivíduo; uma abordagem centralizadora facilita a tomada de decisões. |
| Objetivo do software | Centralizar informações financeiras de diferentes instituições, facilitando o controle de gastos, planejamento e tomada de decisões financeiras. |

### 3.2 Público e stakeholders

| Item | Descrição |
| :--- | :--- |
| Público-alvo / usuários | Pessoas que possuem contas em diferentes instituições financeiras e desejam centralizar, organizar e acompanhar suas finanças em um único sistema. |
| Stakeholders | Usuários finais, instituições financeiras, administradores do sistema, órgãos reguladores. |

### 3.3 Escopo

**Dentro do escopo:**

- Integração com instituições financeiras via Open Finance
- Centralização de contas e cartões
- Controle de receitas e despesas
- Categorização de gastos
- Dashboard e relatórios financeiros

**Fora do escopo:**

- Concessão de empréstimos
- Abertura de contas bancárias
- Consultoria financeira personalizada
- Operações de compra e venda de investimentos

### 3.4 Principais funcionalidades

- Integração com contas via Open Finance
- Visualização de saldo e movimentações
- Controle de receitas e despesas
- Categorização de gastos
- Dashboard financeiro
- Relatórios e gráficos

### 3.5 Dados e integrações externas

| Item | Descrição |
| :--- | :--- |
| Dados principais | Saldo, transações financeiras, informações pessoais. |
| Sistemas/serviços externos | Bancos digitais do usuário (Open Finance). |

### 3.6 Premissas, riscos e critérios de sucesso

**Premissas:**

- Usuários possuem pelo menos uma conta em um banco compatível com a integração.

**Riscos iniciais:**

- Falhas na integração com o Open Finance
- Vazamento ou perda de dados financeiros
- Problemas de segurança e privacidade
- Indisponibilidade das instituições financeiras
- Dados incorretos ou desatualizados
- Mudanças nas regulamentações do Open Finance

**Critérios de sucesso:**

- Dados financeiros centralizados corretamente
- Integração com Open Finance funcionando
- Redução do tempo para acompanhar as finanças
- Segurança e privacidade dos dados garantidas
- Usuários conseguirem controlar melhor seus gastos

## 4. Modelo de processo de desenvolvimento de software

| Modelo | Favorece o projeto porque... | Dificulta o projeto porque... |
| :--- | :--- | :--- |
| Cascata | Permite definir previamente os requisitos, integrações, segurança e escopo do sistema, facilitando a organização e a documentação. | É pouco flexível para mudanças, principalmente devido a possíveis alterações nas APIs, regulamentações e necessidades dos usuários. |
| Iterativo | Permite desenvolver o sistema em ciclos, realizando testes, recebendo feedback dos usuários e corrigindo problemas durante o desenvolvimento. | Pode gerar retrabalho, pois funcionalidades desenvolvidas anteriormente podem precisar ser modificadas nos ciclos seguintes. |
| Incremental | Permite desenvolver e entregar o sistema por partes, como integração de contas, controle de receitas e despesas, categorização e dashboards. Isso facilita a validação de cada funcionalidade. | A integração entre os diferentes incrementos pode aumentar a complexidade, além de algumas funcionalidades dependerem de outras para funcionar corretamente. |

Com base na análise, o modelo **Incremental** se mostra o mais aderente ao projeto, por permitir a entrega e validação por partes, reduzindo o risco de retrabalho amplo mesmo diante de possíveis mudanças em APIs e regulamentações do Open Finance.
