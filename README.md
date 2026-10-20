# UniBank

Sistema de gestão financeira pessoal integrado via **Open Finance**: centraliza saldo, movimentações, categorias, gráficos e relatórios de diferentes instituições financeiras em um único painel.

Projeto da disciplina de **Engenharia de Software** (Ciência da Computação, UFG) — **Grupo 7, Ponto e Vírgula**:
Antônio Couto de Carvalho Júnior, Miguel Venâncio Bertol, Gustavo Bueno Ferreira e Igor Reis Braziel.

## Protótipo navegável

**https://igorbraziel.github.io/unibank-es/prototipo/**

O protótipo é uma página única em HTML, CSS e JavaScript, sem backend: todos os dados são fictícios e ficam apenas na memória da aba. O botão **Mapa do protótipo**, no canto inferior direito, dá acesso direto às telas T01 a T16, simula os fluxos alternativos e preenche os acessos de demonstração:

| Perfil | E-mail | Senha |
| :--- | :--- | :--- |
| Usuário final | `ana.souza@email.com` | `unibank123` |
| Administrador | `admin@unibank.com.br` | `admin123` |

Fluxo principal (RF02, diagrama de sequência): **Entrar → Conectar conta → Banco Horizonte → Continuar → Autorizar compartilhamento**.

## Entregas

| Documento | Arquivo |
| :--- | :--- |
| Atividade prática completa (UML + UX/UI) — **entrega final** | [`entregas/UniBank - Atividade Prática - UML e UX-UI.pdf`](entregas/) |
| Atividade 1: Modelagem UML | [`entregas/UniBank - Atividade 1 - Modelagem UML.pdf`](entregas/) |
| Atividade 2: Design de UX/UI e Prototipação | [`entregas/UniBank - Atividade 2 - Design de UX-UI.pdf`](entregas/) |

Os entregáveis também ficam na pasta do projeto no Google Drive.

## Estrutura do repositório

```
.
├── docs/        # documentação, elicitação, requisitos, user stories e priorização MoSCoW
├── uml/         # fontes PlantUML e imagens dos diagramas de classes, componentes e sequência
├── prototipo/   # protótipo navegável (index.html), publicado pelo GitHub Pages
├── relatorio/   # fontes LaTeX dos PDFs, imagens das telas e fontes Roboto
└── entregas/    # PDFs entregues
```

## Documentação

1. [Documentação do projeto](docs/01-documentacao-do-projeto.md): problema, escopo, riscos e modelo de processo (Incremental)
2. [Usuários e funcionalidades](docs/02-usuarios-e-funcionalidades.md)
3. [Elicitação de requisitos](docs/03-elicitacao-de-requisitos.md)
4. [Requisitos funcionais, não funcionais e user stories](docs/04-requisitos-e-user-stories.md)
5. [Priorização MoSCoW](docs/05-priorizacao-moscow.md)

## Como gerar os artefatos

**Diagramas UML** (requer [PlantUML](https://plantuml.com)):

```bash
cd uml
plantuml -tpng 01_classes.puml 02_componentes.puml 03_sequencia_rf02.puml
```

**PDFs** (requer XeLaTeX com os pacotes `fontspec`, `tikz`, `xltabular`, `tcolorbox` e `titlesec`):

```bash
cd relatorio
xelatex unibank-final.tex && xelatex unibank-final.tex   # atividade prática completa
xelatex atividade2.tex && xelatex atividade2.tex         # somente a Atividade 2
```

**Protótipo:** basta abrir `prototipo/index.html` em um navegador. As fontes (Bricolage Grotesque e IBM Plex) são carregadas do Google Fonts.

## Ferramentas

PlantUML, LaTeX, HTML/CSS/JavaScript, Google Fonts, Playwright (testes e capturas das telas) e Claude (Anthropic), como IA generativa de apoio. Os prompts utilizados estão registrados nos PDFs.
