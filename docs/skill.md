---
name: startellite-visual
description: Criar e revisar interfaces web da Startellite usando os tokens públicos, componentes e regras de acessibilidade da marca.
---

# Startellite — guia visual para agentes

## Fonte

Referências consultadas em 03/10/2026:
- https://startellite.com/
- https://startellite.com/_next/static/css/4d258313c36aa4cd.css

Os tokens abaixo foram extraídos do CSS público quando marcados como “extraído”. Valores marcados como “proposto” são extensões para o MVP e devem ser mantidos centralizados para futura substituição.

## Design Tokens

### Cores

| Papel | Token | HEX | RGB | Uso | Origem |
|---|---|---|---|---|---|
| Primary | turquesa | #1AC1D6 | 26, 193, 214 | CTAs e gradiente principal | Extraído |
| Secondary | orbita | #1A9BDB | 26, 155, 219 | Complemento do gradiente | Extraído |
| Accent | ciano | #6EE2D6 | 110, 226, 214 | Destaques em fundo escuro | Extraído |
| Neutral strong | profundo | #0F172A | 15, 23, 42 | Títulos e seções escuras | Extraído |
| Background | estratosfera | #F1F5F9 | 241, 245, 249 | Fundo principal e seções | Extraído |
| Surface | estelar | #FFFFFF | 255, 255, 255 | Cards, header e superfícies | Extraído |
| Text muted | muted | #475569 | 71, 85, 105 | Texto secundário | Proposto |
| Border | border | #E2E8F0 | 226, 232, 240 | Bordas e separadores | Proposto |

Gradiente principal: `linear-gradient(90deg, #1AC1D6, #1A9BDB)`.

Não substituir esta paleta por roxo ou verde-lima sem validação do cliente.

### Tipografia

Família declarada no CSS:

`"Inter", system-ui, -apple-system, sans-serif`

Pesos:
- 400: corpo;
- 600: navegação e botões;
- 700: títulos de cards;
- 900: títulos principais.

Escala recomendada:

| Elemento | Mobile | Tablet | Desktop | Line-height |
|---|---:|---:|---:|---:|
| h1 | 44px | 60px | 72px | 1.02 |
| h2 | 36px | 48px | 60px | 1.05 |
| h3 | 24px | 24px | 24px | 1.25 |
| body | 16px | 16px | 16px | 1.625 |
| lead | 18px | 18px | 18px | 1.625 |
| small | 14px | 14px | 14px | 1.5 |

`h1` usa peso 900 e tracking aproximado de `-0.03em`.

### Espaçamento

A unidade declarada pelo CSS é `0.25rem`, equivalente a 4px com raiz de 16px.

Escala: 4, 8, 12, 16, 24, 32, 48, 64, 80, 96, 112 e 128px.

Padrões observados:
- cards: padding de 24px;
- seções: padding vertical de 80px mobile e 96px desktop;
- controles: altura mínima de 44px;
- container: máximo aproximado de 1152px;
- conteúdo: 24px de margem lateral;
- grids: gap de 24px.

### Radius e elevação

Extraído:
- `rounded-xl`: 12px;
- `rounded-2xl`: 16px;
- `rounded-3xl`: 24px;
- `rounded-full`: controles e badges.

Extensões do MVP:
- Level 1: `0 4px 16px rgba(15,23,42,.06)`;
- Level 2: `0 20px 48px rgba(15,23,42,.10)`.

## Component Guidelines

### Temas claro e escuro — extensão proposta do MVP

Implementação em `mvp-startellite/themes.css` e `theme.js`.
As cores da marca permanecem constantes; superfícies e texto usam tokens semânticos.
O tema escuro é uma extensão proposta, não uma extração de telas autenticadas.

| Token | Claro | Escuro |
|---|---|---|
| bg | #F1F5F9 | #0F172A |
| paper | #FFFFFF | #1E293B |
| ink | #0F172A | #F1F5F9 |
| muted | #475569 | #CBD5E1 |
| soft | #E2E8F0 | #475569 |
| accent-text / focus | #0F172A | #6EE2D6 |

- Aplicar `data-theme="light|dark"` no elemento raiz antes do CSS.
- Usar preferência do sistema até uma escolha explícita; acompanhar mudanças.
- Salvar escolha em `localStorage`, chave `startellite-theme`.
- Sem storage, manter alternância em memória; sem JavaScript, usar CSS e tema do sistema.
- Botão nativo “Modo escuro”, com `aria-pressed` indicando ativação; mínimo 44px.
- CTAs e cards turquesa usam texto profundo nos dois temas.
- Preservar foco visível, teclado e `prefers-reduced-motion`.

### Botões

Primary:
- altura mínima de 44px;
- padding lateral de 24px;
- border-radius de cápsula;
- gradiente turquesa → órbita;
- texto profundo para garantir contraste;
- hover com sombra;
- active com deslocamento de 1px.

Secondary:
- fundo branco;
- texto profundo;
- borda muted;
- hover com fundo estratosfera.

Ghost:
- fundo transparente;
- texto profundo;
- hover com fundo estratosfera.

Usar links para navegação e buttons para ações. Toda ação deve possuir estado de foco visível.

### Cards e containers

- fundo estelar;
- borda de 1px em border;
- radius de 16px;
- padding de 24px;
- título profundo;
- descrição muted;
- sombra de Level 1;
- painéis principais podem usar radius de 24px e Level 2.

### Header, navbar e footer

Header:
- fundo estelar;
- borda inferior sutil;
- wordmark oficial quando disponível;
- navegação com alvos de pelo menos 44px;
- CTA primary.

Footer:
- pode usar fundo profundo;
- texto estelar;
- destaques em ciano;
- links descritivos e acessíveis.

## Coding Rules for AI

- Centralizar tokens em `:root` ou no tema do Tailwind.
- Não duplicar cores em componentes.
- Preservar os nomes semânticos: turquesa, orbita, ciano, profundo e estratosfera.
- Usar HTML semântico, uma única tag `h1` e hierarquia consistente.
- Construir mobile first.
- Breakpoints: 640px e 1024px.
- Testar em 375px, 768px e 1440px.
- Não inventar cores oficiais; marcar extensões como propostas.
- Não usar grid overlay, excesso de neon ou efeitos espaciais decorativos sem referência visual.
- Respeitar `prefers-reduced-motion`.

### Contraste

- Texto normal: mínimo WCAG AA de 4.5:1.
- Texto grande: mínimo de 3:1.
- Controles e indicadores: mínimo de 3:1.
- Não depender apenas de cor.
- Exibir foco com outline de 3px e offset de 3px.
- Alvos interativos com pelo menos 44px.
