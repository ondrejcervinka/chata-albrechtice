# Chata Albrechtice — Web Project

Landing page pro pronájem chalupy Mariánská hora 776, Jizerské hory.

## Stav projektu

**Fáze:** Třetí iterace — mobile fixes, image positioning, attraction tag links, team review (UX + design + copy).

**Lokální server:** `python3 -m http.server 9000 --directory /Users/ondrejcervinka/Desktop/VScode/website/chata_albrechtice/`
Pak otevřít: http://localhost:9000

**Git:** https://github.com/ondrejcervinka/chata-albrechtice (public)
**Live:** https://ondrejcervinka.github.io/chata-albrechtice/

## Co je hotovo

### Design & layout
- Hero: `fotky/CHATA_MAIN_goldenhour_website.jpeg` (2048px JPEG, letní zlatá hodinka)
- Hero image position: desktop `58% 62%`, mobile `55% 58%` (oddělené hodnoty)
- Nav: jeden frosted glass capsule (logo + separator + links) — desktop centrovaný, mobile vlevo
- Hero titulek: Zodiak Light (`clamp(3.8rem, 9vw, 8rem)`), weight 300
- Scroll indicator: klikatelný — scrolluje na sekci #o-chate
- Hero blur gradient (bottom 55%, blur 2.5px, masked)
- Hero overlay gradients: sníženy na 50 % původní intenzity; na mobilu bez levého gradientu
- "Rezervovat" button: frosted glass capsule styl (matches nav)
- Stat karty: horizontální layout (ikona v kruhu vlevo, text vpravo)
- Footer název: Cormorant Garamond (konzistentní s nav logem)

### Fonty
- **Zodiak Light** (Fontshare CDN) — hero titulek
- **Cormorant Garamond** (Google Fonts) — nav logo + footer název
- **DM Sans** (Google Fonts) — vše ostatní
- Antialiasing: `-webkit-font-smoothing: antialiased` + `-moz-osx-font-smoothing: grayscale`

### Texty & copy (po copywriter review)
- Žádné fráze, žádné em-dashes, žádný scarcity marketing
- "A to je přesně ten bod." — odstraněno
- Ubytování: duplikace z H2 odstraněna
- Galerie H2: "Jak to u nás vypadá"
- Kontakt H2: "Pošlete dotaz nebo rovnou zavolejte."
- Amenity: "Kuchyňská linka" → "Vybavená kuchyně"

### Funkčnost
- Scroll indicator: klik = smooth scroll na #o-chate
- Attraction tagy: všechny jsou `<a>` s externími odkazy (Špičák, magistrála, Google Maps, Zoo Liberec, regiontourist.cz)
- Lightbox: focus trap opraven (klávesnice neunikne z dialogu)
- Kontaktní linky: hover stav (color + underline)
- Galerie popisky: vždy viditelné na mobilu (touch nemá hover)
- Hero CTA → e-chalupy.cz listing
- Adresa → Google Maps
- Email → mailto:

### Mobile
- Hamburger menu: kapsule vlevo, hamburger vpravo — nepřekrývají se
- Separator v nav kapsuli skrytý na mobilu
- Gallery grid: explicitní grid-row na všech items — opraveno překrývání
- Levý hero gradient odstraněn na mobilu

### CSS
- Dead CSS odstraněn: `.hero-eyebrow`, `.btn-wood`, `.restaurants-note`, `.stat-value--word`, `.stat-card--full`, `.scroll-line`, duplicitní `flex-direction: column` v 480px
- Hover transform odstraněn ze stat karet a amenity items (neinteraktivní prvky)
- Kontaktní linky: inline styly přesunuty do CSS třídy

## Otevřené věci (TODO)

### Musí se dořešit s klientem
- **Email** — `info@chata-albrechtice.cz` je stále placeholder
- **Wi-Fi** — není v amenities, ověřit jestli chalupa ho má

### Plánované funkce (další iterace)
- Rezervační systém s napojením na Airbnb + Booking
- Přidat více fotek do galerie (máme 25 v `fotky/`)
- SEO: og:image, structured data
- Google Maps embed v kontaktu
- Instagram link (@marianska_hora776)

## Klíčové URL a kontakty

- **Live:** https://ondrejcervinka.github.io/chata-albrechtice/
- **e-chalupy.cz listing:** https://www.e-chalupy.cz/albrechtice-v-jizerskych-horach-ubytovani-marianska-hora-chalupa-pronajem-o10529
- **Google Maps:** https://maps.google.com/?q=Mariánská+hora+776,+Albrechtice+v+Jizerských+horách
- **Instagram:** @marianska_hora776
- **Telefon:** +420 728 138 020
- **Email (placeholder):** info@chata-albrechtice.cz

## Struktura souborů

```
chata_albrechtice/
├── index.html                              # Landing page
├── style.css                               # Všechny styly
├── CLAUDE.md                               # Tento soubor
├── fotky/
│   ├── CHATA_MAIN_goldenhour_website.jpeg  # Hero foto — aktuální (2048px JPEG)
│   ├── CHATA_MAIN_goldenhour_website.webp  # Hero foto — WebP verze (nepoužívá se)
│   ├── CHATA_MAIN_goldenhour.png           # Hero foto — původní PNG (nepoužívá se)
│   ├── chata_main_nanobanana.png           # Starší hero foto — nepoužívá se
│   └── ...                                 # 25 fotek celkem
├── layout/                                 # Referenční podklady
└── texty.rtf                               # Původní texty od klienta
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
- Hosting: Active24 Smart hosting (produkce) + GitHub Pages (preview/staging)
- Deploy: FTP upload (produkce) / git push (GitHub Pages)
- Fonty: Google Fonts (DM Sans, Cormorant Garamond) + Fontshare (Zodiak)
