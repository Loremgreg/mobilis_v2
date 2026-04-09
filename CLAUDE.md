# Mobilis Physio — Instructions pour Claude Code

## Contexte du projet
Site web statique pour **Mobilis Physio**, un service de physiothérapie mobile premium en Allemagne.
- Cible : Privatpatienten et Selbstzahler
- Positionnement : premium, clinique, individuel 
- Langue du site : **allemand**
- Langue des instructions : **français**

---

## ⚠️ RÈGLE ABSOLUE — RÉFÉRENCE PRIORITAIRE

Si une référence visuelle (site concurrent / screenshot) est fournie :

- Reproduire FIDÈLEMENT :
  - layout
  - spacing
  - structure
  - hiérarchie
- Remplacer uniquement :
  - textes → contenu Mobilis
  - images → placeholders (https://placehold.co/)
- Ne PAS améliorer le design
- Ne PAS ajouter de sections
- Ne PAS interpréter

Objectif : copie pixel-perfect


## Reference Images
- If a reference image is provided: match layout, spacing, typography, and color exactly. Swap in placeholder content (images via `https://placehold.co/`, generic copy). Do not improve or add to the design.
- If no reference image: design from scratch with high craft (see guardrails below).
- Screenshot your output, compare against reference, fix mismatches, re-screenshot. Do at least 2 comparison rounds. Stop only when no visible differences remain or user says so.

##  RÈGLE référence Images

Priorité absolue :

1. Fidélité à la référence
2. Qualité d’exécution (pixel-perfect)
---

## Stack technique
- HTML5 sémantique + CSS3 + Vanilla JS uniquement
- Aucun framework (pas Bootstrap, pas Tailwind, pas jQuery)
- Google Fonts uniquement comme ressource externe

---

## Workflow de développement frontend

### Skill frontend-design
- **Invoquer le skill `frontend-design`** avant d'écrire du code frontend en début de session.

### Serveur local + Screenshots
- Toujours servir via localhost — ne jamais prendre de screenshot d'une URL `file:///`
- Démarrer le serveur : `npx serve . -l 3000` (ou équivalent) en arrière-plan
- Prendre des screenshots avec Puppeteer pour vérifier le rendu visuel
- Après chaque page créée ou modifiée : screenshot → comparer → corriger → re-screenshot
- Faire au minimum 2 passes de comparaison avant de considérer une page terminée
- Vérifier : spacing/padding, tailles de police, couleurs exactes, alignement, border-radius, ombres, responsive

---


### Guardrails qualité CSS
- Jamais `transition: all` — toujours cibler les propriétés exactes (`transform`, `opacity`, `background-color`)
- Chaque élément cliquable doit avoir des états `:hover`, `:focus-visible` et `:active`
- Ombres teintées avec la couleur primaire en rgba — jamais du noir pur
- Système de profondeur : surfaces base → élevées → flottantes (pas tout au même plan z)
- Overlays sur images placeholder : gradient `linear-gradient(to top, rgba(0,0,0,0.5), transparent)`

---

## Règles SEO (priorité haute)
Le SEO est la principale source d'acquisition. Appliquer rigoureusement :

### Meta tags — chaque page doit avoir :
```html
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>[Titre optimisé]</title>
<meta name="description" content="[160 caractères max]">
<link rel="canonical" href="https://www.mobilis-physio.de/[page]">
```


### Règles HTML pour le SEO :
- Un seul `<h1>` par page
- Hiérarchie des titres respectée : H1 → H2 → H3
- Tous les `<img>` doivent avoir un attribut `alt` descriptif en allemand
- Les liens internes doivent avoir des textes d'ancre descriptifs
- Pas de liens brisés

<!-- ### Page Standorte — SEO local prioritaire :
- Chaque ville a un `<h2>` contenant le nom exact de la ville
- Le terme "Physiotherapie Hausbesuch" apparaît dans chaque bloc ville
- Meta title : `Physiotherapie Hausbesuch München & Umgebung | Mobilis Physio`
- Meta description : mentionner toutes les villes dans les 160 caractères -->


---

## Hard Rules
- Do not add sections, features, or content not in the reference
- Do not "improve" a reference design — match it
- Do not stop after one screenshot pass
- Do not use `transition-all`
- Tester mentalement la responsivité de chaque section avant de passer à la suivante
