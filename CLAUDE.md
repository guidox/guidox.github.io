# Contesto Progetto: Clonazione Siti in WordPress

## Scopo
Questo repository contiene skill Claude Code per analizzare qualsiasi sito web e
replicarlo in WordPress migliorandolo, usando Divi, Elementor, Gutenberg o HTML puro.

## Skill disponibili
| Comando | Descrizione |
|---------|-------------|
| `/wp-analyze` | Analizza un sito e produce un design brief strutturato |
| `/wp-divi-clone` | Clona un sito intero in WordPress (Divi default) |
| `/wp-divi-section` | Genera una singola sezione/componente |
| `/wp-proposta` | Genera una proposta commerciale per il cliente |

## Formati di output supportati
Specificare con un flag opzionale nell'argomento:
- `--divi` (default) → Divi shortcodes `[et_pb_*]` + CSS
- `--elementor` → JSON importabile via Elementor Library
- `--gutenberg` → Blocchi WordPress nativi
- `--html` → HTML/CSS standalone

---

## DIVI — Architettura e Reference

### Gerarchia
```
[et_pb_section]           ← banda orizzontale intera larghezza
  [et_pb_row]             ← contenitore colonne
    [et_pb_column]        ← colonna (type: 4_4 / 1_2 / 1_3 / 2_3 / 1_4 / 3_4)
      [modulo]            ← contenuto
```

### Regola obbligatoria
Ogni tag Divi DEVE avere `_builder_version="4.27.0"` altrimenti il modulo non appare.

### Moduli principali
| Modulo | Shortcode | Uso tipico |
|--------|-----------|------------|
| Testo | `et_pb_text` | Corpo testo, titoli inline |
| Immagine | `et_pb_image` | Foto, grafica |
| Pulsante | `et_pb_button` | CTA |
| Blurb | `et_pb_blurb` | Card icona + titolo + testo |
| Intestazione fullwidth | `et_pb_fullwidth_header` | Hero grandi |
| Slider | `et_pb_slider` | Hero con carosello |
| Video | `et_pb_video` | Video embed |
| Testimonianza | `et_pb_testimonial` | Social proof |
| Tabella prezzi | `et_pb_pricing_tables` + `et_pb_pricing_table` | Pricing |
| Modulo contatto | `et_pb_contact_form` | Lead form |
| Codice | `et_pb_code` | HTML/JS raw |
| Countdown | `et_pb_countdown_timer` | Urgenza |
| Contatore numeri | `et_pb_number_counter` | Statistiche |
| Accordion/FAQ | `et_pb_toggle` | FAQ |
| Divisore | `et_pb_divider` | Separatore visivo |
| Social media | `et_pb_social_media_follow` | Icone social |
| Mappa | `et_pb_map` | Google Maps |

### Parametri chiave
```
background_color="#1a1a2e"
background_image="URL"          background_size="cover"
text_color="light"              header_text_color="#ffffff"
padding="80px|40px|80px|40px"  (top|right|bottom|left)
header_font_size="48px"         header_font_size_tablet="32px"  header_font_size_phone="24px"
body_font_size="16px"
button_bg_color="#d4af5f"       button_text_color="#ffffff"     button_border_radius="4px"
button_text="Testo CTA"         button_url="URL"
```

### Struttura output Divi
```divi-shortcode
[et_pb_section fb_built="1" _builder_version="4.27.0" background_color="#..." padding="80px|0px|80px|0px"]
  [et_pb_row _builder_version="4.27.0" max_width="1100px" width="90%"]
    [et_pb_column type="4_4" _builder_version="4.27.0"]
      [et_pb_text _builder_version="4.27.0" header_font_size="48px" text_color="light"]
        <h1>Titolo</h1>
        <p>Sottotitolo</p>
      [/et_pb_text]
    [/et_pb_column]
  [/et_pb_row]
[/et_pb_section]
```

---

## ELEMENTOR — Reference Widget

### Struttura JSON base
```json
{
  "type": "section",
  "settings": { "background_color": "#...", "padding": {...} },
  "elements": [{
    "type": "column",
    "settings": { "_column_size": 100 },
    "elements": [{
      "type": "widget",
      "widgetType": "heading",
      "settings": { "title": "Titolo", "size": "h1" }
    }]
  }]
}
```

### Widget principali
| Widget | widgetType | Uso |
|--------|-----------|-----|
| Intestazione | `heading` | H1-H6 |
| Testo | `text-editor` | Corpo testo |
| Immagine | `image` | Foto |
| Pulsante | `button` | CTA |
| Icon Box | `icon-box` | Card icona |
| Testimonianza | `testimonial` | Social proof |
| Accordion | `accordion` | FAQ |
| Prezzi | `price-table` | Pricing |
| Countdown | `countdown` | Urgenza |
| Video | `video` | Embed |
| Divisore | `divider` | Separatore |
| Social Icons | `social-icons` | Social |

---

## GUTENBERG — Blocchi Nativi

### Blocchi principali
```
wp:heading        → <h1>-<h6>
wp:paragraph      → <p>
wp:image          → <figure><img></figure>
wp:buttons        → gruppo pulsanti
wp:button         → singolo pulsante CTA
wp:columns        → layout multi-colonna
wp:column         → colonna dentro wp:columns
wp:cover          → sezione con immagine sfondo
wp:group          → contenitore generico
wp:separator      → linea separatrice
wp:media-text     → immagine + testo affiancati
wp:embed          → embed video/social
```

---

## Standard di qualità output

Ogni output generato dalle skill DEVE migliorare l'originale su:

1. **Accessibilità**: alt text su immagini, ARIA labels, contrasto colori WCAG AA
2. **Mobile**: sempre impostare parametri `_tablet` e `_phone` per font e padding
3. **Performance**: immagini con lazy loading, no script inline inutili
4. **Conversioni**: CTA chiara, headline orientata al beneficio, social proof visibile
5. **Tipografia**: gerarchia chiara H1 > H2 > H3 > body, dimensioni leggibili (body min 16px)
6. **Struttura**: alternare sezioni chiare/scure per ritmo visivo

## Immagini placeholder
Usare `https://placehold.co/WIDTHxHEIGHT/BGCOLOR/TEXTCOLOR?text=Descrizione`
Esempio: `https://placehold.co/1200x600/1a1a2e/ffffff?text=Hero+Image`

## Come analizzare un sito (strategia multi-metodo)
1. `WebFetch` sull'URL → recupera testo e struttura HTML statica
2. Se contenuto < 500 caratteri utili → `WebFetch` su `https://web.archive.org/web/2024*/URL`
3. `WebSearch "[nome sito] screenshot design landing page 2024"` → trova immagini pubbliche
4. `WebSearch "[nome sito] review analisi home page"` → descrizioni testuali
5. Se l'utente ha allegato screenshot → analizzare le immagini direttamente (visione)
6. Dichiarare sempre quali metodi sono stati usati e il livello di certezza
