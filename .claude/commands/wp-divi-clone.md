Analizza il sito di riferimento fornito e replicalo come pagina WordPress completa, migliorando l'originale in qualità, conversioni e accessibilità.

## Input
$ARGUMENTS

Analizza l'input per estrarre:
- **URL** del sito da clonare (se presente)
- **Builder** target: cerca `--divi` (default), `--elementor`, `--gutenberg`, `--html`
- Eventuali screenshot o immagini allegate direttamente in chat

---

## FASE 1 — Raccolta dati (esegui in sequenza finché ottieni dati sufficienti)

**Se l'utente ha allegato screenshot o immagini**: analizzale direttamente con la visione — è il metodo più affidabile.

**Se è fornito un URL**, esegui questa catena:

1. `WebFetch` sull'URL originale
2. Se il contenuto recuperato ha meno di 500 caratteri di testo visibile (sito JS-heavy):
   - `WebFetch` su `https://web.archive.org/web/2024*/[URL]`
3. `WebSearch "[nome dominio] screenshot design landing page 2024"`
4. `WebSearch "[nome dominio] home page review sito web"`

**Dichiara sempre** quali metodi hai usato e con quale livello di certezza (alta / media / stimata).

### Da estrarre:
1. **Mappa sezioni** — lista ogni sezione dall'alto verso il basso con il suo tipo (hero, features, testimonianze, prezzi, FAQ, CTA, footer, ecc.)
2. **Palette colori** — sfondo principale, testo, accento, colore CTA
3. **Tipografia** — font family o equivalente Google Fonts, scala dimensioni
4. **Copy** — tutti i titoli, sottotitoli, testi body, label CTA visibili
5. **Immagini** — descrizione di ogni immagine presente
6. **Elementi speciali** — countdown, form, video, mappa, slider, animazioni

---

## FASE 2 — Piano di miglioramento

Prima di generare il codice, elenca **3 miglioramenti concreti** rispetto all'originale:
- Esempio: "CTA più visibile con contrasto più alto"
- Esempio: "Aggiunto social proof mancante nell'originale"
- Esempio: "Ottimizzato per mobile con font scalabili"

---

## FASE 3 — Generazione codice

Genera il codice completo per l'intera pagina nel formato target.

### Regole strutturali Divi (default):
- Ogni sezione: `[et_pb_section]...[/et_pb_section]`
- **Obbligatorio**: `_builder_version="4.27.0"` su ogni singolo tag
- Alternare sfondi chiari/scuri tra le sezioni per ritmo visivo
- Hero: usa `et_pb_fullwidth_header` per hero grandi, o `et_pb_slider` per caroselli
- Features grid: riga con 3 colonne, ciascuna con `et_pb_blurb`
- Testimonianze: `et_pb_testimonial` in riga a 2 colonne
- FAQ: `et_pb_toggle` impilati verticalmente (primo aperto: `open="on"`)
- CTA: sfondo ad alto contrasto + `et_pb_text` grande + `et_pb_button` centrato
- Ogni sezione: padding minimo 80px top/bottom
- Ogni modulo: padding minimo 20px

### Parametri obbligatori per ogni modulo:
- `background_color` o `background_image`
- `text_color` (light/dark)
- `padding` top e bottom
- `header_font_size` + `header_font_size_tablet` + `header_font_size_phone`
- Per pulsanti: `button_bg_color`, `button_text_color`, `button_border_radius`

### Immagini non disponibili:
Usa `https://placehold.co/WIDTHxHEIGHT/BGCOLOR/TEXTCOLOR?text=Descrizione`

### Output Divi:

```divi-shortcode
[et_pb_section fb_built="1" _builder_version="4.27.0" ...]
  [et_pb_row _builder_version="4.27.0" max_width="1100px" width="90%"]
    [et_pb_column type="4_4" _builder_version="4.27.0"]
      ...moduli...
    [/et_pb_column]
  [/et_pb_row]
[/et_pb_section]
... sezioni successive ...
```

```custom-css
/* Incolla in: Divi > Opzioni Tema > CSS Personalizzato */

/* Hero */
.sezione-hero { ... }

/* Features */
.sezione-features { ... }
```

### Output Elementor (`--elementor`):
Genera JSON strutturato con sezioni > colonne > widget, importabile via
Elementor > Libreria Template > Importa. Avvolgi in blocco ```elementor-json```.

### Output Gutenberg (`--gutenberg`):
Genera markup blocchi WordPress (<!-- wp:... -->). Avvolgi in blocco ```gutenberg-blocks```.

### Output HTML puro (`--html`):
Genera HTML/CSS completo autonomo. Avvolgi in blocco ```html```.

---

## FASE 4 — Note di implementazione

Dopo i blocchi di codice, fornisci:

### Immagini da sostituire
| Placeholder | Immagine reale necessaria |
|-------------|--------------------------|
| `/hero-bg` | Foto principale hero (1920x1080px) |
| ... | ... |

### Font da importare
Elenca i Google Fonts da aggiungere in Divi > Opzioni Tema > Font.

### Plugin necessari
Nota eventuali plugin WordPress richiesti (es. WooCommerce, WPForms, ecc.)
oppure scrivi "Nessun plugin aggiuntivo necessario."

### Istruzioni di installazione (Divi)
1. WordPress Admin → Pagine → Aggiungi nuova
2. Titolo: [nome pagina]
3. In alto a destra: cambia editor da "Blocchi" a "Testo/Codice"
4. Incolla il contenuto del blocco `divi-shortcode`
5. Pubblica o Salva bozza
6. Divi → Opzioni Tema → CSS Personalizzato → incolla il blocco `custom-css`
7. Salva modifiche
8. Apri la pagina → clicca "Abilita Visual Builder" per verificare il rendering
