# Animations Bretzel 🥨

Une collection d'animations CSS modernes et légères, pilotables via l'attribut HTML `data-animation` au sein d'un fichier CSS unique `anime.css`.

Ce projet explore et démontre l'utilisation des dernières fonctionnalités CSS&#8239;:

- **Scroll-driven Animations** : Animations déclenchées par le défilement.
- **View Transition API** : Transitions fluides entre les pages (MPA).
- **Autres animations modernes** : `@starting-style`, `interpolate-size`, etc. (à venir)

## Installation

Il suffit d'importer le fichier CSS `anime.css` dans votre projet (de préférence dans le fichier d'import général `app.css`).

```css
/* app.css */
@import "anime.css" layer(utilities);
```

## Démo

Une démo est disponible dans le fichier `index.html`.

## Utilisation

### Animations au Scroll

Ajoutez l'attribut `data-animation` sur n'importe quel élément HTML. Vous pouvez combiner plusieurs mots-clés :

1. **Type** : `slide-up`, `slide-left`, `slide-right`, `fade-up`, `fade-left`, `fade-right`, `zoom`, `reveal`, `flip-y`, `flip-x`.
2. **Moment** :
   - `entry` : Déclenche l'animation lorsque l'élément entre dans la vue.
   - `exit` : Déclenche l'animation lorsque l'élément sort de la vue.
   - `entry exit` : Déclenche l'animation lorsque l'élément entre et sort de la vue.
3. **Easing (Optionnel)** :
   - `bounce` : Ajoute un effet de rebond.
4. **Delay (Optionnel)** :
   - `delay-s` (ou `delay`) : Retarde l'animation de 3% du scroll.
   - `delay-m` : Retarde l'animation de 6% du scroll.
   - `delay-l` : Retarde l'animation de 9% du scroll.

**Exemples :**

```html
<!-- Apparition en glissant vers le haut -->
<div data-animation="slide-up entry">...</div>

<!-- Zoom avec effet bounce -->
<div data-animation="zoom entry bounce">...</div>

<!-- Cumul entrée et sortie -->
<div data-animation="fade-up entry exit">...</div>
```

### Animations au Survol

Certaines animations se déclenchent au `:hover` ou `:focus-visible` :

- `shake` : Secousse.
- `spaceboots` : Flottement dans l'espace.

```html
<button data-animation="shake">Survolez-moi</button>
```

### View Transitions (Transitions entre pages)

Pour activer les transitions fluides entre deux pages (Cross-Document View Transitions), ajoutez l'attribut `data-animation` sur l'élément `<html>`.

```html
<html
  lang="fr"
  data-animation="view view-down"></html>
```

_(Note : Ce projet utilise `@view-transition { navigation: auto; }` en CSS, compatible avec les navigateurs récents)._

## Accessibilité

Le projet respecte les préférences utilisateur. Si `prefers-reduced-motion: reduce` est activé au niveau du système, toutes les animations (scroll, hover, view transitions) sont désactivées.

## Compatibilité

- **Scroll-driven Animations**&#8239;: Chrome 115+, Edge 115+.
- **View Transition API**&#8239;: Chrome 111+, Edge 111+, Safari 18+.
