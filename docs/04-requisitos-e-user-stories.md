# UniBank — Requisitos Funcionais, Não Funcionais e User Stories

Grupo 7 — Ponto e Vírgula

## 1. Requisitos Funcionais (RF)

| ID | Requisito | Ator |
| :--- | :--- | :--- |
| RF01 | Cadastrar usuário e realizar login | Usuário Final |
| RF02 | Conectar contas via Open Finance | Usuário Final |
| RF03 | Consultar saldo das contas conectadas | Usuário Final |
| RF04 | Visualizar movimentações financeiras | Usuário Final |
| RF05 | Cadastrar receitas/despesas manualmente | Usuário Final |
| RF06 | Categorizar receitas e despesas | Usuário Final |
| RF07 | Visualizar dashboard financeiro | Usuário Final |
| RF08 | Gerar relatórios financeiros | Usuário Final |
| RF09 | Visualizar gráficos de receitas/despesas/categorias | Usuário Final |
| RF10 | Gerenciar contas/instituições conectadas | Usuário Final |
| RF11 | Atualizar dados financeiros das contas conectadas | Usuário Final |
| RF12 | Desconectar uma instituição financeira | Usuário Final |
| RF13 | Gerar logs de auditoria | Admin |
| RF14 | Visualizar status de deploy dos serviços | Admin |

## 2. Requisitos Não Funcionais (RNF)

| ID | Requisito | Categoria |
| :--- | :--- | :--- |
| RNF01 | Dados financeiros sensíveis devem ser criptografados em trânsito e em repouso | Segurança |
| RNF02 | O sistema deve estar em conformidade com a LGPD e com as normas do Open Finance Brasil (Banco Central) | Conformidade |
| RNF03 | O saldo consolidado deve ser exibido em até 3 s após login (dado em cache válido) | Performance |
| RNF04 | O sistema deve tolerar indisponibilidade temporária de uma instituição financeira sem bloquear o uso das demais contas | Disponibilidade |
| RNF05 | Toda ação sensível (login, conexão/desconexão de conta, exclusão) deve gerar log auditável e imutável | Auditabilidade |
| RNF06 | A interface do dashboard deve ser compreensível sem treinamento prévio | Usabilidade |
| RNF07 | O sistema deve suportar crescimento de usuários e instituições conectadas sem degradação perceptível | Escalabilidade |
| RNF08 | Falhas de integração com uma API de Open Finance não devem propagar erro para o restante do sistema | Confiabilidade |

## 3. User Stories

**US01 — Cadastro e login** *(RF01)*
Como usuário final, eu quero criar uma conta e fazer login de forma segura, para acessar minhas informações financeiras de forma protegida.
- Dado que informo dados válidos de cadastro, quando confirmo, então minha conta é criada e recebo confirmação.
- Dado que informo credenciais corretas, quando faço login, então acesso o sistema; se incorretas, recebo mensagem de erro sem expor qual campo está errado.

**US02 — Conectar conta via Open Finance** *(RF02, RNF02)*
Como usuário final, eu quero conectar minhas contas bancárias via Open Finance, para centralizar minhas finanças em um só lugar.
- Dado que seleciono uma instituição suportada, quando autorizo o compartilhamento, então a conta aparece como conectada em até X minutos.
- Dado que a instituição não responde, quando tento conectar, então recebo mensagem clara de falha, sem quebrar o restante do app (RNF08).

**US03 — Consultar saldo consolidado** *(RF03, RNF03)*
Como usuário final, eu quero ver o saldo de todas as minhas contas em um só painel, para saber minha situação financeira rapidamente.
- Dado que tenho contas conectadas, quando abro a tela inicial, então vejo o saldo total e por conta em até 3 s (com dado em cache, se aplicável).

**US04 — Visualizar movimentações** *(RF04)*
Como usuário final, eu quero visualizar minhas transações recentes, para acompanhar meus gastos.
- Dado que tenho movimentações no período, quando acesso o extrato, então vejo data, valor, descrição e conta de origem, ordenadas por data.

**US05 — Cadastro manual de receita/despesa** *(RF05)*
Como usuário final, eu quero registrar receitas e despesas manualmente, para incluir gastos não capturados automaticamente (ex.: dinheiro em espécie).
- Dado que preencho valor, data e descrição, quando salvo, então o lançamento aparece no extrato e entra nos totais do dashboard.

**US06 — Categorizar transações** *(RF06)*
Como usuário final, eu quero categorizar minhas receitas e despesas, para entender em que estou gastando mais.
- Dada uma transação sem categoria, quando seleciono uma categoria, então ela é salva e refletida nos gráficos/relatórios.

**US07 — Dashboard financeiro** *(RF07, RNF06)*
Como usuário final, eu quero visualizar um resumo financeiro consolidado, para tomar decisões rápidas sobre meus gastos.
- Dado que possuo dados de ao menos uma conta, quando acesso o dashboard, então vejo saldo total, gastos por categoria e comparativo com o mês anterior.

**US08 — Gerar relatórios** *(RF08)*
Como usuário final, eu quero gerar relatórios financeiros por período, para analisar minha evolução financeira.
- Dado que seleciono um intervalo de datas, quando gero o relatório, então recebo um resumo (receitas, despesas, saldo) exportável (ex.: PDF/CSV).

**US09 — Gráficos de gastos** *(RF09)*
Como usuário final, eu quero ver gráficos de receitas, despesas e gastos por categoria, para visualizar padrões de consumo.
- Dado que existem transações categorizadas, quando acesso a aba de gráficos, então vejo, no mínimo, um gráfico de pizza por categoria e um de linha por período.

**US10 — Gerenciar contas conectadas** *(RF10)*
Como usuário final, eu quero visualizar e gerenciar todas as instituições conectadas, para ter controle sobre quais dados compartilho.
- Dado que tenho contas conectadas, quando acesso "Minhas conexões", então vejo lista com status (ativa/expirada) de cada instituição.

**US11 — Atualizar dados financeiros** *(RF11)*
Como usuário final, eu quero atualizar manualmente os dados de uma conta conectada, para garantir que as informações estejam corretas.
- Dada uma conta conectada, quando aciono "atualizar", então o sistema busca novos dados na instituição e atualiza saldo/extrato, ou informa erro se a instituição estiver indisponível.

**US12 — Desconectar instituição** *(RF12, RNF05)*
Como usuário final, eu quero desconectar uma instituição financeira, para revogar o acesso quando não quiser mais compartilhar dados.
- Dada uma conta conectada, quando confirmo a desconexão, então o acesso é revogado, a conta some do dashboard e a ação é registrada em log.

**US13 — Logs de auditoria** *(RF13, RNF05)*
Como administrador, eu quero visualizar logs de ações críticas dos usuários, para garantir rastreabilidade e conformidade regulatória.
- Dado que uma ação sensível ocorre (login, conexão, exclusão), quando consulto os logs, então vejo usuário, ação, timestamp e resultado, de forma imutável.

**US14 — Status de deploy** *(RF14)*
Como administrador, eu quero visualizar o status de deploy dos serviços, para identificar rapidamente falhas de infraestrutura.
- Dado que um serviço está fora do ar, quando acesso o painel de status, então vejo o serviço marcado como "indisponível" com horário da última verificação.
