# The Dev News - Guia de Implementação de Componentes

## Visão Geral
Este guia fornece exemplos práticos para implementar, estender e personalizar componentes no sistema de blog The Dev News.

## Componentes Principais

### 1. Implementação de Layout

#### Estrutura Completa da Página
```html
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,100..900;1,100..900&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="styles.css">
    <title>Título do Seu Blog</title>
</head>
<body>
    <!-- Componente Header -->
    <header>
        <div id="container-header">
            <h1 id="header-title">Nome do Seu Blog</h1>
        </div>
    </header>

    <!-- Grid de Conteúdo Principal -->
    <main>
        <div>
            <!-- Componente Post Principal -->
            <!-- Componente Posts Recentes -->
        </div>
        
        <!-- Sidebar -->
        <aside>
            <!-- Componente Posts Populares -->
            <!-- Componente Categorias -->
        </aside>
    </main>

    <!-- Componente Footer -->
    <footer>
        <div id="container-footer">
            <p>Copyright@Nome do Seu Blog</p>
        </div>
    </footer>
</body>
</html>
```

### 2. Componente Post Principal

#### Implementação Padrão
```html
<section id="main-post">
    <article id="main-post-article">
        <img src="./img/post-destaque.svg" alt="Imagem do artigo em destaque">
        <div id="main-post-content">
            <span id="category">tecnologia</span>
            <h2>Como criar um blog responsivo moderno</h2>
            <p>By João Developer</p>
        </div>
    </article>
</section>
```

#### Estilo Personalizado para Diferentes Categorias
```css
/* Estilo específico para categorias */
#main-post-content span[id="category"] {
    padding: 0.25rem 0.75rem;
    border-radius: 1rem;
    font-size: 0.875rem;
    font-weight: 500;
}

/* Categoria tecnologia */
#category[data-category="tecnologia"] {
    background-color: rgba(2, 162, 143, 0.2);
    color: #02a28f;
}

/* Categoria saúde */
#category[data-category="saude"] {
    background-color: rgba(76, 175, 80, 0.2);
    color: #4caf50;
}
```

### 3. Implementação de Posts Recentes

#### Seção Completa com Múltiplos Cards
```html
<section id="recent-posts">
    <div id="recent-posts-header">
        <h3 class="title-sections">Posts mais recentes</h3>
        <a href="/posts">Ver todos</a>
    </div>

    <div id="recent-posts-container">
        <!-- Card 1: Post de Tecnologia -->
        <div class="card-recents-container">
            <div class="card-recents-content-img">
                <img class="card-recents-img" src="./img/dicas-javascript.svg" alt="Desenvolvimento JavaScript">
            </div>
            <div class="card-recents-content">
                <p class="card-recents-badge">javascript</p>
                <h2 class="card-recents-title">10 Dicas de JavaScript para 2024</h2>
                <p class="author-text"><strong>By </strong>Ana Costa</p>
                <p class="card-recents-info">
                    Descubra as melhores práticas e técnicas modernas de JavaScript que todo desenvolvedor deveria conhecer em 2024.
                </p>
                <p class="date">15 Janeiro 2024</p>
            </div>
        </div>

        <!-- Card 2: Post de Design -->
        <div class="card-recents-container">
            <div class="card-recents-content-img">
                <img class="card-recents-img" src="./img/ui-design.svg" alt="Tendências de UI Design">
            </div>
            <div class="card-recents-content">
                <p class="card-recents-badge">design</p>
                <h2 class="card-recents-title">Tendências de UI Design</h2>
                <p class="author-text"><strong>By </strong>Carlos Designer</p>
                <p class="card-recents-info">
                    Explore as últimas tendências em design de interface que estão moldando a experiência digital em 2024.
                </p>
                <p class="date">12 Janeiro 2024</p>
            </div>
        </div>

        <!-- Card 3: Post de Carreira -->
        <div class="card-recents-container">
            <div class="card-recents-content-img">
                <img class="card-recents-img" src="./img/crescimento-carreira.svg" alt="Desenvolvimento de Carreira">
            </div>
            <div class="card-recents-content">
                <p class="card-recents-badge">carreira</p>
                <h2 class="card-recents-title">Como crescer como desenvolvedor</h2>
                <p class="author-text"><strong>By </strong>Maria Silva</p>
                <p class="card-recents-info">
                    Estratégias comprovadas para acelerar sua carreira como desenvolvedor e alcançar posições sênior.
                </p>
                <p class="date">10 Janeiro 2024</p>
            </div>
        </div>

        <!-- Card 4: Post de Produtividade -->
        <div class="card-recents-container">
            <div class="card-recents-content-img">
                <img class="card-recents-img" src="./img/produtividade.svg" alt="Ferramentas de Produtividade">
            </div>
            <div class="card-recents-content">
                <p class="card-recents-badge">produtividade</p>
                <h2 class="card-recents-title">Ferramentas para aumentar produtividade</h2>
                <p class="author-text"><strong>By </strong>Pedro Tech</p>
                <p class="card-recents-info">
                    Uma lista curada das melhores ferramentas e apps que podem revolucionar seu fluxo de trabalho diário.
                </p>
                <p class="date">08 Janeiro 2024</p>
            </div>
        </div>
    </div>
</section>
```

### 4. Estilo Aprimorado para Cards

#### Cores de Badge Baseadas em Categoria
```css
/* Estilo aprimorado para badges de categoria */
.card-recents-badge {
    color: #02a28f;
    font-size: 0.875rem;
    font-weight: 500;
    padding: 0.25rem 0.75rem;
    border-radius: 1rem;
    border: 1px solid currentColor;
    display: inline-block;
    margin-bottom: 0.5rem;
}

/* Cores específicas por categoria */
.card-recents-badge[data-category="javascript"] { color: #f7df1e; }
.card-recents-badge[data-category="design"] { color: #ff6b6b; }
.card-recents-badge[data-category="carreira"] { color: #4ecdc4; }
.card-recents-badge[data-category="produtividade"] { color: #45b7d1; }
.card-recents-badge[data-category="desenvolvimento"] { color: #02a28f; }
.card-recents-badge[data-category="saude"] { color: #96ceb4; }
```

### 5. Componentes da Sidebar

#### Posts Populares com Conteúdo Dinâmico
```html
<section id="popular-posts">
    <div id="popular-posts-header">
        <h3 class="titles-sections-sidebar">Posts populares</h3>
    </div>
    
    <!-- Post Popular 1 -->
    <div class="card-popular-container">
        <div class="card-popular-content-img">
            <img class="card-popular-img" src="./img/react-hooks.svg" alt="Tutorial React Hooks">
        </div>
        <div class="card-popular-content">
            <h2 class="card-popular-title">Guia completo do React Hooks</h2>
            <p class="date">20 Dezembro 2023</p>
        </div>
    </div>

    <!-- Post Popular 2 -->
    <div class="card-popular-container">
        <div class="card-popular-content-img">
            <img class="card-popular-img" src="./img/css-grid.svg" alt="Layout CSS Grid">
        </div>
        <div class="card-popular-content">
            <h2 class="card-popular-title">CSS Grid: Layout moderno</h2>
            <p class="date">18 Dezembro 2023</p>
        </div>
    </div>

    <!-- Post Popular 3 -->
    <div class="card-popular-container">
        <div class="card-popular-content-img">
            <img class="card-popular-img" src="./img/typescript.svg" alt="Guia TypeScript">
        </div>
        <div class="card-popular-content">
            <h2 class="card-popular-title">TypeScript para iniciantes</h2>
            <p class="date">15 Dezembro 2023</p>
        </div>
    </div>
</section>
```

#### Categorias com Contagens Dinâmicas
```html
<section id="categories">
    <div id="categories-header">
        <h3 class="titles-sections-sidebar">Categorias</h3>
    </div>
    
    <div class="card-categories-container">
        <p class="categories-text">></p>
        <span class="button-categories" data-category="javascript">javascript</span>
        <p class="categories-text2">(8)</p>
    </div>
    
    <div class="card-categories-container">
        <p class="categories-text">></p>
        <span class="button-categories" data-category="desenvolvimento">desenvolvimento</span>
        <p class="categories-text2">(12)</p>
    </div>
    
    <div class="card-categories-container">
        <p class="categories-text">></p>
        <span class="button-categories" data-category="design">design</span>
        <p class="categories-text2">(6)</p>
    </div>
    
    <div class="card-categories-container">
        <p class="categories-text">></p>
        <span class="button-categories" data-category="carreira">carreira</span>
        <p class="categories-text2">(4)</p>
    </div>
    
    <div class="card-categories-container">
        <p class="categories-text">></p>
        <span class="button-categories" data-category="produtividade">produtividade</span>
        <p class="categories-text2">(5)</p>
    </div>
</section>
```

## Personalizações Avançadas

### 1. Filtro Interativo por Categoria

#### Adicionar JavaScript para Filtro Dinâmico
```html
<script>
document.addEventListener('DOMContentLoaded', function() {
    const categoryButtons = document.querySelectorAll('.button-categories');
    const postCards = document.querySelectorAll('.card-recents-container');
    
    categoryButtons.forEach(button => {
        button.addEventListener('click', function() {
            const selectedCategory = this.dataset.category;
            
            postCards.forEach(card => {
                const cardCategory = card.querySelector('.card-recents-badge').textContent.trim();
                
                if (selectedCategory === 'all' || cardCategory === selectedCategory) {
                    card.style.display = 'flex';
                } else {
                    card.style.display = 'none';
                }
            });
            
            // Atualizar estado ativo
            categoryButtons.forEach(btn => btn.classList.remove('active'));
            this.classList.add('active');
        });
    });
});
</script>
```

#### CSS para Estados Ativos
```css
.button-categories {
    cursor: pointer;
    transition: all 0.3s ease;
    padding: 0.25rem 0.5rem;
    border-radius: 0.25rem;
}

.button-categories:hover {
    background-color: rgba(2, 162, 143, 0.1);
    color: #02a28f;
}

.button-categories.active {
    background-color: #02a28f;
    color: #ffffff;
}
```

### 2. Comportamento Responsivo Aprimorado

#### Breakpoints Personalizados para Telas Grandes
```css
/* Telas de desktop grandes */
@media screen and (min-width: 1440px) {
    main {
        max-width: 120rem;
        grid-template-columns: 4fr 1fr;
    }
    
    #recent-posts-container {
        grid-template-columns: repeat(3, 1fr);
    }
}

/* Telas ultra-wide */
@media screen and (min-width: 1920px) {
    #recent-posts-container {
        grid-template-columns: repeat(4, 1fr);
    }
}
```

### 3. Otimizações de Performance

#### Carregamento Preguiçoso de Imagens
```html
<img class="card-recents-img" 
     src="./img/placeholder.svg" 
     data-src="./img/imagem-real.svg" 
     alt="Descrição"
     loading="lazy">
```

#### CSS para Estados de Carregamento de Imagens
```css
.card-recents-img {
    transition: opacity 0.3s ease;
}

.card-recents-img[data-loaded="false"] {
    opacity: 0.7;
    filter: blur(2px);
}

.card-recents-img[data-loaded="true"] {
    opacity: 1;
    filter: none;
}
```

### 4. Melhorias de Acessibilidade

#### Estrutura Semântica Aprimorada
```html
<main role="main" aria-label="Conteúdo principal">
    <div>
        <section id="main-post" aria-labelledby="titulo-post-destaque">
            <article id="main-post-article">
                <img src="./img/main.svg" alt="Ilustração do artigo em destaque">
                <div id="main-post-content">
                    <span id="category" aria-label="Categoria">tecnologia</span>
                    <h2 id="titulo-post-destaque">Título do Artigo</h2>
                    <p aria-label="Autor">By Nome do Autor</p>
                </div>
            </article>
        </section>

        <section id="recent-posts" aria-labelledby="titulo-posts-recentes">
            <div id="recent-posts-header">
                <h3 id="titulo-posts-recentes" class="title-sections">Posts mais recentes</h3>
                <a href="#" aria-label="Ver todos os posts recentes">Ver todos</a>
            </div>
            <!-- Container dos posts -->
        </section>
    </div>
    
    <aside role="complementary" aria-label="Conteúdo da sidebar">
        <!-- Componentes da sidebar -->
    </aside>
</main>
```

#### Gerenciamento de Foco
```css
/* Estilos de foco para navegação por teclado */
.button-categories:focus,
#recent-posts-header a:focus,
.card-recents-container:focus-within {
    outline: 2px solid #02a28f;
    outline-offset: 2px;
}

/* Link pular para conteúdo */
.skip-link {
    position: absolute;
    top: -40px;
    left: 6px;
    background: #02a28f;
    color: white;
    padding: 8px;
    text-decoration: none;
    z-index: 1000;
}

.skip-link:focus {
    top: 6px;
}
```

## Extensões de Componentes

### 1. Componente de Busca
```html
<section id="search-section">
    <div class="search-container">
        <input type="search" 
               id="blog-search" 
               placeholder="Buscar posts..."
               aria-label="Buscar posts do blog">
        <button type="submit" aria-label="Buscar">
            <svg width="20" height="20" viewBox="0 0 24 24">
                <path d="M15.5 14h-.79l-.28-.27A6.471 6.471 0 0 0 16 9.5 6.5 6.5 0 1 0 9.5 16c1.61 0 3.09-.59 4.23-1.57l.27.28v.79l5 4.99L20.49 19l-4.99-5zm-6 0C7.01 14 5 11.99 5 9.5S7.01 5 9.5 5 14 7.01 14 9.5 11.99 14 9.5 14z"/>
            </svg>
        </button>
    </div>
</section>
```

### 2. Inscrição na Newsletter
```html
<section id="newsletter">
    <div id="newsletter-header">
        <h3 class="titles-sections-sidebar">Newsletter</h3>
    </div>
    <form class="newsletter-form">
        <input type="email" 
               placeholder="Seu email"
               required
               aria-label="Endereço de email">
        <button type="submit">Inscrever-se</button>
    </form>
</section>
```

### 3. Links de Mídias Sociais
```html
<section id="social-media">
    <div id="social-header">
        <h3 class="titles-sections-sidebar">Siga-nos</h3>
    </div>
    <div class="social-links">
        <a href="#" aria-label="Twitter">
            <!-- Ícone do Twitter -->
        </a>
        <a href="#" aria-label="LinkedIn">
            <!-- Ícone do LinkedIn -->
        </a>
        <a href="#" aria-label="GitHub">
            <!-- Ícone do GitHub -->
        </a>
    </div>
</section>
```

Este guia abrangente fornece aos desenvolvedores todas as ferramentas necessárias para implementar, personalizar e estender os componentes do blog The Dev News de forma eficaz.