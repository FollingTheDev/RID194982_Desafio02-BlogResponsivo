# The Dev News - Documentação da API

## Índice
1. [Visão Geral do Projeto](#visão-geral-do-projeto)
2. [Componentes HTML](#componentes-html)
3. [Utilitários CSS e Classes](#utilitários-css-e-classes)
4. [Sistema de Layout](#sistema-de-layout)
5. [Design Responsivo](#design-responsivo)
6. [Sistema de Tipografia](#sistema-de-tipografia)
7. [Paleta de Cores](#paleta-de-cores)
8. [Exemplos de Uso](#exemplos-de-uso)

## Visão Geral do Projeto

**The Dev News** é um website de blog responsivo construído com HTML5 e CSS3 semânticos. O projeto apresenta um design moderno com abordagem mobile-first que se adapta perfeitamente a diferentes dispositivos (smartphone, tablet, desktop, monitores ultrawide).

### Principais Características
- Layout responsivo com grid
- Abordagem de design mobile-first
- Estrutura HTML semântica
- Arquitetura CSS baseada em componentes
- Otimização de imagens SVG

### Tecnologias Utilizadas
- HTML5
- CSS3 (Grid, Flexbox, Media Queries)
- Google Fonts (Montserrat)
- Gráficos SVG

---

## Componentes HTML

### 1. Componente Header

**Propósito:** Navegação principal do site e identidade da marca

**Estrutura:**
```html
<header>
    <div id="container-header">
        <h1 id="header-title">The Dev News</h1>
    </div>
</header>
```

**API:**
- `#container-header`: Container principal com restrição de largura máxima
- `#header-title`: Título do site com estilo da marca

**Uso:**
```html
<!-- Implementação básica do header -->
<header>
    <div id="container-header">
        <h1 id="header-title">Nome do Seu Site</h1>
    </div>
</header>
```

---

### 2. Componente Post Principal

**Propósito:** Exibição de artigo em destaque com conteúdo sobreposto

**Estrutura:**
```html
<section id="main-post">
    <article id="main-post-article">
        <img src="./img/main.svg" alt="Descrição">
        <div id="main-post-content">
            <span id="category">nome-categoria</span>
            <h2>Título do Artigo</h2>
            <p>By Nome do Autor</p>
        </div>
    </article>
</section>
```

**API:**
- `#main-post`: Container com altura fixa (25rem)
- `#main-post-article`: Wrapper do artigo com posição relativa
- `#main-post-content`: Conteúdo sobreposto com posição absoluta

**Propriedades:**
- Altura: 25rem (mobile: 15.5rem)
- Border radius: 0.75rem
- Posicionamento do overlay: inferior-esquerdo

**Exemplo de Uso:**
```html
<section id="main-post">
    <article id="main-post-article">
        <img src="./img/destaque.svg" alt="Imagem do artigo em destaque">
        <div id="main-post-content">
            <span id="category">tecnologia</span>
            <h2>Como implementar componentes reutilizáveis</h2>
            <p>By João Silva</p>
        </div>
    </article>
</section>
```

---

### 3. Componente Posts Recentes

**Propósito:** Layout em grid para exibir posts recentes do blog

**Estrutura:**
```html
<section id="recent-posts">
    <div id="recent-posts-header">
        <h3 class="title-sections">Posts mais recentes</h3>
        <a href="#">Ver todos</a>
    </div>
    <div id="recent-posts-container">
        <!-- Componentes de card aqui -->
    </div>
</section>
```

**API:**
- `#recent-posts`: Container principal
- `#recent-posts-header`: Cabeçalho com título e link "ver todos"
- `#recent-posts-container`: Container grid para os cards
- `.title-sections`: Estilo do título do cabeçalho

**Comportamento do Grid:**
- Desktop: 2 colunas
- Tablet: 2 colunas  
- Mobile: 1 coluna

---

### 4. Componente Card de Post Recente

**Propósito:** Card individual de post com imagem e conteúdo

**Estrutura:**
```html
<div class="card-recents-container">
    <div class="card-recents-content-img">
        <img class="card-recents-img" src="./img/img1.svg" alt="Descrição">
    </div>
    <div class="card-recents-content">
        <p class="card-recents-badge">categoria</p>
        <h2 class="card-recents-title">Título do Post</h2>
        <p class="author-text"><strong>By </strong>Nome do Autor</p>
        <p class="card-recents-info">Descrição do post...</p>
        <p class="date">22 Agosto 2022</p>
    </div>
</div>
```

**Classes da API:**
- `.card-recents-container`: Wrapper principal do card
- `.card-recents-content-img`: Container da imagem (altura 12rem)
- `.card-recents-img`: Imagem responsiva
- `.card-recents-content`: Container do conteúdo (altura 13rem)
- `.card-recents-badge`: Badge da categoria
- `.card-recents-title`: Título do post
- `.card-recents-info`: Resumo do post
- `.author-text`: Informações do autor
- `.date`: Data de publicação

**Dimensões do Card:**
- Altura da imagem: 12rem
- Altura do conteúdo: 13rem
- Largura mínima: 16rem
- Border radius: 0.75rem
- Box shadow: 0px 0.25rem 0.25rem rgba(0, 0, 0, 0.1)

---

### 5. Componente Posts Populares

**Propósito:** Componente da sidebar para conteúdo popular

**Estrutura:**
```html
<section id="popular-posts">
    <div id="popular-posts-header">
        <h3 class="titles-sections-sidebar">Posts populares</h3>
    </div>
    <!-- Containers dos cards -->
</section>
```

**API:**
- `#popular-posts`: Container principal
- `#popular-posts-header`: Cabeçalho da seção
- `.titles-sections-sidebar`: Estilo do título da sidebar

---

### 6. Componente Card de Post Popular

**Propósito:** Card horizontal compacto para posts populares

**Estrutura:**
```html
<div class="card-popular-container">
    <div class="card-popular-content-img">
        <img class="card-popular-img" src="./img/img-pop-01.svg" alt="Descrição">
    </div>
    <div class="card-popular-content">
        <h2 class="card-popular-title">Título do Post</h2>
        <p class="date">22 Agosto 2022</p>
    </div>
</div>
```

**Classes da API:**
- `.card-popular-container`: Container flex horizontal (altura 6rem)
- `.card-popular-content-img`: Container da imagem (8rem largura × 4.5rem altura)
- `.card-popular-img`: Imagem responsiva
- `.card-popular-content`: Container do conteúdo de texto
- `.card-popular-title`: Título do post (fonte 0.875rem)

---

### 7. Componente Categorias

**Propósito:** Navegação da sidebar para categorias de conteúdo

**Estrutura:**
```html
<section id="categories">
    <div id="categories-header">
        <h3 class="titles-sections-sidebar">Categorias</h3>
    </div>
    <div class="card-categories-container">
        <p class="categories-text">></p>
        <span class="button-categories">nome-categoria</span>
        <p class="categories-text2">(quantidade)</p>
    </div>
</section>
```

**Classes da API:**
- `#categories`: Container principal
- `#categories-header`: Cabeçalho da seção
- `.card-categories-container`: Linha individual de categoria
- `.categories-text`: Indicador de seta à esquerda
- `.button-categories`: Nome/botão da categoria
- `.categories-text2`: Contagem de posts

---

### 8. Componente Footer

**Propósito:** Rodapé do site com informações de copyright

**Estrutura:**
```html
<footer>
    <div id="container-footer">
        <p>Copyright@The Dev News</p>
    </div>
</footer>
```

**API:**
- `#container-footer`: Container do conteúdo do footer

---

## Utilitários CSS e Classes

### Classes de Layout

#### Classes de Container
```css
#container-header    /* Wrapper do conteúdo do header */
#container-footer    /* Wrapper do conteúdo do footer */
```

#### Sistemas de Grid
```css
#recent-posts-container {
    display: grid;
    grid-template-columns: 1fr 1fr;  /* 2 colunas no desktop */
    gap: 1.5rem;
}
```

### Classes de Tipografia

#### Títulos
```css
.title-sections          /* Títulos principais de seção (1.5rem) */
.titles-sections-sidebar /* Títulos de seção da sidebar (1.5rem) */
.card-recents-title      /* Títulos dos cards (1.25rem) */
.card-popular-title      /* Títulos dos cards populares (0.875rem) */
```

#### Classes de Texto
```css
.author-text            /* Estilo das informações do autor */
.card-recents-info      /* Texto de resumo do post */
.card-recents-badge     /* Badges de categoria */
.date                   /* Formatação de data */
.categories-text        /* Texto de navegação de categoria */
.button-categories      /* Estilo do botão de categoria */
```

### Classes de Componentes

#### Componentes de Card
```css
.card-recents-container    /* Cards de posts recentes */
.card-popular-container    /* Cards de posts populares */  
.card-categories-container /* Itens de navegação de categoria */
```

#### Containers de Imagem
```css
.card-recents-content-img  /* Containers de imagem de posts recentes */
.card-popular-content-img  /* Containers de imagem de posts populares */
.card-recents-img         /* Imagens de posts recentes */
.card-popular-img         /* Imagens de posts populares */
```

---

## Sistema de Layout

### Estrutura Principal do Layout

O site usa CSS Grid para o layout principal:

```css
main {
    display: grid;
    grid-template-columns: 3fr 1fr;  /* Conteúdo : Sidebar = proporção 3:1 */
    max-width: 90rem;
    margin: 3.5rem auto;
    gap: 1.5rem;
}
```

**Comportamento dos Breakpoints:**
- **Desktop (≥1024px):** Grid 3:1 (conteúdo:sidebar)
- **Tablet (768px-1023px):** 1 coluna, sidebar torna-se horizontal
- **Mobile (≤767px):** 1 coluna, sidebar empilhada verticalmente

### Especificações do Grid

#### Grid dos Posts Recentes
```css
#recent-posts-container {
    display: grid;
    grid-template-columns: 1fr 1fr;  /* 2 colunas */
    gap: 1.5rem;
}

/* Sobrescrita para mobile */
@media screen and (max-width: 767px) {
    #recent-posts-container {
        grid-template-columns: 1fr;  /* 1 coluna */
    }
}
```

---

## Design Responsivo

### Breakpoints

O projeto usa três breakpoints principais:

1. **Mobile:** ≤767px
2. **Tablet:** 768px - 1023px  
3. **Desktop:** ≥1024px

### Comportamento Responsivo

#### Mobile (≤767px)
```css
@media screen and (max-width: 767px) {
    html { font-size: 0.75rem; }              /* Fonte base menor */
    main { grid-template-columns: 1fr; }       /* Coluna única */
    #main-post { height: 15.5rem; }           /* Altura reduzida */
    #recent-posts-container { 
        grid-template-columns: 1fr; 
    }                                          /* Cards em coluna única */
    aside { 
        display: flex;
        flex-direction: column;
        gap: 1.5rem;
    }                                          /* Sidebar empilhada */
}
```

#### Tablet (768px-1023px)
```css
@media screen and (min-width: 768px) and (max-width: 1023px) {
    main { grid-template-columns: 1fr; }       /* Coluna única */
    aside { 
        display: flex;
        gap: 1.5rem;
    }                                          /* Sidebar horizontal */
}
```

### Diretrizes para Imagens Responsivas

Todas as imagens usam técnicas responsivas:

```css
.card-recents-img,
.card-popular-img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 0.75rem;
}
```

---

## Sistema de Tipografia

### Configuração da Fonte

**Fonte Principal:** Montserrat (Google Fonts)
**Fallback:** sans-serif

```css
html {
    font-family: "Montserrat", sans-serif;
    font-size: 1rem;        /* Base para desktop */
}

/* Escala para mobile */
@media screen and (max-width: 767px) {
    html { font-size: 0.75rem; }
}
```

### Escala de Fontes

| Elemento | Tamanho Desktop | Peso | Uso |
|----------|----------------|------|-----|
| `#header-title` | 2.25rem | 700 | Título principal do site |
| `.title-sections` | 1.5rem | 700 | Cabeçalhos de seção |
| `.card-recents-title` | 1.25rem | 700 | Títulos dos cards |
| `.author-text` | 1rem | 500 | Informações do autor |
| `.card-recents-info` | 0.875rem | 400 | Texto do corpo |
| `.card-popular-title` | 0.875rem | 700 | Títulos de cards pequenos |
| `.date` | 0.875rem | 500 | Carimbos de data |

---

## Paleta de Cores

### Cores Primárias

```css
/* Cor Principal da Marca */
#02a28f    /* Azul-petróleo - Headers, botões, acentos */

/* Cores de Texto */
#ffffff    /* Branco - Texto do header, texto sobreposto */
#000000    /* Preto - Texto principal */
#616161    /* Cinza - Texto secundário, metadados */
```

### Diretrizes de Uso

#### Cor da Marca (#02a28f)
- Fundos de cabeçalho
- Cabeçalhos de seção
- Badges de categoria
- Links e acentos

#### Hierarquia de Texto
- **Texto primário:** #000000 (títulos, conteúdo principal)
- **Texto secundário:** #616161 (datas, metadados, categorias)
- **Texto sobreposto:** #ffffff (em fundos coloridos)

### Exemplos de Aplicação de Cores

```css
/* Estilo do header */
header { background-color: #02a28f; }
#header-title { color: #ffffff; }

/* Badge de categoria */
.card-recents-badge { color: #02a28f; }

/* Hierarquia de texto */
.card-recents-title { color: #000000; }
.author-text { color: #616161; }
.date { color: #616161; }
```

---

## Exemplos de Uso

### Criando um Novo Card de Post do Blog

```html
<div class="card-recents-container">
    <div class="card-recents-content-img">
        <img class="card-recents-img" src="./img/novo-post.svg" alt="Imagem do novo post">
    </div>
    <div class="card-recents-content">
        <p class="card-recents-badge">javascript</p>
        <h2 class="card-recents-title">Introdução ao React Hooks</h2>
        <p class="author-text"><strong>By </strong>Maria Santos</p>
        <p class="card-recents-info">
            Aprenda os conceitos fundamentais dos React Hooks e como eles 
            podem simplificar o desenvolvimento de componentes funcionais.
        </p>
        <p class="date">15 Janeiro 2024</p>
    </div>
</div>
```

### Adicionando uma Nova Categoria

```html
<div class="card-categories-container">
    <p class="categories-text">></p>
    <span class="button-categories">javascript</span>
    <p class="categories-text2">(5)</p>
</div>
```

### Criando um Post Popular

```html
<div class="card-popular-container">
    <div class="card-popular-content-img">
        <img class="card-popular-img" src="./img/popular-novo.svg" alt="Post popular">
    </div>
    <div class="card-popular-content">
        <h2 class="card-popular-title">Tendências de Frontend 2024</h2>
        <p class="date">10 Janeiro 2024</p>
    </div>
</div>
```

### Personalizando o Post Principal em Destaque

```html
<section id="main-post">
    <article id="main-post-article">
        <img src="./img/destaque-ia.svg" alt="Inteligência Artificial">
        <div id="main-post-content">
            <span id="category">inteligência artificial</span>
            <h2>O Futuro da IA no Desenvolvimento Web</h2>
            <p>By Dr. Carlos Oliveira</p>
        </div>
    </article>
</section>
```

### Modificações CSS Personalizadas

#### Alterando a Cor da Marca
```css
/* Atualizar todas as instâncias da cor da marca */
header,
#recent-posts-header,
#popular-posts-header,
#categories-header {
    background-color: #sua-cor-da-marca;
}

.card-recents-badge {
    color: #sua-cor-da-marca;
}
```

#### Ajustando o Espaçamento dos Cards
```css
#recent-posts-container {
    gap: 2rem;  /* Aumentar espaço entre cards */
}

.card-recents-container {
    margin-top: 2rem;  /* Aumentar margem superior */
}
```

#### Tipografia Personalizada
```css
html {
    font-family: "Sua-Fonte", "Montserrat", sans-serif;
}

.card-recents-title {
    font-size: 1.5rem;  /* Títulos de cards maiores */
    font-weight: 600;
}
```

---

## Melhores Práticas

### Otimização de Imagens
- Use SVG para gráficos escaláveis
- Mantenha proporções de aspecto com `object-fit: cover`
- Sempre inclua atributos `alt` descritivos
- Otimize tamanhos de arquivo para entrega web

### Acessibilidade
- Use elementos HTML semânticos (`<header>`, `<main>`, `<aside>`, `<footer>`)
- Mantenha hierarquia adequada de cabeçalhos (h1 → h2 → h3)
- Assegure contraste de cores suficiente
- Inclua texto alternativo significativo para imagens

### Performance
- Use CSS Grid e Flexbox para layouts
- Minimize conflitos de especificidade CSS
- Aproveite o cache do navegador para Google Fonts
- Otimize formatos e tamanhos de imagens

### Design Responsivo
- Siga abordagem mobile-first
- Teste em múltiplos tamanhos de dispositivo
- Use unidades relativas (rem, %, vw/vh)
- Assegure que alvos de toque tenham tamanho apropriado

---

## Suporte de Navegadores

### Requisitos Mínimos
- Suporte a CSS Grid (IE11+, todos os navegadores modernos)
- Suporte a Flexbox (IE11+, todos os navegadores modernos)
- Propriedades Customizadas CSS para melhorias futuras
- Suporte a SVG (IE9+, todos os navegadores modernos)

### Navegadores Testados
- Chrome 80+
- Firefox 75+
- Safari 13+
- Edge 80+
- Mobile Safari iOS 13+
- Chrome Mobile 80+

---

Esta documentação cobre todos os componentes públicos, utilitários e padrões disponíveis no projeto do blog The Dev News. Para questões de implementação ou modificações personalizadas, consulte as seções específicas de componentes e exemplos de uso fornecidos acima.