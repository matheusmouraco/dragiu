# CLAUDE.md — Projeto: Site Dra. Giuliana Graicer

> Este arquivo é o contexto completo do projeto para o Claude Code.
> Leia tudo antes de fazer qualquer alteração.

---

## Visão Geral

**Cliente:** Dra. Giuliana Graicer — Otorrinolaringologista  
**CRM:** SP 210131  
**Tipo:** Site institucional one-page — HTML puro, zero frameworks, zero dependências  
**Agência:** BZ Comunicação  
**Especialidade:** Otorrinolaringologia adultos e crianças, Jardim Paulista, São Paulo

---

## Estrutura de Arquivos

```
site-dra-giuliana/
├── index.html          ← site completo (HTML + CSS + JS inline, tudo em um arquivo)
├── Ativo_1_2x.png      ← logo oficial
├── Giuliana-1.jpg      ← seção "Como funciona" (consultório)
├── Giuliana-43.jpg     ← hero principal
├── Giuliana-49.jpg     ← disponível (não usada atualmente)
├── Giuliana-72.jpg     ← disponível (não usada atualmente)
├── Giuliana-83.jpg     ← seção "Sobre" (foto grande)
├── vercel.json         ← config deploy
├── .gitignore
└── CLAUDE.md           ← este arquivo
```

**Regra importante:** tudo está em `index.html`. CSS e JS são inline. Não criar arquivos separados a menos que explicitamente pedido.

---

## Stack Técnica

- HTML5 semântico
- CSS puro com variáveis CSS (`--rose`, `--ink`, `--cream` etc.)
- JavaScript vanilla (sem jQuery, sem React, sem nada)
- Google Fonts: `Geist` + `Geist Mono`
- Deploy: GitHub + Vercel (static site, sem build step)

---

## Design System

### Paleta de Cores (CSS Variables)
```css
--rose: #B5827A        /* cor principal da médica */
--rose-2: #C49991      /* rosa mais claro */
--rose-pale: #EDD8D5   /* rosa pálido (bordas) */
--rose-faint: #F8F1F0  /* rosa quase branco (backgrounds) */
--sand: #E8E0D8        /* areia */
--sand-2: #F2EDE8      /* areia clara */
--cream: #FAFAF9       /* fundo principal */
--ink: #1A1917         /* preto quente (textos principais) */
--ink-2: #2E2C2A       /* preto ligeiramente mais claro */
--muted: #6B6560       /* cinza morno (textos secundários) */
--muted-2: #9A9590     /* cinza ainda mais claro */
--border: rgba(26,25,23,0.07)
--border-2: rgba(26,25,23,0.12)
--glass: rgba(255,255,255,0.78)
--max-w: 1100px        /* largura máxima do conteúdo */
--ease: cubic-bezier(0.16,1,0.3,1)
```

### Tipografia
- **Títulos:** `Geist`, weight 700, `letter-spacing: -0.035em` a `-0.045em`
- **Monospace (datas, números):** `Geist Mono`, weight 400/500
- **Body:** `Geist`, weight 400, `line-height: 1.6`
- **font-size base:** 105% (levemente aumentado para dar zoom)
- **Nunca usar serif** — identidade é tech/clean

### Estética Geral
- Inspirada em Vercel/Linear/21st.dev
- Grid de fundo sutil (linhas finas via `body::before`)
- Glassmorphism leve na nav e float cards
- Hover com `translateY(-2px)` + `box-shadow`
- Ambient glow no hero (radial-gradient absoluto)
- Sem emojis, sem decorações excessivas

---

## Seções do Site (ordem)

1. **Nav** — logo 60px, links de navegação, CTA "Agendar consulta", hamburger mobile
2. **Hero** (`#home`) — grid 2 colunas, texto à esquerda, foto `Giuliana-43.jpg` à direita
3. **Tratamentos** (`#tratamentos`) — chips de sintomas + grid 2x2 de condições + sit-cards + banner otoscópio
4. **Como Funciona** (`#como-funciona`) — 5 passos numerados + imagem `Giuliana-1.jpg` (full height desktop, **oculta no mobile**)
5. **Sobre** (`#sobre`) — foto única `Giuliana-83.jpg` (680px desktop) + timeline 2x2 cards
6. **Diferenciais** — fundo escuro (`var(--ink-2)`), 3 cards translúcidos + quote bar
7. **Especialidades** (`#especialidades`) — tabs laterais, listas 2 colunas, **sem imagens**
8. **Depoimentos** (`#depoimentos`) — 3 colunas scroll infinito CSS, **sem fotos de perfil**
9. **Contato** (`#contato`) — infos à esquerda + formulário à direita, `align-items: center`
10. **Footer** — logo invertido, links, CRM
11. **WhatsApp Float** — fixo bottom-right

---

## Breakpoints Responsivos

```
Desktop:  > 1024px  → layout full, duas colunas, max-w:1100px
Tablet:   ≤ 1024px  → grid 1 coluna, nav sem links (só CTA + hamburger)
Mobile:   ≤  640px  → tudo centralizado, imagem "Como Funciona" oculta
```

### Regras Mobile Críticas
- Tudo centralizado: `text-align: center` nos títulos, leads, tags, badges
- `.hero-left` com `align-items: center`
- Imagem do "Como Funciona" oculta: `.funciona-img { display: none }`
- Hero image: `height: 88vw`, `object-position: center 15%`, `scale(1.08)`
- Logo nav: `height: 52px`
- Nav: `height: 68px`
- Formulário: `.fg-row` em 1 coluna

---

## Contato / Dados da Médica

- **WhatsApp:** (11) 98603-0172 — `https://wa.me/5511986030172`
- **E-mail:** dragiulianagraicer@gmail.com
- **Endereço:** R. da Consolação, 3367 – Cj. 13 · Jardim Paulista, SP · CEP 01416-904
- **CRM:** SP 210131

**Mensagem padrão do WhatsApp:**
```
https://wa.me/5511986030172?text=Ol%C3%A1%2C%20gostaria%20de%20agendar%20uma%20consulta
```

---

## Formação da Médica (para manter consistente)

| Período | Descrição |
|---------|-----------|
| Graduação | Medicina — PUC-SP, Pontifícia Universidade Católica · Sorocaba |
| Residência | Otorrinolaringologia — HC-USP, Hospital das Clínicas FMUSP |
| 2020 | Serviço Militar — 2ª Tenente Médica do Exército Brasileiro |
| 2024 | Fellowship Internacional — Massachusetts Eye and Ear · Harvard Medical School |

---

## Diferenciais Clínicos (mencionar sempre que relevante)

- Nasofibrolaringoscopia + videolaringoscopia **na própria consulta**
- **Otoscópio digital com tela** — paciente/pais acompanham exame em tempo real ← diferencial mais forte
- Diagnóstico no mesmo dia, sem encaminhamentos
- Polissonografia orientada na consulta (apneia)
- Audiometria na clínica + fonoaudióloga integrada (presbiacusia)
- Manobra de Epley na consulta (VPPB)
- Imunoterapia/dessensibilização (rinite)
- Cirurgia como **última escolha** fundamentada

---

## Especialidades com Conteúdo

Cada tab tem ID `p-{id}` e é ativada por `setTab('{id}', this)`:

| ID | Tab |
|----|-----|
| `rinite` | Rinite & Respiração |
| `apneia` | Apneia do Sono |
| `pediatrica` | Otorrino Pediátrica |
| `audicao` | Perda Auditiva |
| `vertigem` | Vertigem & VPPB |

---

## JavaScript (inline no final do HTML)

```js
// Logo fallback se imagem não carregar
document.getElementById('logoImg').onerror = function() { ... }

// Troca de tabs nas especialidades
function setTab(id, btn) { ... }

// Hamburger menu mobile
ham.addEventListener('click', function() { ... })

// Intersection Observer para animações de entrada (.rv → .vis)
const obs = new IntersectionObserver(...)

// Hero: anima imediatamente sem scroll
document.querySelectorAll('.hero-left .rv').forEach(...)

// Nav sombra ao scrollar
window.addEventListener('scroll', ...)
```

---

## Convenções de Classe CSS

| Classe | Uso |
|--------|-----|
| `.rv` | Elemento com animação reveal (opacity 0 → 1) |
| `.vis` | Estado visível (aplicado pelo IntersectionObserver) |
| `.d1` `.d2` `.d3` `.d4` | Delays de transição (0.07s, 0.14s, 0.21s, 0.28s) |
| `.btn-dark` | Botão fundo escuro |
| `.btn-outline` | Botão borda |
| `.btn-light` | Botão fundo branco (usado no fundo escuro) |
| `.section-white` | Seção fundo branco |
| `.section-sand` | Seção fundo areia |
| `.section-cream` | Seção fundo cream (padrão) |
| `.section-dark` | Seção fundo escuro |
| `.tag` | Label pequeno acima dos títulos (ex: "Sobre a médica") |
| `.s-title` | Título de seção |
| `.s-lead` | Parágrafo introdutório de seção |

---

## Deploy

1. Subir para GitHub (repositório pode ser privado)
2. Vercel → Add New Project → conectar repo → deploy automático
3. Domínio: Settings → Domains no Vercel, apontar DNS no registrador

**`vercel.json`:**
```json
{
  "cleanUrls": true,
  "trailingSlash": false
}
```

---

## Regras para Edição

- **Não separar CSS/JS em arquivos externos** — manter tudo em `index.html`
- **Não adicionar dependências** (sem npm, sem CDN de libs pesadas)
- **Manter o design system** — usar sempre as variáveis CSS da paleta
- **Não usar fontes serifadas**
- **Não usar `—` (em dash)** em nenhum texto do site — usar vírgula, ponto, ponto-e-vírgula ou reescrever a frase
- **WhatsApp:** sempre abrir em `target="_blank"`
- **Imagens:** sempre com `alt` descritivo
- **Mobile:** toda mudança de layout deve ter regra no `@media(max-width:640px)`

---

*Gerado por BZ Comunicação — Projeto Dra. Giuliana Graicer — 2026*

---

## Atualização: Site Multi-Page (v2)

O site foi refatorado de one-page para multi-page. Estrutura atual:

```
index.html          ← Home resumida
sobre.html          ← Sobre + Como Funciona
tratamentos.html    ← Condições + chips + sit-cards
especialidades.html ← Tabs com 5 especialidades
contato.html        ← Formulário + informações
style.css           ← CSS compartilhado entre todas as páginas
```

### Navegação
- Nav ativa: cada página tem `class="active"` no link correspondente
- Todas as páginas iniciam do topo (comportamento padrão HTML)
- JS compartilhado: hamburger, IntersectionObserver, scroll shadow da nav

### Função setTab (só em especialidades.html)
```js
function setTab(id, btn) { ... }
```
