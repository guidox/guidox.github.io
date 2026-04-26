Analizza il sito web fornito e produci un design brief strutturato, pronto per replicarlo in WordPress o presentarlo a un designer.

## Input
$ARGUMENTS

Estrai dall'input: URL del sito e/o nome del sito. Se sono allegate immagini/screenshot, analizzali direttamente.

---

## Raccolta dati (esegui in sequenza)

1. **WebFetch** sull'URL → struttura HTML, testi, meta title/description
2. Se contenuto insufficiente → **WebFetch** su `https://web.archive.org/web/2024*/[URL]`
3. **WebSearch** "[nome sito] screenshot design home page 2024"
4. **WebSearch** "[nome sito] review sito web analisi"
5. Se immagini allegate → analizzale con la visione

Dichiara quali metodi hai usato.

---

## Output: Design Brief Strutturato

---
### Design Brief: [Nome Sito o Dominio]
**URL analizzato**: [URL]
**Data**: [data odierna]
**Settore/Scopo**: [cosa vende o fa il sito]
**Metodi usati**: [WebFetch / WebSearch / Screenshot / ecc.] — Certezza: [alta/media/stimata]

---

#### 1. Palette Colori
| Ruolo | Hex | Utilizzo |
|-------|-----|----------|
| Sfondo principale | #... | Sezioni principali |
| Sfondo secondario | #... | Sezioni alternate |
| Accento | #... | Titoli, icone, highlights |
| CTA Pulsante | #... | Call-to-action principale |
| Testo principale | #... | Corpo testo |
| Testo secondario | #... | Sottotitoli, didascalie |

#### 2. Tipografia
| Elemento | Font Family | Dimensione (desktop) | Peso |
|----------|-------------|---------------------|------|
| H1 | | px | |
| H2 | | px | |
| Body | | px | |
| Pulsante CTA | | px | |

**Equivalente Google Fonts**: [se font custom, indica il più simile su Google Fonts]

#### 3. Struttura Pagina (dall'alto verso il basso)
Per ogni sezione:

```
[NOME SEZIONE] Layout — Modulo Divi consigliato
  Sfondo: [colore/immagine/gradiente]
  Contenuto chiave: [elementi principali]
  Note: [osservazioni]
```

Esempio:
```
[HERO] Full-width, sfondo immagine scura
  → et_pb_fullwidth_header
  → H1: "...", sottotitolo: "...", CTA: "Inizia ora"
  → Overlay gradiente scuro sull'immagine

[FEATURES] 3 colonne, sfondo bianco
  → 3× et_pb_blurb
  → Icona + titolo + descrizione per ogni card

[TESTIMONIANZE] 2 colonne, sfondo grigio chiaro
  → 2× et_pb_testimonial

[CTA FINALE] Full-width, sfondo accento
  → et_pb_text + et_pb_button
```

#### 4. Stile Visivo
- **Aesthetic generale**: [minimale / bold / lusso / giocoso / corporate / artigianale]
- **Border radius**: [nessuno (0px) / leggero (4-8px) / arrotondato (16px+) / pillola (50px)]
- **Ombre**: [assenti / sottili / prominenti]
- **Animazioni**: [assenti / fade sottile / parallax / aggressive]
- **Stile immagini**: [fotografia / illustrazione / icone / misto]
- **Spaziatura**: [compatta / bilanciata / ariosa]

#### 5. Tono del Copy
- **Tono**: [formale / conversazionale / urgente / ispirazionale / tecnico]
- **Audience**: [B2B / B2C / livello tecnico assunto]
- **Stile CTA**: [verbi d'azione usati: "Scopri", "Prenota", "Inizia gratis", ecc.]
- **Lingua**: [italiano / inglese / altro]

#### 6. Problemi rilevati nell'originale
Elenca 4-6 problemi concreti:
- [ ] [Problema specifico, es: "CTA non visibile nella prima schermata"]
- [ ] [Problema specifico, es: "Nessuna sezione testimonianze / social proof"]
- [ ] [Problema specifico, es: "Font troppo piccolo su mobile"]
- [ ] [Problema specifico, es: "Caricamento lento per immagini non ottimizzate"]
- [ ] [Problema specifico, es: "Struttura H1/H2 confusa per SEO"]

#### 7. Miglioramenti proposti
Per ogni problema, proponi la soluzione:
- [ ] [Soluzione concreta]
- [ ] [Soluzione concreta]

#### 8. Note implementazione WordPress
- **Numero stimato sezioni**: N
- **Plugin necessari**: [lista o "Nessuno"]
- **Complessità CSS custom**: [bassa / media / alta]
- **Google Fonts da importare**: [lista font]
- **Stima tempo implementazione**: [ore stimate]

---

**Prossimi passi**:
- Per generare la pagina completa: `/wp-divi-clone [URL]`
- Per generare una sezione specifica: `/wp-divi-section [tipo sezione] [stile]`
- Per creare la proposta commerciale: `/wp-proposta [URL] [Nome Cliente]`
