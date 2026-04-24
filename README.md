# Bartido — Batidos Naturales en Madrid

Landing page estática para un bar de smoothies en Madrid.

## Stack
- HTML5 + Tailwind CSS (CDN) + AOS animations
- Fonts: **Lora** (títulos) + **Raleway** (cuerpo)
- Hosting: GitHub Pages → https://ismaelakapo.github.io/Bartido/
- Repo: https://github.com/IsmaelAkapo/Bartido

---

## Estado actual de la página

### Secciones (en orden)
1. **Navbar** — blur backdrop, hamburger mobile con aria-expanded
2. **Hero** — gradiente animado, imagen flotante, badges glassmorphism, botánica SVG animada
3. **Marquee strip** — ticker de valores clave (social proof)
4. **Batidos** — 6 cards con tilt 3D, barra color por categoría, botón WhatsApp por batido
5. **Por qué nosotros** — 3 features con números editoriales 01/02/03 en background
6. **3 CTA cards** — visual cards: Ver carta / Pedir WhatsApp / Ubicación (inspirado Amazonia)
7. **Testimonios** — 3 reviews, card central destacada (dark green, scale)
8. **CTA Banner** — dark green con glow radial, botones WhatsApp + Instagram
9. **Ubicación** — dirección, horarios, contacto, tarjeta con botón Google Maps
10. **Footer** — nav + redes sociales (Instagram, WhatsApp, Facebook)
11. **Botón WA flotante** — oculto en el hero, pulse animation

### Diseño
- Paleta: `#FF6B35` naranja CTA · `#1E3A2F` verde oscuro · `#1A1A2E` navy · `#D97706` amber · `#FF2D78` magenta · `#00C896` teal
- Hero gradiente: `-45deg, #FF6B35, #E8511A, #1E3A2F, #2A4F3A` — animación 20s
- CTA section: `#0F2318 → #1E3A2F` + glow radial naranja centrado
- Cards batidos: rounded-[2rem], barra gradiente top por categoría, card-soft shadows
- Testimonial central: fondo `#1E3A2F`, texto blanco, scale(1.04) en desktop

### Efectos visuales
- **Botánica SVG** en hero: 5 trazos que se dibujan al cargar (stroke-dashoffset)
- **Subrayados ondulados SVG** en títulos de sección: se dibujan al hacer scroll (IntersectionObserver)
- **Transiciones de color por scroll**: body background cambia suavemente entre secciones (IntersectionObserver + CSS transition 0.9s)
- **Tilt 3D** en cards de batidos: JS mousemove + perspective(1000px)
- **Shine effect** en botones CTA: pseudo-element sweep al hover
- **Count-up** en badge "+2.000": IntersectionObserver + requestAnimationFrame
- **Marquee** pausa on hover

### Técnico
- SVG icons definidos una sola vez con `<symbol>`: `#icon-whatsapp` y `#icon-star`
- `prefers-reduced-motion`: todos los efectos JS + CSS desactivados
- Accesibilidad: aria-label, aria-expanded, aria-hidden, focus-visible WCAG AA
- Schema.org JSON-LD (FoodEstablishment), Open Graph completo con dimensiones
- `loading="lazy"` en todas las imágenes

### Responsive
- Hero h1: `text-4xl sm:text-5xl md:text-7xl`
- Secciones: `py-14 md:py-24`
- Section headers: `mb-10 md:mb-16`
- CTA cards: `h-44 sm:h-64 md:h-72`, descripción hidden en móvil
- Batidos imágenes: `h-44 sm:h-56`
- Step numbers: `text-[5rem] md:text-[7rem]`
- Testimonial featured: sin scale en móvil (evita overflow)
- Botones hero: apilados en móvil (`flex-col sm:flex-row`)

---

## Pendiente (necesario para lanzar)

### Contenido real — BLOQUEANTE
- [ ] Reemplazar `34600000000` por el número real de WhatsApp (navbar, 6 cards, CTA, footer, botón flotante)
- [ ] Reemplazar `instagram.com/bartidobar` y `facebook.com/bartidobar` por las cuentas reales
- [ ] **Google Maps embed** — sustituir la tarjeta de dirección por un `<iframe>` real
- [ ] Fotos reales del local y los productos (actualmente Unsplash CDN)
- [ ] Dirección real en Schema.org JSON-LD (líneas 23-30 del `<head>`)

### SEO
- [ ] Número de teléfono real en Schema.org

---

## Tailwind config
```js
colors: {
  primary: '#FF6B35',  // naranja CTA
  dark:    '#1E3A2F',  // texto verde oscuro
  navy:    '#1A1A2E',  // navbar/footer dark
  amber:   '#D97706',  // dorado muted
  accent:  '#FF2D78',  // magenta
  teal:    '#00C896',  // teal
}
```

## CSS classes importantes
| Clase | Uso |
|---|---|
| `.hero-bg` | Gradiente animado del hero |
| `.cta-section` | Fondo dark del banner CTA |
| `.card-soft` | Sombras suaves en cards de batidos |
| `.tilt-card` | Hook JS para el efecto 3D |
| `.btn-shine` | Efecto shine en botones |
| `.action-card` | CTA cards visuales |
| `.testimonial-featured` | Card testimonial destacada |
| `.stroke-hero` | Botánica SVG animada (hero) |
| `.stroke-section` | Subrayados SVG por scroll |
| `.wa-float` | Botón WhatsApp flotante |
| `.marquee-track` | Ticker de social proof |
