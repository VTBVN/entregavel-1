# Startellite — Engenharia de Produto, Qualidade e Evolução da Plataforma

> Entrega intermediária 1 — definição e estruturação  
> Insper Code Jr. — semestre 2026.2  
> Entrega final do case: 29/10/2026 · apresentação: 30/10/2026

## Descrição do projeto

A Startellite é uma plataforma que conecta desenvolvedores de software a projetos, missões e oportunidades corporativas. O produto já opera em produção e possui regras de autorização e integrações reais. Este projeto evolui a plataforma de forma incremental, demonstrável e com baixo risco, sem reescrever o sistema nem interferir em fluxos críticos.

O trabalho está dividido em cinco frentes:

1. Frente 0 — ambiente reproduzível de homologação com Supabase e dados fictícios;
2. Frente A — página pública compartilhável de Espaçonaves;
3. Frente B — testes automatizados e integração contínua em Pull Requests;
4. Frente C — Design System aditivo utilizado pela nova página;
5. Frente D — aprimoramento do assistente de IA Orbitinho.

## Objetivo

Fortalecer a base de engenharia da aplicação e entregar uma nova superfície pública do produto, preservando privacidade, segurança e compatibilidade com a operação existente.

## Tecnologias previstas

- TypeScript e JavaScript;
- React e Next.js, com SSR, rotas dinâmicas, SEO e OpenGraph;
- PostgreSQL e Supabase (migrations, RLS, Storage e seed);
- pgTAP e o framework de testes já adotado pelo repositório;
- GitHub Actions para CI;
- Storybook ou ferramenta equivalente aprovada pelo cliente;
- APIs/modelos de IA e Web Speech já compatíveis com a arquitetura do Orbitinho.

Versões, gerenciador de pacotes e comandos exatos serão registrados após o handover do repositório. Nenhuma nova dependência paga será adotada sem aprovação do cliente.

## Integrantes e responsabilidades
Victor Barbosa Viana exerce simultaneamente os papéis de **Scrum Master** e **Product Owner**. Sua atuação é exclusivamente de produto e facilitação: priorização e manutenção do backlog, definição e validação de objetivos, alinhamento com o cliente, facilitação das cerimônias e remoção de impedimentos. Victor **não desenvolverá, revisará, aprovará nem integrará código**, nem será responsável por migrations, CI, testes automatizados ou deploy.


| Integrante | Responsabilidade principal | Apoio e revisão |
|---|---|---|
| Victor Barbosa Viana | Scrum Master e Product Owner — produto, backlog, cerimônias e aceite | Alinhamento com cliente e remoção de impedimentos; sem atuação em código |
| Pedro Pereira | Frente D — Orbitinho; liderança técnica e integração | Revisão de arquitetura, privacidade, segurança, banco e IA |
| Wesley Lima Silva | Frente 0 — homologação; Frente B — testes e CI | Apoio à página pública e ao Design System |
| Guilherme Kenzo Taba Nakamura | Frente A — página pública; Frente C — componentes necessários | Testes de frontend e documentação visual |
| Thiago Brasileiro de Sousa | Entregas assistidas no Orbitinho e em testes | Documentação, demonstração e casos de regressão |

A distribuição técnica considera experiência declarada, interesse, disponibilidade e senioridade. Victor mantém a responsabilidade de produto e facilitação durante todo o ciclo; a distribuição técnica será revista ao final da segunda semana, quando a homologação deve estar validada.

## Escopo essencial

- reconstrução previsível do ambiente de homologação sem dados de produção;
- rota pública `/spaceships/[slug]` com SSR, OpenGraph e ativação por `is_public`;
- exposição de dados por lista branca, sem leitura anônima das tabelas base;
- Portfólio, Tripulação e CTA “Fazer Proposta” com consentimento, validação e mitigação de abuso;
- CI com typecheck, lint e testes em PRs;
- testes unitários e testes de RLS selecionados com o cliente;
- componentes reutilizáveis documentados e usados na página pública;
- melhorias incrementais, seguras e demonstráveis no Orbitinho.

O detalhamento está em [docs/REQUISITOS.md](docs/REQUISITOS.md) e o plano de execução em [docs/BACKLOG.md](docs/BACKLOG.md).

## Fora de escopo

- separar frontend e backend em repositórios diferentes;
- converter genericamente Server Actions em REST;
- adotar AWS ou migrar arquivos para S3;
- alterar pagamentos, faturamento, webhooks, cron jobs, OAuth ou APIs públicas existentes;
- reformular todo o Design System ou migrar todas as telas legadas;
- executar DDL diretamente em produção.

## Organização e fluxo de trabalho

- `main`: branch protegida e sob governança do cliente;
- `develop`, se aprovada pelo cliente: integração antes de `main`;
- branches curtas: `feat/ST-<id>-descricao`, `fix/ST-<id>-descricao`, `docs/ST-<id>-descricao`;
- commits objetivos, preferencialmente no padrão Conventional Commits;
- toda mudança entra por Pull Request ligado a um item do backlog;
- Victor mantém o Product Backlog, prioriza itens e valida o aceite funcional; essa atuação não inclui alterações em código;
- Victor facilita Planning, Daily, Review e Retrospective e remove impedimentos;
- PR deve conter contexto, evidência, testes e riscos;
- mudanças em dados públicos, RLS, migrations ou IA exigem revisão de Pedro;
- não integrar PR com typecheck, lint ou testes falhando.

Detalhes em [CONTRIBUTING.md](CONTRIBUTING.md).

## Estrutura prevista do repositório do produto

```text
.
├── .github/workflows/       # integração contínua
├── app/spaceships/[slug]/   # página pública (ajustar à estrutura real)
├── components/ui/           # Design System aditivo
├── docs/                    # requisitos, decisões e instruções
├── supabase/
│   ├── migrations/
│   ├── tests/
│   ├── config.toml
│   └── seed.sql
├── .env.example
└── README.md
```

Esta estrutura é uma proposta inicial e não autoriza uma reorganização ampla da base existente.

## Documentos da entrega

- [Documento de requisitos](docs/REQUISITOS.md)
- [Backlog priorizado](docs/BACKLOG.md)
- [Imagem do backlog](docs/evidencias/backlog-inicial.png)
- [Registro de alinhamento com o cliente](docs/ALINHAMENTO_CLIENTE.md)
- [Definição de pronto](docs/DEFINITION_OF_DONE.md)
- [Fluxo de contribuição](CONTRIBUTING.md)

## Fontes

- Case técnico “Startellite 2026.2 — Engenharia de Produto, Qualidade e Evolução da Plataforma”, fornecido pelo cliente/Insper Code Jr.;
- respostas do formulário de mapeamento técnico do time, consultadas em 10/09/2026;
- [site institucional da Startellite](https://startellite.com/);
- [orientações de entregáveis da Insper Code Jr.](https://inspercodejr.github.io/material-didatico-26-2/reunioes/).

