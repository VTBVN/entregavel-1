# Registro do alinhamento com o cliente

## Evidências

- Print/foto da reunião: **pendente de anexação pela equipe**.
- Destino sugerido: `docs/evidencias/reuniao-cliente-AAAA-MM-DD.jpg`.
- Não foi criada uma evidência artificial. Antes da submissão, anexar uma imagem autorizada e registrar data, participantes e consentimento de uso.

## Entendimento consolidado

- O produto já está em produção; a equipe fará evolução incremental, não reescrita.
- Produção, branch principal e deploy permanecem sob governança do cliente.
- O time trabalhará por branches e Pull Requests pequenos.
- O cliente fornecerá repositório, handover, dump somente de estrutura e credenciais de homologação por canal seguro.
- A página pública deve usar ativação explícita e lista branca de dados.
- Pagamentos, webhooks, cron jobs, OAuth, APIs públicas existentes, AWS e migração completa de legado não fazem parte do case.
- Haverá alinhamento semanal, ajuste flexível de pessoas e demonstrações incrementais.

## Decisões propostas para validação

| ID | Proposta | Estado |
|---|---|---|
| DEC-01 | Pedro lidera Orbitinho e revisa mudanças críticas | A validar com Pedro/cliente |
| DEC-02 | Wesley lidera homologação e CI/testes | A validar com cliente |
| DEC-03 | Guilherme lidera página pública e componentes estritamente necessários | A validar com cliente |
| DEC-04 | Thiago executa fatias pequenas de Orbitinho/testes com pareamento | A validar com cliente |
| DEC-05 | O gate da S2 bloqueia integração da página com banco não validado | A validar com cliente |
| DEC-06 | “Criar tarefa” será o primeiro comando demonstrável do Orbitinho | A validar com cliente |

## Dúvidas pendentes

### Repositório e execução

1. Qual é a URL do repositório privado, a branch-base e a política de merge?
2. Quais versões de Node, gerenciador de pacotes e comandos oficiais devem ser usados?
3. Já existem lint, typecheck, testes, Storybook e preview deployments? Quais devem ser preservados?
4. Quem aprova PRs e quem aplica migrations/deploy em produção?

### Homologação e dados

5. Quando serão fornecidos o dump estrutural e o projeto Supabase de homologação?
6. Quais buckets, funções, triggers e policies são indispensáveis ao recorte?
7. Quais estados fictícios de empresas, satélites, Espaçonaves e missões devem existir no seed?

### Página pública e privacidade

8. Como o slug será criado, alterado e reservado? Ele precisa ser único sem diferenciar maiúsculas?
9. Qual é a allowlist definitiva de campos de `public_spaceship_profiles`?
10. Onde ficam registrados os opt-ins de membros e consentimentos de clientes do portfólio?
11. Quais métricas de autoridade podem ser públicas e como são calculadas?
12. Para onde a proposta anônima é enviada, por quanto tempo os dados ficam retidos e qual limite de requisições deve ser aplicado?

### Orbitinho

13. Qual é a arquitetura atual, o modelo utilizado e o orçamento aceitável de tokens/latência?
14. Quais comandos escritos e de voz têm prioridade em desktop e mobile?
15. Quais fontes podem compor a base de conhecimento e quais informações são confidenciais?
16. O que significa “programar para o usuário” neste ciclo: gerar instruções, criar tarefa, produzir patch ou integrar diretamente com IDEs?
17. Quais ações sempre exigem confirmação e quais dados podem ser registrados em logs?

### Gestão

18. Qual será o dia fixo da reunião semanal e quem representa o cliente?
19. O case menciona em trechos diferentes quatro e cinco desenvolvedores; confirmamos que a equipe efetiva é Pedro, Wesley, Guilherme e Thiago?
20. Qual ferramenta será a fonte oficial do backlog e das evidências: Startellite, GitHub Projects ou outra?

## Modelo para as próximas reuniões

```text
Data e participantes:
Evidência:
Entregas demonstradas:
Feedback do cliente:
Decisões tomadas:
Dúvidas/bloqueios:
Mudanças de prioridade ou escopo:
Próximos passos, responsáveis e prazo:
```

