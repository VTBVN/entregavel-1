# Documento de requisitos

## 1. Visão e atores

O projeto deve permitir que a Startellite evolua uma aplicação em produção sem expor dados pessoais nem afetar integrações críticas.

Principais atores:

- visitante anônimo;
- empresa autenticada;
- membro de uma Espaçonave;
- administrador/cliente Startellite;
- desenvolvedor do projeto;
- usuário do Orbitinho.

## 2. Requisitos funcionais

| ID | Requisito | Prioridade | Responsável |
|---|---|---:|---|
| RF01 | Reconstruir homologação a partir de artefatos versionados e seed, sem dados reais | Must | Wesley |
| RF02 | Executar typecheck, lint e testes automaticamente em Pull Requests | Must | Wesley |
| RF03 | Disponibilizar `/spaceships/[slug]` sem autenticação, com SSR e OpenGraph | Must | Guilherme |
| RF04 | Retornar 404 quando a Espaçonave não existir ou `is_public` não for `true` | Must | Guilherme |
| RF05 | Consumir somente uma view/DTO público com lista branca de campos | Must | Guilherme/Pedro |
| RF06 | Exibir tripulantes respeitando opt-in e regras existentes de identidade | Must | Guilherme |
| RF07 | Exibir portfólio sem identificar clientes sem consentimento registrado | Must | Guilherme |
| RF08 | Permitir proposta de empresa autenticada e visitante, com validação e rate limiting | Must | Guilherme/Pedro |
| RF09 | Documentar componentes reutilizáveis e utilizá-los na página pública | Should | Guilherme |
| RF10 | Preservar os fluxos de produção que estão fora do escopo | Must | Pedro |
| RF11 | Aceitar comandos digitados e ampliar comandos de voz priorizados com o cliente | Must | Pedro/Thiago |
| RF12 | Responder dúvidas sobre a plataforma usando somente conhecimento não confidencial aprovado | Must | Pedro |
| RF13 | Oferecer ações hands-free demonstráveis, com confirmação antes de ações sensíveis | Should | Pedro/Thiago |
| RF14 | Oferecer assistência de programação/gestão de tarefas apenas no recorte validado pelo cliente | Could | Pedro/Thiago |

Os requisitos RF11–RF14 tornam verificável o escopo narrativo do Orbitinho e precisam de validação explícita do cliente antes da implementação.

## 3. Requisitos não funcionais

| ID | Requisito | Evidência esperada |
|---|---|---|
| RNF01 | Não criar custo recorrente sem aprovação | Registro de decisão do cliente |
| RNF02 | Isolar produção e não fornecer credenciais produtivas ao time | `.env.example`, homologação e revisão de acessos |
| RNF03 | Versionar todas as alterações de schema | migrations SQL em PR |
| RNF04 | Não versionar segredos | revisão, `.gitignore` e verificação da CI |
| RNF05 | Manter typecheck, lint e testes aprovados | checks verdes no PR |
| RNF06 | Aplicar boas práticas de performance e assets na rota indexável | Lighthouse ou medição aprovada |
| RNF07 | Trabalhar em PRs pequenos e revisáveis | histórico de PRs ligados ao backlog |
| RNF08 | Preservar acessibilidade por teclado, leitor de tela e uso mobile | checklist e teste manual |
| RNF09 | Não registrar prompts, documentos ou dados pessoais sensíveis no Orbitinho | revisão de telemetria/logs |

## 4. User stories e critérios de aceite

### US01 — Reconstruir o ambiente

Como pessoa desenvolvedora, quero reconstruir o banco e os dados fictícios por comando documentado para testar mudanças sem acessar produção.

Critérios:

- `supabase db reset` ou comando acordado termina sem intervenção manual não documentada;
- schema, funções, triggers, índices e RLS necessários são recriados;
- buckets e policies necessários são documentados/reproduzidos;
- seed contém empresas, satélites, Espaçonaves e missões fictícias em estados relevantes;
- nenhum dado pessoal ou segredo de produção está presente.

### US02 — Validar mudanças automaticamente

Como mantenedor, quero checks automáticos em cada PR para impedir a integração de regressões conhecidas.

Critérios:

- workflow dispara em Pull Requests;
- typecheck, lint e testes produzem status independentes e compreensíveis;
- falha em check obrigatório bloqueia integração conforme regra do repositório;
- documentação ensina a executar e adicionar testes localmente.

### US03 — Compartilhar uma Espaçonave

Como membro autorizado, quero uma URL pública da minha Espaçonave para apresentar equipe, competências e trabalhos.

Critérios:

- rota usa slug e renderiza no servidor;
- metadata e OpenGraph são dinâmicos;
- perfil não publicado retorna 404;
- página possui banner/logo, nome, bio, contagem, métricas e stacks aprovadas;
- layout funciona nos breakpoints acordados e é navegável por teclado.

### US04 — Proteger dados públicos

Como titular de dados, quero que a página pública revele somente informações autorizadas.

Critérios:

- consulta pública usa view/DTO com lista branca;
- tabelas base com dados pessoais não ganham leitura anônima;
- tripulante sem opt-in não tem nome real revelado;
- projeto sem consentimento não identifica empresa contratante;
- testes comprovam a ausência de campos proibidos.

### US05 — Consultar portfólio e tripulação

Como visitante, quero conhecer projetos e especialidades para avaliar a Espaçonave.

Critérios:

- abas Portfólio e Tripulação têm estados de loading, vazio e erro;
- projetos internos e externos seguem regras de consentimento;
- tripulação mostra avatar, especialidade e nível conforme autorização;
- componentes vêm de `/components/ui` quando aplicável.

### US06 — Fazer uma proposta

Como empresa ou visitante interessado, quero enviar uma proposta para iniciar contato com a Espaçonave.

Critérios:

- empresa autenticada tem identidade associada à proposta;
- visitante fornece os campos mínimos acordados;
- entradas são validadas no servidor;
- tentativas abusivas são limitadas sem prejudicar uso legítimo;
- sucesso, validação e erro recebem feedback claro;
- destino e retenção dos dados são aprovados pelo cliente.

### US07 — Reutilizar componentes

Como pessoa desenvolvedora, quero componentes e tokens documentados para manter consistência na nova rota.

Critérios:

- componentes necessários estão em `/components/ui` ou caminho existente aprovado;
- cores, tipografia e espaçamento utilizados estão documentados;
- Storybook ou equivalente executa pelo comando documentado;
- pelo menos a página pública usa os componentes criados;
- não há migração ampla de telas legadas.

### US08 — Usar o Orbitinho com menos cliques

Como usuário, quero pedir por texto ou voz uma ação simples para navegar e trabalhar com mais acessibilidade.

Critérios:

- lista inicial de intents e plataformas é aprovada pelo cliente;
- pelo menos um comando priorizado funciona por texto e, quando suportado, voz;
- “Criar tarefa” solicita confirmação dos dados antes da execução;
- entradas inválidas ou ambíguas não disparam ação irreversível;
- testes cobrem reconhecimento da intenção, autorização, confirmação e falhas.

### US09 — Tirar dúvidas no Orbitinho

Como usuário, quero respostas fundamentadas sobre o uso da plataforma sem exposição de regras confidenciais.

Critérios:

- base de conhecimento possui fontes aprovadas e versionamento/data de atualização;
- resposta distingue informação conhecida de incerteza;
- conteúdo confidencial e dados pessoais não entram na base;
- conjunto de perguntas de avaliação mede correção e recusas seguras;
- uso de tokens e latência são observados sem registrar conteúdo sensível.

## 5. Casos de uso

### UC01 — Abrir perfil público

1. Visitante acessa `/spaceships/[slug]`.
2. Sistema consulta somente a superfície pública aprovada.
3. Sistema verifica `is_public`.
4. Sistema renderiza dados autorizados e metadados.

Alternativas: slug inexistente ou perfil privado retorna 404; falha de dependência apresenta erro seguro sem dados internos.

### UC02 — Enviar proposta

1. Visitante seleciona “Fazer Proposta”.
2. Sistema identifica fluxo autenticado ou anônimo.
3. Usuário informa dados mínimos e confirma.
4. Backend valida conteúdo, autorização e limite de requisições.
5. Sistema registra/envia a proposta e retorna confirmação.

### UC03 — Executar comando no Orbitinho

1. Usuário envia comando por texto ou voz.
2. Orbitinho identifica intenção e parâmetros.
3. Sistema valida autorização e pede confirmação quando aplicável.
4. Ação aprovada é executada e o resultado é informado.
5. Falha ou ambiguidade resulta em orientação segura, sem ação parcial silenciosa.

## 6. Dependências e premissas

- acesso ao repositório privado e handover técnico;
- dump somente de estrutura do banco;
- projeto e credenciais exclusivamente de homologação por canal seguro;
- disponibilidade de representante do cliente para alinhamento semanal;
- confirmação das tecnologias, comandos, regras de consentimento e arquitetura atual do Orbitinho;
- sincronização periódica com a evolução paralela do produto.

## 7. Fora de escopo

Aplicam-se os itens registrados no README, em especial alterações em pagamentos, faturamento, webhooks, cron jobs, OAuth, APIs públicas existentes, AWS e migração completa de telas legadas.

