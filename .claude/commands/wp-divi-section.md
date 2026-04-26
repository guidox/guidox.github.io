Genera una singola sezione WordPress/Divi basata sulla descrizione o riferimento fornito.

## Input
$ARGUMENTS

Analizza l'input per estrarre:
- **Tipo di sezione**: hero, features, testimonianze, prezzi, FAQ, CTA, contatto, video, statistiche, team, footer, o descrizione libera
- **URL di riferimento** (se presente): usa WebFetch per estrarre stile dal sito
- **Preferenze stilistiche**: colori, font, layout menzionati
- **Builder**: cerca `--divi` (default), `--elementor`, `--gutenberg`, `--html`

---

## Analisi (solo se è fornito un URL)

Esegui WebFetch sull'URL presente negli argomenti.
Estrai palette colori e stile tipografico. Applica quello stile alla sezione generata.
Se WebFetch non restituisce contenuto sufficiente, usa WebSearch per trovare screenshot del sito.

---

## Generazione

Genera UNA sola sezione (un blocco `[et_pb_section]` completo con tutto l'interno).

### Quick-reference tipo sezione → moduli Divi

**Hero**
```
[et_pb_section] fullwidth="on"
  [et_pb_fullwidth_header]  titolo, sottotitolo, pulsante CTA, sfondo immagine/gradiente
  + [et_pb_countdown_timer] se richiesta urgenza
```

**Features / Vantaggi**
```
[et_pb_section]
  [et_pb_row] con 3 colonne
    [et_pb_blurb] ×3  icona + titolo + descrizione 2 righe per card
```

**Testimonianze**
```
[et_pb_section]
  [et_pb_row] con 2 colonne
    [et_pb_testimonial] ×2  autore, titolo, azienda, ritratto placeholder
```

**Prezzi**
```
[et_pb_section]
  [et_pb_row]
    [et_pb_pricing_tables]
      [et_pb_pricing_table] ×2-4  piano in evidenza: featured="on"
```

**FAQ / Accordion**
```
[et_pb_section]
  [et_pb_row] colonna unica
    [et_pb_toggle] ×N  primo aperto: open="on"
```

**CTA**
```
[et_pb_section] sfondo alto contrasto
  [et_pb_row]
    [et_pb_text]    titolo grande, sottotitolo
    [et_pb_button]  centrato, largo, hover color definito
```

**Contatto / Form**
```
[et_pb_section]
  [et_pb_row]
    [et_pb_contact_form]  campi: nome, email, messaggio
```

**Statistiche / Numeri**
```
[et_pb_section] sfondo scuro
  [et_pb_row] 3-4 colonne
    [et_pb_number_counter] ×3-4  numero + etichetta
```

**Video**
```
[et_pb_section]
  [et_pb_row] colonna 2/3
    [et_pb_video]  embed centrato
  oppure: colonna 1/2 video + 1/2 testo
```

**Footer**
```
[et_pb_section] sfondo molto scuro
  [et_pb_row] 3-4 colonne
    [et_pb_text]  logo + descrizione
    [et_pb_text]  link navigazione
    [et_pb_social_media_follow]  icone social
    [et_pb_text]  contatti
```

---

## Output (Divi default)

```divi-shortcode
[et_pb_section fb_built="1" _builder_version="4.27.0" background_color="#..." padding="80px|0px|80px|0px"]
  [et_pb_row _builder_version="4.27.0" max_width="1100px" width="90%"]
    [et_pb_column type="..." _builder_version="4.27.0"]
      ...
    [/et_pb_column]
  [/et_pb_row]
[/et_pb_section]
```

```custom-css
/* Incolla in: Divi > Opzioni Tema > CSS Personalizzato */
...
```

**Scelte di design**: [breve spiegazione delle scelte stilistiche]

**Personalizzazione rapida**:
- Colore sfondo: parametro `background_color` nel tag `[et_pb_section]`
- Colore CTA: `button_bg_color` nel tag `[et_pb_button]`
- Font size titolo: `header_font_size` (desktop) e `header_font_size_phone` (mobile)
- Testo: modifica il contenuto HTML dentro i tag dei moduli
