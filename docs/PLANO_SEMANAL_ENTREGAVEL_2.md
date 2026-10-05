# Plano semanal de recuperação — Sprint 5

**Período:** 05–11/10/2026  
**Situação:** as atividades das Sprints 1 a 4 ainda não foram iniciadas.  
**Estratégia:** reunir as pendências anteriores com as entregas da Sprint 5 e priorizar um MVP integrado, seguro e demonstrável.

## Objetivo da semana

Ao final da semana, a equipe deverá conseguir demonstrar:

1. aplicação executando localmente;
2. ambiente de homologação minimamente reproduzível;
3. CI executando lint, typecheck e testes;
4. página pública de Espaçonave funcionando com dados fictícios;
5. proteção básica dos dados públicos;
6. primeira melhoria demonstrável do Orbitinho;
7. Portfólio e Tripulação em versão inicial;
8. documentação das decisões, pendências e evidências.

## Ordem de execução

```text
Handover e setup
        ↓
Homologação e CI
        ↓
Contrato dos dados públicos
        ↓
Página pública
        ↓
Portfólio e Tripulação
        ↓
Testes, documentação e demonstração
```

Sem acesso ao repositório, ao banco e ao ambiente atual, diversas tarefas ficarão bloqueadas. A liberação desses acessos é prioridade máxima.

## Segunda-feira — desbloqueio e diagnóstico

### Coordenação da equipe

- confirmar com o cliente o acesso ao repositório;
- solicitar o dump somente da estrutura do banco;
- solicitar credenciais exclusivas de homologação;
- confirmar tecnologias, comandos e gerenciador de pacotes;
- confirmar os campos que podem aparecer publicamente;
- confirmar regras de consentimento para Portfólio e Tripulação;
- priorizar o backlog de recuperação;
- registrar decisões e impedimentos.

### Pedro Pereira

- conduzir o handover técnico;
- mapear arquitetura, banco, autenticação e integrações;
- identificar fluxos críticos que não podem ser alterados;
- mapear o funcionamento atual do Orbitinho;
- definir quais mudanças podem ser entregues com segurança na semana.

### Wesley Lima Silva

- executar o projeto localmente;
- identificar variáveis de ambiente e dependências;
- levantar migrations, tabelas, RLS, buckets e comandos existentes;
- verificar os comandos atuais de lint, typecheck e testes.

### Guilherme Kenzo Taba Nakamura

- mapear a estrutura do frontend;
- verificar rotas, componentes e padrões visuais existentes;
- localizar os dados relacionados às Espaçonaves;
- preparar o esqueleto da rota pública.

### Thiago Brasileiro de Sousa

- documentar os passos do setup;
- levantar casos básicos de teste;
- mapear comandos e comportamentos atuais do Orbitinho;
- registrar erros encontrados durante o diagnóstico.

**Resultado esperado:** aplicação executando ou impedimentos claramente documentados.

## Terça-feira — homologação, CI e estrutura inicial

### Wesley Lima Silva

- preparar a configuração local do Supabase;
- organizar as migrations existentes;
- criar um seed fictício mínimo;
- documentar o comando de reconstrução do ambiente;
- criar o workflow inicial de CI;
- separar checks de lint, typecheck e testes.

**Itens relacionados:** `ST-003`, `ST-004`, `ST-007`, `ST-008`, `ST-009` e `ST-011`.

### Pedro Pereira

- revisar migrations e regras de acesso;
- definir o contrato de dados públicos;
- garantir que tabelas privadas não recebam leitura anônima;
- selecionar uma melhoria pequena do Orbitinho para a semana.

### Guilherme Kenzo Taba Nakamura

- inventariar componentes e tokens existentes;
- criar o esqueleto de `/spaceships/[slug]`;
- preparar estados de carregamento, vazio, erro e 404;
- começar os componentes de cabeçalho da Espaçonave.

### Thiago Brasileiro de Sousa

- criar testes básicos para o pipeline;
- documentar a execução local;
- preparar cenários de teste do Orbitinho.

### Coordenação da equipe

- validar com o cliente o recorte do MVP;
- confirmar quais dados fictícios serão usados na demonstração;
- atualizar prioridades e critérios de aceite.

**Resultado esperado:** homologação inicial, CI básico e rota pública iniciada.

## Quarta-feira — superfície pública e Orbitinho

### Guilherme Kenzo Taba Nakamura

- implementar a página pública com slug;
- implementar a renderização no servidor;
- exibir nome, bio, imagem, métricas e tecnologias autorizadas;
- retornar 404 para perfil inexistente ou privado;
- aplicar componentes reutilizáveis.

**Itens relacionados:** `ST-015`, `ST-016`, `ST-019` e `ST-020`.

### Wesley Lima Silva

- criar ou ajustar `is_public` e slug;
- apoiar a criação da view/DTO pública;
- adicionar testes de acesso anônimo e RLS;
- garantir que o pipeline execute em Pull Requests.

**Itens relacionados:** `ST-014` e `ST-017`.

### Pedro Pereira

- revisar a view/DTO pública;
- verificar campos proibidos e exposição de dados pessoais;
- implementar ou orientar a primeira melhoria do Orbitinho;
- definir autorização e confirmação para ações sensíveis.

### Thiago Brasileiro de Sousa

- apoiar a implementação do comando escolhido para o Orbitinho;
- criar casos de sucesso, falha, ambiguidade e falta de autorização;
- testar o comando por texto.

### Coordenação da equipe

- validar funcionalmente a primeira versão da página;
- registrar feedback e controlar o aumento de escopo;
- preparar a estrutura da demonstração.

**Resultado esperado:** página pública inicial e primeira melhoria do Orbitinho demonstráveis.

## Quinta-feira — Portfólio, Tripulação e privacidade

### Guilherme Kenzo Taba Nakamura

- implementar a aba Portfólio;
- implementar a aba Tripulação;
- criar estados de loading, vazio e erro;
- garantir responsividade e navegação por teclado;
- utilizar os componentes reutilizáveis preparados.

**Itens relacionados:** `ST-023` e `ST-024`.

### Wesley Lima Silva

- criar testes de privacidade e campos proibidos;
- cobrir regras puras com testes unitários;
- verificar o comportamento para perfil público e privado;
- corrigir falhas da CI.

**Itens relacionados:** `ST-021` e `ST-025`.

### Pedro Pereira

- revisar o consentimento de projetos e membros;
- verificar se nomes de clientes ou integrantes podem ser exibidos;
- revisar segurança, autorização e arquitetura;
- revisar o comportamento do Orbitinho.

### Thiago Brasileiro de Sousa

- executar testes de regressão;
- testar Portfólio, Tripulação e Orbitinho;
- documentar resultados e evidências;
- registrar bugs priorizados.

### Coordenação da equipe

- executar o aceite funcional;
- classificar problemas entre bloqueadores e melhorias futuras;
- atualizar o backlog;
- confirmar com o cliente as pendências de consentimento.

**Resultado esperado:** Portfólio e Tripulação funcionais com proteção básica de dados.

## Sexta-feira — estabilização e demonstração

Todos devem priorizar correções, integração e documentação. Não devem ser iniciadas funcionalidades grandes nesse dia.

### Wesley Lima Silva

- garantir a CI verde;
- validar a reconstrução do ambiente do zero;
- consolidar os comandos de setup e testes.

### Guilherme Kenzo Taba Nakamura

- corrigir problemas visuais e funcionais;
- validar mobile, teclado, loading, vazio, erro e 404;
- documentar os componentes utilizados.

### Pedro Pereira

- fazer a revisão técnica final;
- verificar segurança, privacidade e integrações;
- validar a entrega do Orbitinho;
- registrar riscos que não puderam ser resolvidos.

### Thiago Brasileiro de Sousa

- executar a regressão final;
- organizar capturas de tela, vídeos e resultados dos testes;
- documentar os casos validados.

### Coordenação da equipe

- realizar o aceite funcional;
- atualizar backlog e status;
- organizar a apresentação;
- conduzir uma demonstração interna;
- registrar o que foi entregue e o que ficou pendente.

**Resultado esperado:** MVP integrado, documentado e demonstrável.

## Distribuição resumida

| Integrante ou função | Prioridade nesta semana |
|---|---|
| Coordenação da equipe | Acessos, alinhamento, backlog, critérios de aceite e demonstração |
| Pedro Pereira | Arquitetura, segurança, privacidade, revisão transversal e Orbitinho |
| Wesley Lima Silva | Homologação, Supabase, migrations, seed, testes e CI |
| Guilherme Kenzo Taba Nakamura | Página pública, Design System, Portfólio e Tripulação |
| Thiago Brasileiro de Sousa | Apoio ao Orbitinho, testes, regressão, documentação e evidências |

## Escopo mínimo obrigatório

Se o tempo for insuficiente, a equipe deve proteger os seguintes itens:

- projeto executando localmente;
- ambiente de homologação com dados fictícios;
- CI com lint, typecheck e pelo menos alguns testes;
- página pública por slug;
- retorno 404 para perfil inexistente ou privado;
- lista branca de campos públicos;
- Portfólio e Tripulação em versão inicial;
- uma melhoria pequena e testável do Orbitinho;
- README com setup e comandos;
- evidências da demonstração.

## Itens que podem ser adiados

- Storybook completo;
- acabamento visual avançado;
- cobertura ampla de testes;
- comandos complexos de voz;
- base extensa de conhecimento do Orbitinho;
- sitemap e otimizações avançadas de SEO;
- Lighthouse e otimização detalhada de performance;
- fluxo completo de “Fazer Proposta”, originalmente previsto para a Sprint 6.

## Diretriz de execução

Esta semana não deve tentar recuperar todas as tarefas atrasadas com o mesmo nível de profundidade. A prioridade é entregar um fluxo vertical funcionando:

```text
ambiente → dados públicos seguros → página pública → testes → demonstração
```

