# Alinhamento com o cliente — perguntas e decisões da reunião

## Entendimento consolidado

- O produto já está em produção; a equipe fará evolução incremental, não reescrita.
- Produção, branch principal e deploy permanecem sob governança do cliente.
- O time trabalhará por branches e Pull Requests pequenos.
- O cliente fornecerá repositório, handover, dump somente de estrutura e credenciais de homologação por canal seguro.
- A página pública deve usar ativação explícita e lista branca de dados.
- Pagamentos, webhooks, cron jobs, OAuth, APIs públicas existentes, AWS e migração completa de legado não fazem parte do case.
- Haverá alinhamento semanal, ajuste flexível de pessoas e demonstrações incrementais.
- Victor Barbosa Viana será o ponto de governança do projeto como Scrum Master e Product Owner, responsável por backlog, priorização, facilitação e aceite funcional, sem atuação em código.

## Perguntas da reunião de alinhamento — 10/09/2026

### Frente A — Página Pública de Espaçonaves (peso 20%)

1. Para o controle de visibilidade, o escopo prevê granularidade campo a campo, como no LinkedIn, ou um interruptor geral usando `is_public`?
   **Registro da reunião:** O cliente ainda não definiu o modelo final. Foi discutido que um mesmo astronauta pode atuar em diferentes Espaçonaves e que, em princípio, é preferível permitir que o astronauta defina quais informações poderão ser visualizadas. A granularidade dessa configuração ainda depende de validação de escopo e viabilidade.
2. A lista de campos da view `public_spaceship_profiles` já foi definida pelo cliente ou deve ser proposta pela equipe para validação?
   **Registro da reunião:** A lista de campos deverá ser revalidada após a equipe obter acesso à plataforma e realizar uma reunião específica com o cliente.

### Frente C — Design System (peso 15%)

3. Existe brand book, guia de estilo ou definição de identidade visual/verbal que deve orientar os componentes? Caso não exista, qual é o posicionamento e o tom de voz da Startellite?
   **Registro da reunião:** Atualmente não há um brand book disponível. O cliente irá fornecê-lo assim que possível. Até que o material seja entregue, a equipe deverá preservar o template e a identidade visual já existentes na página.
4. Qual é o mercado primário da Startellite? A experiência deve priorizar o público brasileiro apesar da alternância entre PT e EN?
   **Registro da reunião:** A visão do cliente é atender ao mercado global. Embora o escopo ainda não esteja claramente definido, a orientação preliminar indica iniciar pelo mercado brasileiro, mantendo desde o início uma infraestrutura preparada para expansão internacional.

### Frente D — Assistente de IA Orbitinho (peso 30%)

5. Qual é o estado atual do Orbitinho, incluindo stack, comandos cobertos e integrações em funcionamento?
   **Registro da reunião:** O Orbitinho utiliza o modelo Gemini 2.5 Flash. Atualmente, permite acessar páginas por comandos de voz e conversar com o cliente por voz. As demais funcionalidades, integrações e limitações deverão ser validadas diretamente na plataforma.
6. O que significa, na prática, “programar para o usuário enquanto ele está longe do notebook”? Qual nível de autonomia e quais IDEs são prioritários (VS Code, Claude, Cursor ou Antigravity)?
   **Registro da reunião:** O cliente espera que o Orbitinho ofereça essa capacidade literalmente, em linha com o funcionamento já observado em outras soluções de inteligência artificial. O nível exato de autonomia e as ferramentas prioritárias ainda deverão ser detalhados e validados na plataforma.

> A Frente D concentra 30% da avaliação e possui menor definição no case. É necessário aprovar um recorte realista para as oito semanas, com validação de Victor como Product Owner e do cliente.



