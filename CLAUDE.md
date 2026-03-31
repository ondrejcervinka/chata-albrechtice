# Chata Albrechtice — Web Project

Landing page pro pronájem chalupy Mariánská hora 776, Jizerské hory.

## Stav projektu

**Fáze:** První návrh hotov, čeká na feedback a iterace.

**Lokální server:** `python3 -m http.server 9000 --directory /Users/ondrejcervinka/Desktop/VScode/website/chata_albrechtice/`
Pak otevřít: http://localhost:9000

## Co je hotovo

- `index.html` + `style.css` — kompletní landing page
- Světlý design: Cormorant Garamond (nadpisy) + DM Sans (body), paleta krémová/písková/lesní zelená
- Hero: full-bleed `fotky/CHATA_MAIN.jpg`, průhledný nav → frosted glass při scrollu
- Sekce: Hero, O chatě, Ubytování, Vybavení, Okolí & Aktivity, Galerie, Kontakt, Footer
- UX fixes: prefers-reduced-motion, focus states, color contrast, touch targets, keyboard nav
- Texty od copywritera zapracovány
- Všechna emoji nahrazena SVG ikonkami (Lucide styl, lesní zelená)
- Kontakty: tel. +420 728 138 020, e-chalupy.cz rezervace

## Otevřené věci (TODO)

### Musí se dořešit s klientem
- **Email** — v kontaktu je placeholder `info@chata-albrechtice.cz`, potřebujeme reálný
- **e-chalupy.cz URL** — dosazeno zkrácené URL, potřebujeme přesné URL listingu
- **Attraction tagy** — jsou jako `<span>` bez odkazu; rozhodnout jestli linkovat ven nebo ne

### Feedback od web designera (ke zvážení)
- About odstavec začíná "Chalupa Mariánská hora 776 stojí..." — stejná slova jako v nadpisu sekce; zvážit jiný úvod odstavce
- Ubytování sekce nemá odkaz v navigaci (nav má: Galerie, Vybavení, Okolí, Kontakt)
- Contact address badge je dekorativní duplikát — zvážit přidání odkazu na Google Maps
- Léto sekce je obecná — zvážit jestli dát rovnováhu zimě nebo winter-first přístup

### Možná vylepšení do dalších iterací
- Přidat fotky do galerie (máme 25 fotek v `fotky/`)
- Zvážit lightbox na galerii
- SEO meta tagy (og:image, structured data)
- Google Maps embed v kontaktu
- Instagram link (@marianska_hora776)

## Struktura souborů

```
chata_albrechtice/
├── index.html          # Landing page
├── style.css           # Všechny styly
├── CLAUDE.md           # Tento soubor
├── fotky/              # 25 fotek chalupy
│   ├── CHATA_MAIN.jpg  # Hero foto (letecký zimní pohled)
│   └── ...
├── layout/             # Referenční podklady
│   ├── layout template.png   # WIP layout (tmavý, my máme světlý)
│   ├── header.png            # Reference pro header (skog styl)
│   └── booking layout.png    # Booking sekce (zatím neimplementována)
└── texty.rtf           # Původní texty od klienta
```

## Skills a agenti

Dostupné v `.claude/`:
- `/frontend` — bold redesign komponent nebo celých stránek
- `/run-design` — dvoustupňový pipeline (frontend agent → UX review)
- `/ux` — UX review agent
- `/design-review` — web designer Keep/Remove/Change/Question review
- `/copy` — copywriter agent (voice: stručný, konkrétní, bez fráze)

## Kontakty klienta

- Instagram: @marianska_hora776
- Telefon: +420 728 138 020
- Listing: www.e-chalupy.cz (přesné URL zkráceno — doplnit)

## Tech stack

Vanilla HTML/CSS/JS, žádný framework, žádný build tool.
Hosting: Active24 Smart hosting (stejný jako portfolio projekt).
Deploy: FTP upload.
