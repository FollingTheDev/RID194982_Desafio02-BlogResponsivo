# The Dev News - Guia de Referência Rápida

## IDs e Classes dos Componentes

### Componentes de Layout
| Componente | ID/Classe | Propósito |
|-----------|----------|-----------|
| Header | `#container-header` | Wrapper do header |
| Título do Header | `#header-title` | Título principal do site |
| Layout Principal | `main` | Container CSS Grid (3fr 1fr) |
| Footer | `#container-footer` | Wrapper do footer |

### Post Principal
| Elemento | ID/Classe | Propósito |
|---------|----------|-----------|
| Container | `#main-post` | Seção do post principal |
| Artigo | `#main-post-article` | Wrapper do artigo (relative) |
| Conteúdo | `#main-post-content` | Conteúdo sobreposto (absolute) |
| Categoria | `#category` | Badge da categoria |

### Posts Recentes
| Elemento | ID/Classe | Propósito |
|---------|----------|-----------|
| Seção | `#recent-posts` | Container dos posts recentes |
| Cabeçalho | `#recent-posts-header` | Cabeçalho da seção com "Ver Todos" |
| Grid | `#recent-posts-container` | Grid de 2 colunas (1 no mobile) |
| Card | `.card-recents-container` | Card individual de post |
| Imagem | `.card-recents-img` | Imagem responsiva do card |
| Badge | `.card-recents-badge` | Badge da categoria |
| Título | `.card-recents-title` | Título do post |
| Info | `.card-recents-info` | Resumo do post |

### Posts Populares (Sidebar)
| Elemento | ID/Classe | Propósito |
|---------|----------|-----------|
| Seção | `#popular-posts` | Container dos posts populares |
| Cabeçalho | `#popular-posts-header` | Cabeçalho da seção |
| Card | `.card-popular-container` | Card horizontal |
| Imagem | `.card-popular-img` | Imagem do card |
| Título | `.card-popular-title` | Título do post |

### Categorias (Sidebar)
| Elemento | ID/Classe | Propósito |
|---------|----------|-----------|
| Seção | `#categories` | Container das categorias |
| Cabeçalho | `#categories-header` | Cabeçalho da seção |
| Linha | `.card-categories-container` | Linha de categoria |
| Seta | `.categories-text` | Indicador de seta (>) |
| Botão | `.button-categories` | Nome da categoria |
| Contagem | `.categories-text2` | Contagem de posts |

### Classes de Tipografia
| Classe | Tamanho | Peso | Uso |
|-------|---------|------|-----|
| `.title-sections` | 1.5rem | 700 | Cabeçalhos de seção |
| `.titles-sections-sidebar` | 1.5rem | 700 | Cabeçalhos da sidebar |
| `.card-recents-title` | 1.25rem | 700 | Títulos dos cards |
| `.card-popular-title` | 0.875rem | 700 | Títulos dos cards populares |
| `.author-text` | 1rem | 500 | Informações do autor |
| `.card-recents-info` | 0.875rem | 400 | Texto do corpo |
| `.date` | 0.875rem | 500 | Carimbos de data |

## Breakpoints Responsivos

| Breakpoint | Tamanho da Tela | Comportamento |
|------------|-----------------|---------------|
| Mobile | ≤767px | Coluna única, fonte menor (0.75rem) |
| Tablet | 768px-1023px | Coluna única, sidebar horizontal |
| Desktop | ≥1024px | Layout grid 3:1 |

## Variáveis de Cores

| Cor | Hex | Uso |
|-----|-----|-----|
| Azul-petróleo da Marca | `#02a28f` | Headers, badges, acentos |
| Branco | `#ffffff` | Texto do header, sobreposições |
| Preto | `#000000` | Texto principal |
| Cinza | `#616161` | Texto secundário, metadados |

## Layouts em Grid

### Layout Principal
```css
main {
    display: grid;
    grid-template-columns: 3fr 1fr; /* Conteúdo:Sidebar */
    gap: 1.5rem;
}
```

### Grid dos Posts Recentes
```css
#recent-posts-container {
    display: grid;
    grid-template-columns: 1fr 1fr; /* 2 colunas */
    gap: 1.5rem;
}
```

## Dimensões dos Cards

### Cards de Posts Recentes
- Altura da imagem: `12rem`
- Altura do conteúdo: `13rem`
- Largura mínima: `16rem`
- Border radius: `0.75rem`

### Cards de Posts Populares
- Altura do container: `6rem`
- Imagem: `8rem × 4.5rem`
- Border radius: `0.75rem`

### Post Principal
- Altura no desktop: `25rem`
- Altura no mobile: `15.5rem`
- Border radius: `0.75rem`

## Templates de Componentes Rápidos

### Card de Post Recente
```html
<div class="card-recents-container">
    <div class="card-recents-content-img">
        <img class="card-recents-img" src="./img/post.svg" alt="Descrição">
    </div>
    <div class="card-recents-content">
        <p class="card-recents-badge">categoria</p>
        <h2 class="card-recents-title">Título do Post</h2>
        <p class="author-text"><strong>By </strong>Autor</p>
        <p class="card-recents-info">Descrição...</p>
        <p class="date">Data</p>
    </div>
</div>
```

### Card de Post Popular
```html
<div class="card-popular-container">
    <div class="card-popular-content-img">
        <img class="card-popular-img" src="./img/popular.svg" alt="Descrição">
    </div>
    <div class="card-popular-content">
        <h2 class="card-popular-title">Título do Post</h2>
        <p class="date">Data</p>
    </div>
</div>
```

### Linha de Categoria
```html
<div class="card-categories-container">
    <p class="categories-text">></p>
    <span class="button-categories">nome-categoria</span>
    <p class="categories-text2">(contagem)</p>
</div>
```

## Conjunto de Fontes
```css
font-family: "Montserrat", sans-serif;
```

## Modificações Comuns

### Alterar Cor da Marca
```css
/* Atualizar estes seletores */
header, #recent-posts-header, #popular-posts-header, #categories-header {
    background-color: #sua-cor;
}
.card-recents-badge { color: #sua-cor; }
```

### Ajustar Espaçamentos do Grid
```css
#recent-posts-container { gap: 2rem; }
main { gap: 2rem; }
```

### Sobrescrita de Tipografia
```css
.card-recents-title { 
    font-size: 1.5rem; 
    font-weight: 600; 
}
```