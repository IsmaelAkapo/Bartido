# Bartido — Batidos Naturales en Madrid

Landing page statique pour un bar à smoothies à Madrid.

## Stack
- HTML5 + Tailwind CSS (CDN) + AOS animations
- Fonts: **Lora** (titres) + **Raleway** (corps) — pairing UI/UX Pro Max wellness
- Hébergement: GitHub Pages → https://ismaelakapo.github.io/Bartido/

## Ce qui a été fait (session 2 — 24/04/2026)

### Corrections design + refacto technique

#### Design
- **Hero gradient** : palette harmonisée (`#FF6B35 → #E8511A → #1E3A2F → #2A4F3A`), animation ralentie 20s (était 12s), taille réduite 300% (était 400%) — plus premium, moins agressif
- **CTA Banner** : nouvelle classe `.cta-section` (dark green `#0F2318 → #1E3A2F` + glow radial orange centré) — ne copie plus le hero
- **"Por qué nosotros"** : numéros géants `01` `02` `03` en arrière-plan (style éditorial), `relative overflow-hidden` sur chaque card
- **Testimonios** : card centrale (Carlos G.) mise en vedette — fond dark green `#1E3A2F`, texte blanc, `scale(1.04)`, ombre profonde — casse la "grille cimetière"
- **Section Ubicación — map** : placeholder remplacé par une vraie carte adresse avec icône, texte et bouton "Ver en Google Maps" (propre, intentionnel)

#### Technique
- **SVG deduplication** : icône WhatsApp définie une seule fois via `<symbol id="icon-whatsapp">`, utilisée partout avec `<use href="#icon-whatsapp">` (était répétée 9 fois)
- **SVG deduplication** : étoile de rating définie une seule fois via `<symbol id="icon-star">`, utilisée partout (était répétée 16 fois)
- **OG meta** : ajout `og:image:width` (1200) et `og:image:height` (800)
- **Facebook link** : `href="#"` remplacé par `facebook.com/bartidobar`

## Ce qui a été fait (session 1 — 24/04/2026)

### Design system appliqué (UI/UX Pro Max + Antigravity skills)
- Style : **Soft UI Evolution** — ombres douces multi-couches
- Palette : orange `#FF6B35` (CTA), vert forêt `#1E3A2F` (texte), mint `#ECFDF5` (fonds)
- Or muted `#D97706` remplace le `#FFD700` trop harsh
- Tous les emojis remplacés par **SVG Heroicons**
- `prefers-reduced-motion` CSS complet
- `cursor-pointer`, `aria-label`, `aria-expanded`, `loading="lazy"` partout
- `transition-colors duration-200` sur tous les hovers

### Sections présentes
1. **Navbar** — dark blur (`rgba(255,255,255,0.93)`), hamburger mobile avec aria
2. **Hero** — gradient animé (orange → amber → teal), image flottante, badges glassmorphism
3. **Batidos** — 6 cards (Mango Paradise, Berry Blast, Detox Verde, Banana Power, Choco Dream, El Tuyo)
4. **Por qué nosotros** — 3 features avec icônes SVG gradient
5. **Testimonios** — 3 avis clients (section ajoutée, pattern UI/UX Pro Max)
6. **CTA Banner** — post-testimonials, bouton Instagram
7. **Ubicación** — adresse, horaires, contact, map placeholder
8. **Footer** — nav + réseaux sociaux SVG (Instagram, Facebook, X)

### Responsive (375 → 640 → 768 → 1024 → 1440px)
- Hero : `min-h-[85vh] md:min-h-screen`, image `w-56 sm:w-72 md:w-96`
- Titres : `text-3xl md:text-4xl` / h1 `text-4xl sm:text-5xl md:text-6xl`
- Sections : `py-16 md:py-24`
- Boutons : `px-6 sm:px-8`, `justify-center md:justify-start`
- Testimonials cards : `p-5 sm:p-7`

## Ce qui reste à faire (priorités)

### 1. Contenu réel (bloquant pour le lancement)
- [ ] Remplacer `34600000000` par le vrai numéro WhatsApp partout (navbar, cards, CTA, footer, bouton flottant)
- [ ] Remplacer les liens `instagram.com/bartidobar` et `facebook.com/bartidobar` par les vrais comptes
- [ ] **Google Maps embed** — remplacer le bloc adresse par un vrai `<iframe>` Google Maps
- [ ] Photos réelles du local et des produits (remplacer Unsplash)

### 2. SEO local
- [ ] Mettre la vraie adresse dans le Schema.org JSON-LD (ligne 23-30)
- [ ] Mettre le vrai numéro de téléphone dans le Schema.org

### 3. Améliorations design optionnelles
- [ ] Texte hero : **3D text-shadow** sur h1
- [ ] Icônes "Por qué nosotros" : gradient coloré au lieu de bg pastel

## Fichiers
```
bartido/
├── index.html       # Page principale (627 lignes)
├── css/styles.css   # Vide (tout inline dans index.html)
├── js/main.js       # Vide (JS inline dans index.html)
└── assets/
    ├── icons/       # Vide
    └── images/      # Vide (images Unsplash CDN)
```

## Tailwind config actuelle
```js
colors: {
  primary: '#FF6B35',  // orange CTA
  dark:    '#1E3A2F',  // texte vert forêt
  navy:    '#1A1A2E',  // footer/navbar dark
  amber:   '#D97706',  // or muted
}
```

## À ajouter au prochain Tailwind config (pour effets 3D)
```js
colors: {
  primary: '#FF6B35',
  accent:  '#FF2D78',  // magenta (nouveau)
  gold:    '#FFB800',  // or vif (remplace amber)
  teal:    '#00C896',  // teal électrique (nouveau)
  dark:    '#1E3A2F',
  navy:    '#1A1A2E',
  deep:    '#0A1628',  // bleu nuit (hero dark)
}
```

## Repo
- GitHub : https://github.com/IsmaelAkapo/Bartido
- Live : https://ismaelakapo.github.io/Bartido/
