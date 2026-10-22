# 🎨 Figma para Desenvolvedores — Guia Didático

> **Material didático autônomo** (arquivo HTML único) que apresenta o Figma a alunos de cursos técnicos de Desenvolvimento de Sistemas, com trilha de cadastro, demonstrações em vídeo, desafio prático e publicação de protótipo.

[![HTML5](https://img.shields.io/badge/HTML5-Monolítico-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://developer.mozilla.org/pt-BR/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-Responsivo-1572B6?style=for-the-badge&logo=css3&logoColor=white)](https://developer.mozilla.org/pt-BR/docs/Web/CSS)
[![Figma](https://img.shields.io/badge/Figma-Design%20%26%20Prototipagem-a259ff?style=for-the-badge&logo=figma&logoColor=white)](https://www.figma.com)
[![Licença](https://img.shields.io/badge/Licen%C3%A7a-MIT-10b981?style=for-the-badge)](LICENSE)

---

## 📌 Sumário

- [Sobre o Material](#-sobre-o-material)
- [Público-alvo e Pré-requisitos](#-público-alvo-e-pré-requisitos)
- [Estrutura da Aplicação](#-estrutura-da-aplicação)
- [Seções da Página](#-seções-da-página)
- [Recursos Externos Referenciados](#-recursos-externos-referenciados)
- [Arquitetura Técnica](#-arquitetura-técnica)
- [Design System](#-design-system)
- [Guia de Uso em Sala](#-guia-de-uso-em-sala)
- [Limitações Conhecidas](#-limitações-conhecidas)
- [Roadmap](#-roadmap)
- [Licença & Créditos](#-licença--créditos)

---

## 🎯 Sobre o Material

Este documento HTML é um **guia introdutório ao Figma** distribuído como arquivo único (`index.html`) para alunos iniciantes em design de interfaces. A página é **100% estática** — sem JavaScript, sem backend, sem build — e roda em qualquer navegador moderno após o carregamento inicial (os vídeos e links externos exigem internet).

**Objetivo pedagógico:** apresentar o Figma como ferramenta de **prototipagem de interfaces** que o desenvolvedor consulta antes de codificar, e não como software de "desenho". A seção de destaque conecta a ferramenta ao fluxo de trabalho de quem programa:

> "Figma permite que você visualize especificações de design, exporte assets (ícones, imagens, cores) e entenda a estrutura do layout antes de codificar. Isso reduz retrabalho e alinha expectativas entre design e desenvolvimento."

**Ferramenta oficial:** [figma.com](https://www.figma.com) — a documentação da própria Figma define o produto como uma ferramenta na qual "teammates and AI agents work in the same space with shared context", voltada a transformar ideias em apps, sites e produtos ([figma.com](https://www.figma.com/)).

---

## 👥 Público-alvo e Pré-requisitos

| Item | Descrição |
| --- | --- |
| **Público** | Alunos do 1º módulo de cursos técnicos de Desenvolvimento de Sistemas. |
| **Pré-requisito técnico** | Navegador moderno (Chrome, Firefox, Edge, Safari) e acesso à internet (para os vídeos e o cadastro no Figma). |
| **Pré-requisito conceitual** | Nenhum. O material assume que o aluno nunca utilizou a ferramenta. |
| **Conta necessária** | Conta gratuita no Figma — criada durante a seção de cadastro. |

---

## 📁 Estrutura da Aplicação

O projeto é **um único arquivo HTML** com CSS embutido, sem dependências locais:

```text
figma-para-devs/
│
├── index.html               # Material completo (HTML + CSS embutidos)
├── Desafio_Figma.pdf        # Enunciado do desafio prático (link relativo)
└── sugestao.png             # Gabarito visual/sugestão do desafio (link relativo)
```

> ⚠️ **Atenção aos caminhos relativos:** o HTML referencia `Desafio_Figma.pdf` e `sugestao.png` pelos nomes diretos, sem pasta. Os três arquivos devem estar **na mesma pasta** no momento da distribuição. A ausência desses arquivos quebra os dois links (`📥 Abrir Desafio` e `💡 Ver Sugestão`) sem afetar o restante da página.

### Diagrama de blocos internos do `index.html`

```text
<!DOCTYPE html>
├── <head>
│   ├── <meta> viewport (responsividade)
│   ├── <title> 🎨 Figma - Para Desenvolvedores
│   └── <style> Design System completo (sem CSS externo)
│
└── <body>
    └── .container
        ├── .header          → título, badges e subtítulo
        ├── .secao "O que é Figma?"
        ├── .secao "Link Oficial"
        ├── .secao "Criar Conta"        → 4 passos numerados
        ├── .secao "Demonstrações"      → 3 cards de vídeo
        ├── .secao "Desafio"            → link para Desafio_Figma.pdf
        ├── .secao "Publicar"           → 4 passos para compartilhar
        ├── .secao "Ajuda"              → link para sugestao.png
        └── .footer
```

---

## 📖 Seções da Página

### 1. Header

Banner superior com:
- Ícone 🎨 e título "Figma / Design de Interfaces para Desenvolvedores".
- Quatro badges temáticos: 🎯 Design · 💻 Prototipagem · 🛠️ Wireframes · 🚀 Colaboração.

### 2. O que é Figma?

Parágrafo definindo o Figma como ferramenta de design de interfaces baseada na nuvem para *wireframes, protótipos e layouts* colaborativos. Inclui:
- **Imagem ilustrativa** carregada de `https://help.figma.com/hc/article_attachments/26978261914391` — segundo a documentação oficial, é a figura de referência de *frames* no Figma Design, ilustrando a hierarquia **Top-level Frame → Nested Frame → Children** e a divisão **Descriptions / Layers / Pages / File Assets** da interface ([help.figma.com](https://help.figma.com/hc/article_attachments/26978261914391)).
- **Caixa de destaque** (`.destaque`) com o argumento pedagógico sobre o papel do Figma no fluxo de quem programa.

### 3. Link Oficial

Card clicável para [figma.com](https://www.figma.com/) com ícone 🌐, descrição curta e seta indicativa.

### 4. Como Criar uma Conta Gratuita

Grid com 4 passos numerados (`.passos`) e caixa de destaque com a informação sobre o plano gratuito:

> 💡 **Dica:** A versão gratuita permite criar até **3 projetos** e colaborar com até **2 editores** simultâneos.

Conteúdo consistente com o relato do instrutor Edu Sites: no plano gratuito, "you can only create a project with up to three screens"; projetos com mais de três telas e múltiplos arquivos exigem plano pago ([youtu.be/J6pP0TFljpo](https://youtu.be/J6pP0TFljpo)).

### 5. Demonstrações

Grid `.videos-grid` com **3 cards de vídeo** do YouTube:

| # | Título | Canal / Autor | URL |
| --- | --- | --- | --- |
| 1 | Wireframes e Protótipos com Figma | Thiago Veigah | [youtu.be/69PngSL6XN4](https://youtu.be/69PngSL6XN4) |
| 2 | Aprenda Figma Grátis — Interfaces profissionais do zero | Edu Sites | [youtu.be/J6pP0TFljpo](https://youtu.be/J6pP0TFljpo) |
| 3 | Navegar Entre Páginas em Protótipo no Figma | Panamericana Escola de Arte e Design | [youtu.be/uSUBC_kU5Cg](https://youtu.be/uSUBC_kU5Cg) |

O card do vídeo 3 ocupa as duas colunas via `grid-column: 1 / -1`. O vídeo do Edu Sites, publicado em **11/02/2025** com 13min44s de duração, cobre desde a criação de projeto no Figma até a padronização de frames para desktop e mobile — usando, segundo o próprio relato, **MacBook Pro 16** para web e **iPhone 16 Pro Max** para mobile ([youtu.be/J6pP0TFljpo](https://youtu.be/J6pP0TFljpo)).

### 6. Desafio

Bloco tracejado laranja (`.desafio-box`) com:
- Nome do arquivo `Desafio_Figma.pdf`.
- Botão `📥 Abrir Desafio` (`target="_blank"`, `href="Desafio_Figma.pdf"`).

### 7. Publicar seu Protótipo

Caixa verde (`.publicacao-box`) com lista ordenada de 4 passos operacionais dentro do Figma:
1. Clicar em **"Share"**.
2. Alterar para **"Anyone with the link"**.
3. Selecionar **"Can view"**.
4. Copiar e compartilhar o link.

O fluxo coincide com o mecanismo padrão de compartilhamento do Figma, no qual o proprietário do arquivo define permissões de *view* sem exigir que o visitante tenha conta.

### 8. Ajuda

Bloco com degradê roxo/rosa (`.ajuda-box`) que convida o aluno a **tentar antes** de abrir a sugestão:
- Botão `💡 Ver Sugestão` (`href="sugestao.png"`, `target="_blank"`).
- Aviso: "⚡ Dica: Tente primeiro! A sugestão é apenas um guia."

### 9. Footer

Menção à natureza educacional, com a observação de que "todos os links abrem em nova aba".

---

## 🔗 Recursos Externos Referenciados

| Recurso | URL | Uso |
| --- | --- | --- |
| Site oficial do Figma | https://www.figma.com/ | Link para cadastro. |
| Imagem de referência (Frames) | https://help.figma.com/hc/article_attachments/26978261914391 | Ilustração da seção "O que é Figma?". |
| Vídeo 1 | https://youtu.be/69PngSL6XN4 | Demonstração (card). |
| Vídeo 2 | https://youtu.be/J6pP0TFljpo | Demonstração (card). |
| Vídeo 3 | https://youtu.be/uSUBC_kU5Cg | Demonstração (card duplo). |
| `Desafio_Figma.pdf` | *(relativo)* | Enunciado do desafio. |
| `sugestao.png` | *(relativo)* | Gabarito / sugestão do desafio. |

> 🔍 **Sobre a imagem do Figma:** a ilustração vem da documentação de ajuda oficial e é hospedada pelo próprio fabricante. Se a URL for descontinuada em futuras revisões do help center, o elemento `<img>` quebrará silenciosamente (sem legenda alternativa). Recomenda-se baixar a imagem e servi-la localmente — inclusive para permitir o uso do material offline.

---

## 🏗 Arquitetura Técnica

### Padrão de código

- **HTML5 semântico + CSS3 puro** embutido em `<style>`, sem frameworks.
- **Zero JavaScript** — a página é totalmente estática, sem interação (as únicas ações são links e novos links para vídeos).
- **Layout flexível** via CSS Grid e Flexbox com `minmax()` / `auto-fill`, sem media queries dedicadas para grids que colapsam naturalmente.

### Técnicas de responsividade

| Abordagem | Onde é usada |
| --- | --- |
| `grid-template-columns: repeat(auto-fill, minmax(180px, 1fr))` | Grid de passos de cadastro (`.passos`) — colapsa de 4 para 2 e depois 1. |
| `flex: 1; min-width: 180px` | Cards de links oficiais. |
| `@media (max-width: 768px)` | Ajustes de `padding`, `h1` e grid de vídeos (2→1 coluna). |
| `@media (max-width: 480px)` | Ajustes finais de `padding`, `h1`, `icon`, `.ajuda-box`, `.desafio-box`. |
| `grid-column: 1 / -1` | Card do 3º vídeo ocupa a largura inteira. |

### Componentes reutilizáveis via classes

| Classe | Papel | Pseudo-estado |
| --- | --- | --- |
| `.secao` | Sistema de seções uniformes | — |
| `.destaque` | Caixa de citação com borda roxa | — |
| `.badge` / `.badge.figma` | Etiquetas do header | — |
| `.link-card` | Card de link oficial | `:hover` com `translateY(-2px)` |
| `.passo` | Card de passo numerado | — |
| `.video-card` | Card de vídeo | `:hover` com `translateY(-3px)` |
| `.btn-desafio` / `.btn-ajuda` | Botões pill | `:hover` com `scale(1.02)` |
| `.img-ilustrativa` | Moldura para ilustração | — |

### Acessibilidade — o que está OK e o que falta

**OK:**
- Contraste alto (texto escuro sobre fundo claro em quase todas as seções).
- Uso de `alt` no `<img>` da seção "O que é Figma?".

**Falta (para auditoria futura):**
- Badges e emojis dentro dos cards **não possuem `aria-label`** — leitores de tela vão ler "🎨 Design" como "emoji paleta Design".
- Cards de vídeo usam `<a>` com `target="_blank"` sem `rel="noopener"` (não afeta a segurança dos alunos, mas é boa prática).
- A navegação por tabulação passa por todos os cards em ordem de leitura — aceitável, mas poderia ter `aria-labelledby` ligando cada `.secao` ao seu `h2`.
- Sem `<main>` semântico — o `.container` faz o papel, mas um wrapper `<main>` seria mais correto para leitores de tela.

---

## 🎨 Design System

### Paleta

```css
--figma-purple:   #a259ff   /* cor de destaque principal */
--figma-dark:     #7b2fbe   /* hover e títulos com destaque */
--ink:            #1a1a2e   /* títulos */
--text-body:      #2c3e50   /* corpo de texto */
--surface:        #f8f9fa   /* cards neutros */
--surface-purple: #f8f0ff   /* cards de destaque */
--border:         #e9ecef   /* divisores */
--danger:         #dc3545   /* badge YouTube */
--warning:        #fd7e14   /* desafio (tracejado laranja) */
--success:        #28a745   /* publicar (borda verde) */
```

### Tipografia

- Fonte: `'Segoe UI', Tahoma, Geneva, Verdana, sans-serif` — pilha de fontes de sistema, sem carregamento externo.
- Escala baseada em `rem` a partir do `body` (16px), com ajustes em todos os headings via `rem`.
- `line-height: 1.7` no corpo de texto para leitura confortável.

### Estrutura visual

- **Cantos:** `24px` no `.container`, `12px` nos cards, `8px` nas caixas de destaque, `30px` nos botões pill.
- **Sombras:** `0 20px 60px rgba(0,0,0,0.3)` no container; `0 4px 15px rgba(162, 89, 255, 0.15)` no hover dos cards.
- **Bordas laterais coloridas** em caixas de destaque (`border-left: 4px solid`) — recurso visual consistente entre seções.
- **Fundo da página:** gradiente linear `135deg` com três stops (`#0f2027`, `#203a43`, `#2c5364`) — o dark slate que envolve o container branco.

---

## 🎓 Guia de Uso em Sala

**Trilha sugerida (50 minutos):**

1. **5 min | Motivação** — abrir a página e discutir: "por que um desenvolvedor precisa ler um layout no Figma?". Projetar a seção "O que é Figma?" e ler em voz alta o parágrafo de destaque.
2. **10 min | Cadastro** — alunos seguem os 4 passos na própria máquina, criando conta gratuita. Circulação do professor para conferir quem já confirmou e-mail.
3. **15 min | Vídeo guiado** — assistir ao vídeo do Edu Sites ([youtu.be/J6pP0TFljpo](https://youtu.be/J6pP0TFljpo)) até o momento de criação de frames (MacBook Pro 16 e iPhone 16 Pro Max são os padrões usados pelo instrutor). Pausar e discutir a diferença entre **frame** e **nested frame** — a documentação oficial categoriza essa hierarquia em "Top-level Frame", "Nested Frame" e "Children" ([help.figma.com](https://help.figma.com/hc/article_attachments/26978261914391)).
4. **15 min | Desafio** — projetar ou distribuir o `Desafio_Figma.pdf`, permitir que os alunos tentem por 10 minutos antes de liberar `sugestao.png`.
5. **5 min | Publicação** — seguir a seção "Publicar seu Protótipo" juntos e validar que cada aluno possui um link de visualização ativo.

**Avaliação sugerida:** exigir do aluno o envio do **link de compartilhamento do protótipo** (permissão "Can view") como entrega do desafio. O link é auditável e permite verificar se o fluxo de publicação foi realmente executado — não apenas respondido no papel.

---

## ⚠️ Limitações Conhecidas

| Item | Descrição | Impacto |
| --- | --- | --- |
| **Dependência total de internet** | Nenhum dos vídeos, links externos ou a imagem de referência funciona offline. O HTML em si abre, mas fica com um `<img>` quebrado visível. | Distribuir com uma `sugestao.png` local e baixar a imagem de referência evita desconforto em laboratórios sem rede. |
| **Links relativos sem pasta** | `Desafio_Figma.pdf` e `sugestao.png` são referenciados pelo nome direto. Se forem movidos para uma subpasta (ex.: `assets/`), os botões quebram. | Manter os três arquivos juntos ou ajustar os `href` caso se organize em pastas. |
| **Informação sobre plano gratuito sem fonte citada no HTML** | A afirmação "até 3 projetos e 2 editores simultâneos" aparece como fato; as políticas de plano do Figma variam ao longo do tempo. | Confirmar com a página de planos do Figma antes da aula, se o curso for longo. |
| **Sem `<main>` semântico** | O `.container` cumpre o papel, mas um wrapper `<main>` deixaria a leitura por leitor de tela mais correta. | Melhoria de acessibilidade, não bloqueia uso. |
| **`target="_blank"` sem `rel="noopener"`** | Todos os links abrem em nova aba. O `noopener` é recomendação de segurança. | Não afeta o aluno, mas convém corrigir em versão didática. |
| **Badges sem `aria-label`** | Os emojis dentro dos badges e cards são lidos por extenso por leitores de tela. | Pode ser resolvido com `role="img" aria-label="Design"`, por exemplo. |
| **Vídeos do YouTube sem transcrição / legendas** | O material apenas linka os vídeos — não incorpora legendas embutidas. | Alunos com deficiência auditiva dependem das legendas automáticas do YouTube. |
| **Imagem `help.figma.com` pode ser descontinuada** | A URL é do help center do Figma e não é controlada por quem distribui o material. | Baixar e servir localmente elimina o risco. |
| **Ausência de versão em PDF / impressão** | O material é tela-only, com gradiente de fundo — impressão fica pesada em tinta. | Se for necessário imprimir, criar folha de estilo `@media print`. |

---

## 🗺 Roadmap

Sugestões de evolução para próximas versões:

- [ ] **Fixar a imagem de referência localmente** (`assets/frames-figma.png`) para permitir uso offline.
- [ ] Adicionar `<main>` semântico e `aria-label` nos badges e ícones.
- [ ] Adicionar `rel="noopener noreferrer"` em todos os `target="_blank"`.
- [ ] Incluir **transcrição resumida** de cada vídeo na própria página (aumenta a acessibilidade e desacopla o material do YouTube).
- [ ] Embarcar os vídeos com `<iframe>` do YouTube (privacidade: domínio `youtube-nocookie.com`).
- [ ] Adicionar seção "**Handoff: do Figma ao código**" com exemplo de exportação de CSS a partir do painel de propriedades.
- [ ] Adicionar folha `@media print` para impressão do material.
- [ ] Versão em PDF (fiel ao HTML) para distribuição em LMS.

---

## 📄 Licença & Créditos

Material didático com foco em Figma para o curso técnico de **Desenvolvimento de Sistemas**.

- **Figma** — [figma.com](https://www.figma.com/)
- **Documentação oficial:** [help.figma.com](https://help.figma.com/hc/article_attachments/26978261914391) (hierarquia de frames).
- **Vídeo de referência:** *Aprenda Figma Grátis: Como Criar Interfaces Profissionais do Zero* — Edu Sites, 11/02/2025, 13:44 — [youtu.be/J6pP0TFljpo](https://youtu.be/J6pP0TFljpo).
- **Vídeos complementares:** [youtu.be/69PngSL6XN4](https://youtu.be/69PngSL6XN4) (Thiago Veigah), [youtu.be/uSUBC_kU5Cg](https://youtu.be/uSUBC_kU5Cg) (Panamericana).

Distribuído sob **MIT** — adapte livremente para sua instituição.
