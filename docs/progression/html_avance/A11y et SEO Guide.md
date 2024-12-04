
# HTML Avancé : Guide Exhaustif

## Table des matières
1. [Accessibilité (a11y)](#1-accessibilité-a11y)
    - [Structure sémantique et logique de navigation](#11-structure-sémantique-et-logique-de-navigation)
    - [Navigation au clavier et focus](#12-navigation-au-clavier-et-focus)
    - [Rôles ARIA avancés](#13-rôles-aria-avancés)
    - [Exercices pratiques avancés](#exercices-pratiques-avancés)
2. [SEO Avancé](#2-seo-avancé)
    - [Optimisation des contenus](#21-optimisation-des-contenus)
    - [Optimisation des performances (Core Web Vitals)](#22-optimisation-des-performances-core-web-vitals)
    - [Exercices SEO avancés](#exercices-seo-avancés)
3. [Microdata pour un balisage sémantique avancé](#3-microdata-pour-un-balisage-sémantique-avancé)
    - [Microdata complexe](#31-microdata-complexe)
    - [Exercices Microdata avancés](#exercices-microdata-avancés)
4. [Ressources supplémentaires](#ressources-supplémentaires)

---

## 1. Accessibilité (a11y)

L'accessibilité garantit que les pages web soient utilisables par tous, y compris les personnes ayant des handicaps sensoriels, physiques ou cognitifs.

### 1.1. Structure sémantique et logique de navigation

#### Structure sémantique approfondie
- **Balises de conteneur :**
    - `<header>` : En-têtes (logo, navigation principale, titre de la page).
    - `<footer>` : Informations additionnelles (mentions légales, crédits).
    - `<main>` : Contenu principal unique par page.
    - `<aside>` : Contenus connexes (widgets, publicités).

- **Balises de contenu :**
    - `<article>` : Contenu autonome (articles de blog, produits).
    - `<section>` : Regroupe des contenus thématiquement liés.

#### Exemple structuré
```html
<header>
    <h1>Actualités du Web</h1>
</header>
<main>
    <section>
        <h2>HTML5</h2>
        <article>
            <h3>Introduction au HTML5</h3>
            <p>Le HTML5 est...</p>
        </article>
        <article>
            <h3>Balises multimédia</h3>
            <p>Les balises comme <code>&lt;audio&gt;</code> et <code>&lt;video&gt;</code>...</p>
        </article>
    </section>
</main>
```

---

### 1.2. Navigation au clavier et focus

#### Navigation clavier
1. Tous les éléments interactifs (liens, boutons, formulaires) doivent être accessibles via Tab.
2. Gestion de l’ordre de navigation avec `tabindex` :
    - `tabindex="0"` : Ordre DOM par défaut.
    - `tabindex="-1"` : Exclu de la navigation clavier.

#### Gestion du focus
- Styles visuels pour indiquer le focus :
```css
button:focus {
    outline: 2px solid #00f;
}
```

- Exemple pour un modal :
```html
<div id="modal" role="dialog" aria-labelledby="modalTitle" aria-hidden="true">
    <h2 id="modalTitle">Titre du Modal</h2>
    <button onclick="closeModal()">Fermer</button>
</div>
```

---

### 1.3. Rôles ARIA avancés

#### Cas pratiques
- **Grille interactive** :
```html
<div role="grid">
    <div role="row">
        <div role="gridcell">Cellule 1</div>
        <div role="gridcell">Cellule 2</div>
    </div>
</div>
```

- **Alertes dynamiques** :
```html
<div role="alert">Formulaire soumis avec succès !</div>
```

---

### Exercices pratiques avancés
1. Crée un menu de navigation avec des sous-menus accessibles :
    - Utilise `aria-expanded` et `tabindex` pour indiquer les états.
2. Implémente un modal dynamique avec focus géré.

---

## 2. SEO Avancé

### 2.1. Optimisation des contenus

#### Balises importantes
- `<meta name="description" content="Résumé concis">`
- `<title>Page Optimisée</title>`

#### Rich snippets et données structurées
```html
<script type="application/ld+json">
{
    "@context": "https://schema.org",
    "@type": "WebSite",
    "url": "https://nahual.fr",
    "name": "Nahual Studio"
}
</script>
```

---

### 2.2. Optimisation des performances (Core Web Vitals)

#### Principaux indicateurs
1. **LCP** (Largest Contentful Paint) : Temps de chargement du plus grand élément.
2. **FID** (First Input Delay) : Temps de réponse après une interaction.
3. **CLS** (Cumulative Layout Shift) : Limiter les sauts visuels.

#### Chargement différé
```html
<img src="image.jpg" alt="Exemple" loading="lazy">
```

---

### Exercices SEO avancés
1. Crée une page produit :
    - Rich snippets pour avis et prix.
    - Images optimisées avec `srcset`.
2. Analyse avec [PageSpeed Insights](https://pagespeed.web.dev/).

---

## 3. Microdata pour un balisage sémantique avancé

### 3.1. Microdata complexe

#### Schéma produit
```html
<div itemscope itemtype="https://schema.org/Product">
    <span itemprop="name">Ordinateur Portable</span>
    <img itemprop="image" src="laptop.jpg" alt="Ordinateur">
    <span itemprop="priceCurrency" content="EUR">€</span>
    <span itemprop="price">999.99</span>
</div>
```

---

### Exercices Microdata avancés
1. Implémente un schéma Article avec :
    - Auteur, date, catégorie.
    - Balisage des commentaires.

---

## Ressources supplémentaires
1. [MDN Web Docs : Accessibilité](https://developer.mozilla.org/en-US/docs/Web/Accessibility)
2. [Google Lighthouse](https://developers.google.com/web/tools/lighthouse/)
3. [WCAG Quick Reference](https://www.w3.org/WAI/WCAG21/quickref/)

---

### Remarque importante
Ce cours couvre les bases et des concepts avancés d'accessibilité, SEO, et Microdata, mais approfondir chaque aspect avec des cas spécifiques et des projets réels est crucial pour atteindre un niveau d’expertise.
