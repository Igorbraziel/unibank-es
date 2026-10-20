# UniBank: Priorização de Requisitos (MoSCoW)

*Grupo 7, Ponto e Vírgula*

## Critérios adotados

| Categoria | Critério utilizado pela equipe |
| :--- | :--- |
| **Must have** | Sem o requisito, o produto não cumpre seu objetivo central (centralizar dados financeiros via Open Finance) ou descumpre exigências legais e regulatórias (LGPD, Open Finance Brasil). |
| **Should have** | Agrega valor relevante ao usuário, mas o sistema funciona sem ele no primeiro incremento. |
| **Could have** | Desejável, com impacto menor. É implementado apenas se houver tempo e recursos. |
| **Won't have (nesta versão)** | Fora do escopo atual. Pode ser reavaliado em versões futuras. |

## Priorização das User Stories

| Prioridade | User Story | Justificativa |
| :--- | :--- | :--- |
| **Must** | US01: Cadastro e login | É a base de acesso e segurança. Nenhuma outra funcionalidade existe sem ela. |
| **Must** | US02: Conectar conta via Open Finance | É o núcleo da proposta de valor, a centralização via Open Finance. |
| **Must** | US03: Consultar saldo consolidado | Entrega direta do objetivo do software, que é ver a situação financeira em um só lugar. |
| **Must** | US04: Visualizar movimentações | Sem o extrato, os dados centralizados não têm utilidade prática. |
| **Must** | US12: Desconectar instituição | A revogação do consentimento é exigência da LGPD e do Open Finance. |
| **Should** | US05: Cadastro manual de receita/despesa | Complementa os dados automáticos (ex.: dinheiro em espécie), mas o sistema funciona sem ele. |
| **Should** | US06: Categorizar transações | É importante para a análise de gastos e é pré-requisito dos gráficos. Não bloqueia o uso básico. |
| **Should** | US07: Dashboard financeiro | Tem alto valor para a tomada de decisão. Parte da informação essencial já é coberta pela US03. |
| **Should** | US10: Gerenciar contas conectadas | Dá controle ao usuário. A desconexão (Must) pode ser entregue antes, a partir da lista de contas. |
| **Should** | US11: Atualizar dados financeiros | Garante dados atualizados, mas a sincronização periódica automática já atende o caso básico. |
| **Should** | US13: Logs de auditoria (visualização) | A geração dos logs é obrigatória (RNF05). A interface de consulta para o administrador pode vir depois. |
| **Could** | US08: Gerar relatórios exportáveis | Útil para análise histórica, mas o dashboard e o extrato já suprem a necessidade inicial. |
| **Could** | US09: Gráficos de gastos | Melhora a visualização, porém depende da categorização (US06) e não é essencial. |
| **Could** | US14: Status de deploy | Apoia a operação interna, sem impacto direto no usuário final. |
| **Won't** | Concessão de empréstimos, abertura de contas, consultoria personalizada e compra/venda de investimentos | Estão definidos como fora do escopo do projeto. |
| **Won't** | Categorização automática por IA, notificações/alertas de gastos e aplicativo mobile nativo | São evoluções possíveis, mas excedem a capacidade desta versão. |

## Priorização dos Requisitos Não Funcionais

| Prioridade | Requisito | Justificativa |
| :--- | :--- | :--- |
| **Must** | RNF01: Criptografia | Trata-se de dados financeiros sensíveis, e um vazamento é o risco mais grave do projeto. |
| **Must** | RNF02: Conformidade LGPD/Open Finance | É obrigação legal. Sem ela, a integração não pode operar. |
| **Must** | RNF04: Tolerância à indisponibilidade | A indisponibilidade de instituições é um risco já identificado, e o sistema depende de múltiplas fontes externas. |
| **Must** | RNF05: Logs auditáveis e imutáveis | Rastreabilidade é exigência regulatória para ações sensíveis. |
| **Must** | RNF08: Isolamento de falhas de integração | Evita que a falha de uma API comprometa o sistema inteiro. |
| **Should** | RNF03: Saldo em até 3 s | É importante para a experiência, mas não impede o funcionamento. |
| **Should** | RNF06: Usabilidade sem treinamento | É relevante para a adoção e pode ser refinada ao longo dos incrementos. |
| **Could** | RNF07: Escalabilidade | Não é crítica no contexto inicial, que tem um volume reduzido de usuários. |
