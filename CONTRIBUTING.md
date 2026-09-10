# Guia de contribuição

## Antes de começar

1. Escolha um item priorizado e confirme responsável, critérios de aceite e dependências.
2. Se o requisito estiver incompleto, registre a dúvida antes de implementar.
3. Atualize sua branch a partir da base definida pelo cliente.
4. Nunca copie dados ou credenciais de produção para o ambiente local.

## Branches

- `feat/ST-012-public-spaceship-view`
- `fix/ST-021-public-profile-privacy`
- `test/ST-009-rls-pgtap`
- `docs/ST-003-local-setup`

Uma branch deve tratar de uma entrega pequena e revisável.

## Commits

Exemplos:

```text
feat(spaceships): add public profile view
test(rls): cover anonymous spaceship access
ci: run typecheck and tests on pull requests
docs(setup): document Supabase reset
```

## Pull Requests

Cada PR deve informar:

- item do backlog e objetivo;
- o que mudou e o que ficou fora;
- como validar localmente;
- evidências visuais, quando aplicável;
- testes criados ou executados;
- impacto em banco, privacidade, segurança e deploy;
- rollback ou forma de desativação quando houver risco operacional.

### Aprovações mínimas

- código comum: uma aprovação;
- rota pública, exposição de dados, migrations, RLS ou Orbitinho: aprovação de Pedro;
- banco/homologação/CI: revisão adicional de Wesley;
- interface/Design System: revisão adicional de Guilherme;
- o autor não aprova nem integra o próprio PR sozinho.

## Segurança

- nenhum secret deve aparecer em commit, issue, print ou log;
- somente variáveis sem valor real entram em `.env.example`;
- mudanças de schema são migrations versionadas;
- não executar DDL ou seeds no banco de produção;
- não ampliar permissões anônimas de tabelas com dados pessoais;
- qualquer dado público deve sair de view/DTO com lista branca.

