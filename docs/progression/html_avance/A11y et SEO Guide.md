# **HTML avancé**

## **1. Accessibilité (a11y)**
L'accessibilité garantit que les pages web soient utilisables par tous, y compris les personnes ayant des handicaps sensoriels, physiques ou cognitifs.
 

### **1.1. Structure sémantique et navigation**

#### **Importance :**

  - Permet aux lecteurs d'écran (comme NVDA ou JAWS) d'identifier clairement le contenu.
  - Facilite l'organisation logique pour les moteurs de recherche et les utilisateurs.
  
#### **Concepts :**

  1. **Balises sémantiques :**
    - Utiliser des balises comme `<header>`, `<main>`, `<section>`, `<article>`, `<aside>`, et `<footer>`.
    - Hiérarchiser les titres correctement (`<h1>` pour le titre principal, puis `<h2>`, etc.).
  2. **Navigation claire :**
    - Ajouter un conteneur `<nav>` pour regrouper les liens de navigation.
    - Exemples :
 

### **1.2. ARIA et attributs spécifiques**

#### **Importance :**
Les attributs ARIA comblent les lacunes des balises HTML natives pour décrire des composants dynamiques (comme les menus ou carrousels).
#### **Concepts :**

  1. **Attributs courants :**
    - `aria-label` : Donne un nom descriptif.
    - `aria-hidden` : Cache un élément des technologies d'assistance.
    - `role` : Décrit la fonction d'un élément.
  2. **Exemple pratique :**
#### **Exercice avancé :**
Créez une page avec un menu déroulant accessible. Assurez-vous que :
  - Le bouton utilise `aria-expanded`.
  - Le menu est masqué via `aria-hidden` lorsque fermé.
 

### **1.3. Couleurs et contrastes**

#### **Règles essentielles :**

  1. Respecter un ratio de contraste d'au moins 4.5:1 pour le texte normal et 3:1 pour le texte large (WCAG 2.1).
  2. Fournir une alternative au contenu dépendant de la couleur.
#### **Outils :**

  - [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/)
 

### **Exercices : Accessibilité**

  1. Ajoutez une navigation avec :
    - Une structure sémantique complète.
    - Des attributs ARIA pertinents.
  2. Utilisez un outil comme Lighthouse (dans Chrome DevTools) pour analyser votre page.
 

## **2. SEO (Search Engine Optimization)**
Le SEO consiste à optimiser une page pour qu'elle soit mieux référencée par les moteurs de recherche.
 

### **2.1. Balises méta et titres**

#### **Concepts clés :**

  1. **Méta description :**
    - Fournit un résumé concis de la page.
    - Longueur recommandée : 50-160 caractères.Exemple :
  2. **Balise `<title>` :**
    - Doit être unique et contenir des mots-clés.
    - Longueur idéale : 50-60 caractères.
  3. **Balises Open Graph :**
    - Optimisent l'affichage des pages sur les réseaux sociaux.Exemple :
 

### **2.2. Optimisation des images**

  1. **Compression :**
    - Utiliser des outils comme [TinyPNG](https://tinypng.com/).
  2. **Texte alternatif :**
    - Décrire chaque image en tenant compte de son contexte.
Exemple :
 

### **2.3. Fichiers robots.txt et sitemap.xml**

#### **Robots.txt :**
Permet d'empêcher certaines pages d'être explorées.
Exemple :
#### **Sitemap.xml :**
Liste des URL importantes pour les moteurs de recherche.
Exemple :
 

### **Exercices : SEO**

  1. Créez une page d'accueil avec :
    - Une balise `<title>` optimisée.
    - Une description SEO correcte.
    - Des images avec attributs `alt`.
  2. Analysez votre page avec [Ahrefs Webmaster Tools](https://ahrefs.com/webmaster-tools).
 

## **3. Microdata pour un balisage sémantique**
Les Microdata enrichissent le HTML avec des métadonnées standardisées.
 

### **3.1. Syntaxe Microdata**

#### **Principaux attributs :**

  1. `itemscope` : Définit une entité.
  2. `itemtype` : Définit le type de l’entité (via Schema.org).
  3. `itemprop` : Spécifie les propriétés.Exemple :
 

### **3.2. Types communs de schémas**

  1. **Article :**
Exemple :
  2. **Produit :**
Exemple :
 

### **Exercices : Microdata**

  1. Implémentez un balisage Microdata pour :
    - Un article de blog avec titre, auteur, date.
    - Une liste de produits fictifs.
  2. Testez vos données avec [Google Rich Results Test](https://search.google.com/test/rich-results).
 

## **Ressources générales**

  1. [HTML Living Standard (WHATWG)](https://html.spec.whatwg.org/multipage/)
  2. [Google Lighthouse](https://addons.mozilla.org/fr/firefox/addon/google-lighthouse/)
  3. [Schema.org Documentation](https://schema.org/)
  4. [WAVE Web Accessibility Evaluation Tool](https://wave.webaim.org/)