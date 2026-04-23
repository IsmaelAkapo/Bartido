# Bartido — Batidos Naturales en Madrid

Landing page statique pour un bar à smoothies à Madrid.

## Stack
- HTML5 + Tailwind CSS (CDN) + AOS animations
- Fonts: **Lora** (titres) + **Raleway** (corps) — pairing UI/UX Pro Max wellness
- Hébergement: GitHub Pages → https://ismaelakapo.github.io/Bartido/

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

### 1. Effets 3D + couleurs vibrantes (demandé, pas encore fait)
Inspirations : Joe & the Juice, Pressed, Tropical Smoothie Cafe
- [ ] Hero : gradient animé (`background-size: 400% 400%` + `@keyframes gradientShift`)
- [ ] Blobs flottants en arrière-plan hero (CSS `blur` + `@keyframes`)
- [ ] Hero image : animation float (`@keyframes floatImg`)
- [ ] Cards produits : **tilt 3D** au hover (JS `mousemove` + `perspective`)
- [ ] Cards : barre de couleur gradient en haut (couleur par catégorie)
- [ ] Boutons : effet **shine** (pseudo-element sweep au hover)
- [ ] **Marquee strip** (ticker de valeurs clés entre hero et produits)
- [ ] **Wave SVG dividers** entre sections
- [ ] Palette plus vibrante : ajouter `accent: #FF2D78` (magenta) et `teal: #00C896`
- [ ] Navbar dark sur hero (rgba dark au lieu de blanc)
- [ ] Texte hero : **3D text-shadow** sur h1
- [ ] Icônes features : gradient coloré (orange, amber, green) au lieu de bg pastel

### 2. Fonctionnel
- [ ] Boutons "Pedir" → lien WhatsApp (`https://wa.me/34600000000?text=Hola...`)
- [ ] Google Maps embed dans section ubicación
- [ ] Formulaire de contact fonctionnel (ou lien mailto)

### 3. SEO
- [ ] Schema.org JSON-LD (LocalBusiness + FoodEstablishment)
- [ ] Open Graph meta tags
- [ ] Favicon SVG

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
