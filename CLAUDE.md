# Chata Albrechtice — Web Project

Landing page pro pronájem chalupy Mariánská hora 776, Jizerské hory.

## Stav projektu

**Fáze:** Druhá iterace — hero redesign, UX/copy review zapracován, lightbox hotov.

**Lokální server:** `python3 -m http.server 9000 --directory /Users/ondrejcervinka/Desktop/VScode/website/chata_albrechtice/`
Pak otevřít: http://localhost:9000

**Git:** https://github.com/ondrejcervinka/chata-albrechtice (private)
Poslední commit: UX/copy/web designer review fixes + font swap + lightbox

## Co je hotovo

### Design & layout
- Hero: `fotky/chata_main_nanobanana.png`, text vlevo dole, budova vpravo
- Nav: jeden centrovaný frosted glass capsule (logo + separator + links)
- Hero titulek: Zodiak Light (`clamp(3.8rem, 9vw, 8rem)`), weight 300
- Scroll indicator: animovaný kruh se šipkou, bottom-right
- Hero blur gradient (bottom 55%, blur 2.5px, masked)
- "Rezervovat" button: frosted glass capsule styl (matches nav)
- Stat karty: horizontální layout (ikona v kruhu vlevo, text vpravo)
- Všechna emoji nahrazena Lucide-style SVG ikonkami

### Fonty
- **Zodiak Light** (Fontshare CDN) — hero titulek
- **Cormorant Garamond** (Google Fonts) — nav logo "Chata Albrechtice"
- **DM Sans** (Google Fonts) — vše ostatní (nadpisy sekcí, body, nav links)
- Antialiasing: `-webkit-font-smoothing: antialiased` + `-moz-osx-font-smoothing: grayscale`

### Texty & copy
- Copywriter review zapracován — žádné fráze, žádné em-dashes
- Scroll indicator: jen šipka (text odstraněn — byl anglicky)
- O chatě H2: "Nově zrekonstruovaná. Přímo u vleku."
- Vybavení H2: "Od lyžárny po infrasaunu."
- Okolí H2: "V zimě sjezdovky. V létě magistrála. Zbytek roku jen klid."
- Meta description aktualizována

### Funkčnost
- Ubytování v navigaci (desktop + mobile drawer)
- Hero CTA → přímý odkaz na e-chalupy.cz listing
- Adresa → Google Maps odkaz
- Email → mailto: odkaz
- Lightbox: klik na fotku = fullscreen, šipky vlevo/vpravo, X/Escape zavře
  - Ubytování fotky navigují jen mezi sebou (2 fotky)
  - Galerie fotky navigují jen mezi sebou (6 fotek)
- prefers-reduced-motion: všechny animace potlačeny vč. scrollBounce
- Mobile nav drawer: focus management, Escape, inert links při zavření

### CSS
- Dead CSS odstraněn: `.hero-eyebrow`, `.btn-wood`, `.restaurants-note`
- Attraction tags: hover transform odstraněn (neinteraktivní prvky)

## Otevřené věci (TODO)

### Musí se dořešit s klientem
- **Email** — `info@chata-albrechtice.cz` je stále placeholder, potřebujeme reálný
- **Wi-Fi** — není v amenities, ověřit jestli chalupa ho má
- **Attraction tagy** — `<span>` bez odkazu s hover stylem; rozhodnout: linkovat ven nebo odebrat hover

### Plánované funkce (další iterace)
- Rezervační systém s napojením na Airbnb + Booking
- Přidat více fotek do galerie (máme 25 v `fotky/`)
- SEO: og:image, structured data
- Google Maps embed v kontaktu
- Instagram link (@marianska_hora776)
- Hero image → WebP konverze (PNG je velký, LCP kritická cesta)

## Klíčové URL a kontakty

- **e-chalupy.cz listing:** https://www.e-chalupy.cz/albrechtice-v-jizerskych-horach-ubytovani-marianska-hora-chalupa-pronajem-o10529
- **Google Maps:** https://maps.google.com/?q=Mariánská+hora+776,+Albrechtice+v+Jizerských+horách
- **Instagram:** @marianska_hora776
- **Telefon:** +420 728 138 020
- **Email (placeholder):** info@chata-albrechtice.cz

## Struktura souborů

```
chata_albrechtice/
├── index.html                    # Landing page
├── style.css                     # Všechny styly
├── CLAUDE.md                     # Tento soubor
├── fotky/
│   ├── chata_main_nanobanana.png # Hero foto (letecký zimní pohled) — aktuální
│   ├── CHATA_MAIN.jpg            # Původní hero foto — nepoužívá se
│   └── ...                       # 25 fotek celkem
├── layout/                       # Referenční podklady
│   ├── layout template.png       # WIP layout reference
│   ├── header.png                # Header reference (skog styl)
│   └── booking layout.png        # Booking sekce (zatím neimplementována)
└── texty.rtf                     # Původní texty od klienta
```

## Skills a agenti

Dostupné v `.claude/`:
- `/frontend` — bold redesign komponent nebo celých stránek
- `/run-design` — dvoustupňový pipeline (frontend agent → UX review)
- `/ux` — UX review agent
- `/design-review` — web designer Keep/Remove/Change/Question review
- `/copy` — copywriter agent (voice: stručný, konkrétní, bez fráze)

## Tech stack

- Vanilla HTML/CSS/JS, žádný framework, žádný build tool
- Hosting: Active24 Smart hosting
- Deploy: FTP upload
- Fonty: Google Fonts (DM Sans, Cormorant Garamond) + Fontshare (Zodiak)
