# The Dev News - Quick Reference Guide

## Component IDs & Classes

### Layout Components
| Component | ID/Class | Purpose |
|-----------|----------|---------|
| Header | `#container-header` | Header wrapper |
| Header Title | `#header-title` | Main site title |
| Main Layout | `main` | CSS Grid container (3fr 1fr) |
| Footer | `#container-footer` | Footer wrapper |

### Main Post
| Element | ID/Class | Purpose |
|---------|----------|---------|
| Container | `#main-post` | Main post section |
| Article | `#main-post-article` | Article wrapper (relative) |
| Content | `#main-post-content` | Overlay content (absolute) |
| Category | `#category` | Category badge |

### Recent Posts
| Element | ID/Class | Purpose |
|---------|----------|---------|
| Section | `#recent-posts` | Recent posts container |
| Header | `#recent-posts-header` | Section header with "View All" |
| Grid | `#recent-posts-container` | 2-column grid (1 on mobile) |
| Card | `.card-recents-container` | Individual post card |
| Image | `.card-recents-img` | Responsive card image |
| Badge | `.card-recents-badge` | Category badge |
| Title | `.card-recents-title` | Post title |
| Info | `.card-recents-info` | Post excerpt |

### Popular Posts (Sidebar)
| Element | ID/Class | Purpose |
|---------|----------|---------|
| Section | `#popular-posts` | Popular posts container |
| Header | `#popular-posts-header` | Section header |
| Card | `.card-popular-container` | Horizontal card |
| Image | `.card-popular-img` | Card image |
| Title | `.card-popular-title` | Post title |

### Categories (Sidebar)
| Element | ID/Class | Purpose |
|---------|----------|---------|
| Section | `#categories` | Categories container |
| Header | `#categories-header` | Section header |
| Row | `.card-categories-container` | Category row |
| Arrow | `.categories-text` | Arrow indicator (>) |
| Button | `.button-categories` | Category name |
| Count | `.categories-text2` | Post count |

### Typography Classes
| Class | Size | Weight | Usage |
|-------|------|--------|-------|
| `.title-sections` | 1.5rem | 700 | Section headers |
| `.titles-sections-sidebar` | 1.5rem | 700 | Sidebar headers |
| `.card-recents-title` | 1.25rem | 700 | Card titles |
| `.card-popular-title` | 0.875rem | 700 | Popular card titles |
| `.author-text` | 1rem | 500 | Author info |
| `.card-recents-info` | 0.875rem | 400 | Body text |
| `.date` | 0.875rem | 500 | Date stamps |

## Responsive Breakpoints

| Breakpoint | Screen Size | Behavior |
|------------|-------------|----------|
| Mobile | ≤767px | Single column, smaller font (0.75rem) |
| Tablet | 768px-1023px | Single column, horizontal sidebar |
| Desktop | ≥1024px | 3:1 grid layout |

## Color Variables

| Color | Hex | Usage |
|-------|-----|-------|
| Brand Teal | `#02a28f` | Headers, badges, accents |
| White | `#ffffff` | Header text, overlays |
| Black | `#000000` | Primary text |
| Gray | `#616161` | Secondary text, metadata |

## Grid Layouts

### Main Layout
```css
main {
    display: grid;
    grid-template-columns: 3fr 1fr; /* Content:Sidebar */
    gap: 1.5rem;
}
```

### Recent Posts Grid
```css
#recent-posts-container {
    display: grid;
    grid-template-columns: 1fr 1fr; /* 2 columns */
    gap: 1.5rem;
}
```

## Card Dimensions

### Recent Post Cards
- Image height: `12rem`
- Content height: `13rem`
- Min width: `16rem`
- Border radius: `0.75rem`

### Popular Post Cards
- Container height: `6rem`
- Image: `8rem × 4.5rem`
- Border radius: `0.75rem`

### Main Post
- Desktop height: `25rem`
- Mobile height: `15.5rem`
- Border radius: `0.75rem`

## Quick Component Templates

### Recent Post Card
```html
<div class="card-recents-container">
    <div class="card-recents-content-img">
        <img class="card-recents-img" src="./img/post.svg" alt="Description">
    </div>
    <div class="card-recents-content">
        <p class="card-recents-badge">category</p>
        <h2 class="card-recents-title">Post Title</h2>
        <p class="author-text"><strong>By </strong>Author</p>
        <p class="card-recents-info">Description...</p>
        <p class="date">Date</p>
    </div>
</div>
```

### Popular Post Card
```html
<div class="card-popular-container">
    <div class="card-popular-content-img">
        <img class="card-popular-img" src="./img/popular.svg" alt="Description">
    </div>
    <div class="card-popular-content">
        <h2 class="card-popular-title">Post Title</h2>
        <p class="date">Date</p>
    </div>
</div>
```

### Category Row
```html
<div class="card-categories-container">
    <p class="categories-text">></p>
    <span class="button-categories">category-name</span>
    <p class="categories-text2">(count)</p>
</div>
```

## Font Stack
```css
font-family: "Montserrat", sans-serif;
```

## Common Modifications

### Change Brand Color
```css
/* Update these selectors */
header, #recent-posts-header, #popular-posts-header, #categories-header {
    background-color: #your-color;
}
.card-recents-badge { color: #your-color; }
```

### Adjust Grid Gaps
```css
#recent-posts-container { gap: 2rem; }
main { gap: 2rem; }
```

### Typography Override
```css
.card-recents-title { 
    font-size: 1.5rem; 
    font-weight: 600; 
}
```