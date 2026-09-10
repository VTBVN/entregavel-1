# Backlog inicial priorizado

## Convenções

- Prioridade: **P0** essencial/bloqueadora, **P1** importante, **P2** desejável.
- Size: sequência Fibonacci (`1`, `2`, `3`, `5`, `8`), usada para comparação relativa, não como horas.
- Status inicial: `A fazer`, exceto atividades documentais já concluídas neste pacote.
- Pedro revisa itens de IA, arquitetura, privacidade e segurança; Wesley revisa banco/CI; Guilherme revisa UI.

## Itens

| ID | Sprint | Pri. | Size | Frente | Entrega | Responsável | Apoio | Status |
|---|---:|---:|---:|---|---|---|---|---|
| ST-001 | S1 | P0 | 3 | Geral | Handover e mapa da arquitetura atual | Pedro | Todos | A fazer |
| ST-002 | S1 | P0 | 2 | Geral | Confirmar requisitos, dúvidas e critérios com cliente | Pedro | Todos | A fazer |
| ST-003 | S1 | P0 | 3 | 0 | Executar projeto localmente e documentar setup real | Wesley | Pedro | A fazer |
| ST-004 | S1 | P0 | 3 | B | Criar workflow inicial de typecheck e lint em PR | Wesley | Thiago | A fazer |
| ST-005 | S1 | P1 | 3 | C | Inventariar componentes/tokens existentes | Guilherme | Wesley | A fazer |
| ST-006 | S1 | P1 | 3 | D | Mapear arquitetura, intents e riscos do Orbitinho | Pedro | Thiago | A fazer |
| ST-007 | S2 | P0 | 5 | 0 | Restaurar dump estrutural no Supabase de homologação | Wesley | Pedro | A fazer |
| ST-008 | S2 | P0 | 5 | 0 | Sanear migrations e criar `config.toml` | Wesley | Pedro | A fazer |
| ST-009 | S2 | P0 | 5 | 0 | Criar seed fictício representativo | Wesley | Thiago | A fazer |
| ST-010 | S2 | P1 | 3 | 0 | Recriar buckets e policies necessários | Wesley | Pedro | A fazer |
| ST-011 | S2 | P1 | 3 | B | Adicionar estrutura de testes e documentação | Wesley | Thiago | A fazer |
| ST-012 | S2 | P0 | 3 | D | Prototipar melhoria pequena aprovada do Orbitinho | Pedro | Thiago | A fazer |
| ST-013 | S2 | P1 | 3 | C | Preparar Storybook/equivalente e tokens básicos | Guilherme | Wesley | A fazer |
| ST-014 | S3 | P0 | 3 | A | Criar migration de `is_public` e slug conforme modelo aprovado | Guilherme | Wesley/Pedro | A fazer |
| ST-015 | S3 | P0 | 5 | A | Criar view/DTO `public_spaceship_profiles` | Guilherme | Pedro/Wesley | A fazer |
| ST-016 | S3 | P0 | 5 | A | Implementar rota SSR e retorno 404 seguro | Guilherme | Pedro | A fazer |
| ST-017 | S3 | P1 | 3 | B | Testar RLS e exposição anônima da view pública | Wesley | Thiago | A fazer |
| ST-018 | S3 | P1 | 3 | D | Implementar intent e confirmação de “Criar tarefa” | Thiago | Pedro | A fazer |
| ST-019 | S4 | P0 | 5 | A | Implementar header e dados principais da Espaçonave | Guilherme | Wesley | A fazer |
| ST-020 | S4 | P1 | 3 | C | Consolidar componentes usados pelo header | Guilherme | Wesley | A fazer |
| ST-021 | S4 | P0 | 5 | B/A | Criar testes de privacidade e campos proibidos | Wesley | Pedro/Thiago | A fazer |
| ST-022 | S4 | P1 | 5 | D | Implementar sugestões de próximo passo/contexto otimizado | Pedro | Thiago | A fazer |
| ST-023 | S5 | P0 | 5 | A | Implementar aba Portfólio com consentimento | Guilherme | Pedro | A fazer |
| ST-024 | S5 | P0 | 5 | A | Implementar aba Tripulação com opt-in | Guilherme | Pedro | A fazer |
| ST-025 | S5 | P1 | 3 | B | Cobrir regras puras selecionadas com testes unitários | Wesley | Thiago | A fazer |
| ST-026 | S5 | P1 | 3 | D | Criar conjunto de avaliação de dúvidas e recusas seguras | Pedro | Thiago | A fazer |
| ST-027 | S6 | P0 | 8 | A | Implementar “Fazer Proposta” autenticado e anônimo | Guilherme | Pedro/Wesley | A fazer |
| ST-028 | S6 | P0 | 5 | A/B | Validar servidor, autorização e rate limiting da proposta | Pedro | Wesley | A fazer |
| ST-029 | S6 | P1 | 3 | C | Documentar componentes finais e estados de UI | Guilherme | Wesley | A fazer |
| ST-030 | S6 | P1 | 3 | D/B | Testar comandos por texto/voz, autorização e falhas | Thiago | Pedro/Wesley | A fazer |
| ST-031 | S7 | P0 | 3 | A | Adicionar sitemap e OpenGraph dinâmico | Guilherme | Pedro | A fazer |
| ST-032 | S7 | P1 | 3 | A/C | Revisar performance, responsividade e acessibilidade | Guilherme | Thiago | A fazer |
| ST-033 | S7 | P0 | 5 | B | Consolidar CI, testes unitários, integração e pgTAP | Wesley | Todos | A fazer |
| ST-034 | S7 | P1 | 3 | D | Revisar segurança, custo, logs e base de conhecimento | Pedro | Thiago | A fazer |
| ST-035 | S8 | P0 | 3 | Geral | Congelar escopo e executar regressão final | Wesley | Todos | A fazer |
| ST-036 | S8 | P0 | 5 | Geral | Atualizar README, documentação técnica e handoff | Pedro | Todos | A fazer |
| ST-037 | S8 | P0 | 3 | Geral | Gravar demonstração de 1–3 minutos | Thiago | Todos | A fazer |
| ST-038 | S8 | P0 | 3 | Geral | Preparar e ensaiar apresentação de 5–7 minutos | Thiago | Todos | A fazer |

## Organização das sprints

| Sprint | Período | Objetivo verificável |
|---|---|---|
| S1 | 07–13/09 | Time executa a base local; CI inicial e arquitetura estão mapeadas |
| S2 | 14–20/09 | Homologação reconstruível e primeira melhoria do Orbitinho demonstrável |
| S3 | 21–27/09 | Superfície pública de dados e esqueleto SSR funcionando com segurança |
| S4 | 28/09–04/10 | Primeiro MVP demonstrável para a entrega intermediária de 05/10 |
| S5 | 05–11/10 | Portfólio, Tripulação e testes de regras principais |
| S6 | 12–18/10 | Propostas, proteção contra abuso e integração de componentes |
| S7 | 19–25/10 | SEO, acessibilidade, performance e consolidação de qualidade |
| S8 | 26–29/10 | Congelamento, documentação, vídeo, handoff e ensaio final |

## Dependências críticas

```text
ST-001/003 → ST-007/008/009 → gate de homologação → ST-014/015/016
ST-015 → ST-017/021 → ST-023/024/027
ST-004/011 → todos os PRs → ST-033/035
ST-005/013 → ST-019/020 → ST-023/024/029
ST-006 → ST-012/018/022/026/030/034
```

## Regra de replanejamento

No fim da S2, Pedro e o cliente devem avaliar o gate de homologação. Se ele não estiver seguro, Wesley permanece na frente 0 e a página pública trabalha somente com contrato/mock aprovado. Itens P2 e migração de legado não entram enquanto P0 estiver pendente.

