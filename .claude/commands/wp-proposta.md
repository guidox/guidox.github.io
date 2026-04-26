Genera una proposta commerciale professionale in italiano da presentare al cliente, dopo aver analizzato e migliorato il suo sito in WordPress.

## Input
$ARGUMENTS

Estrai dall'input:
- **URL** del sito originale del cliente
- **Nome cliente** o nome azienda (se fornito)
- **Nome tuo** o della tua agenzia (se fornito, altrimenti usa "il nostro team")

---

## Raccolta dati sul sito originale

Esegui la stessa catena di analisi di `/wp-analyze`:
1. **WebFetch** sull'URL
2. Se insufficiente → **WebFetch** Wayback Machine
3. **WebSearch** per screenshot e descrizioni del sito
4. Immagini allegate → analizza con visione

Identifica i problemi principali del sito originale (velocità, mobile, UX, conversioni, design, SEO).

---

## Output: Proposta Commerciale

Genera il seguente documento in italiano, formattato in modo professionale e leggibile anche da chi non è tecnico.

---

**OGGETTO: Proposta di Restyling Sito Web — [Nome Cliente/Azienda]**

---

Gentile [Nome Cliente],

ho analizzato il suo sito web ([URL]) e ho preparato per lei una proposta concreta per migliorarlo in modo significativo. Le presento i risultati dell'analisi e cosa abbiamo realizzato per lei.

---

### Cosa abbiamo trovato nel sito attuale

Abbiamo analizzato il suo sito e identificato questi punti critici che stanno probabilmente limitando i risultati:

| Problema | Impatto sul business |
|----------|---------------------|
| [Problema 1, es: "Il sito non è ottimizzato per smartphone"] | [Conseguenza, es: "Oltre il 60% degli utenti naviga da mobile: li sta perdendo"] |
| [Problema 2, es: "La call-to-action non è visibile"] | [Conseguenza, es: "I visitatori non sanno cosa fare e abbandonano il sito"] |
| [Problema 3] | [Conseguenza] |
| [Problema 4] | [Conseguenza] |
| [Aggiungere altri in base all'analisi] | |

---

### Cosa abbiamo migliorato nella nuova versione

Abbiamo già realizzato una versione migliorata del suo sito, pronta da installare. Ecco cosa è cambiato:

**Design e Aspetto**
- [Miglioramento design specifico, es: "Nuovo layout moderno con gerarchia visiva chiara"]
- [Miglioramento, es: "Palette colori professionale coerente su tutta la pagina"]
- [Miglioramento, es: "Immagini di alta qualità con placeholder ottimizzati"]

**Esperienza Utente (UX)**
- [Miglioramento UX, es: "Navigazione semplificata: l'utente trova subito quello che cerca"]
- [Miglioramento, es: "Call-to-action in evidenza in ogni sezione della pagina"]
- [Miglioramento, es: "Sezione testimonianze per costruire fiducia"]

**Mobile e Performance**
- [Miglioramento tecnico, es: "Design completamente responsivo per smartphone e tablet"]
- [Miglioramento, es: "Caricamento ottimizzato per velocità"]
- [Miglioramento, es: "Struttura SEO corretta per Google"]

**Conversioni**
- [Miglioramento conversioni, es: "Modulo di contatto integrato e visibile"]
- [Miglioramento, es: "Sezione prezzi chiara con evidenza dell'offerta principale"]
- [Miglioramento, es: "Countdown timer per creare senso di urgenza"]

---

### Confronto: Prima e Dopo

| Aspetto | Sito attuale | Nuova versione |
|---------|-------------|----------------|
| Design mobile | Non ottimizzato | Completamente responsivo |
| Velocità | Lenta | Ottimizzata |
| Call-to-action | Poco visibile | Prominente in ogni sezione |
| Social proof | Assente | Sezione testimonianze dedicata |
| SEO | Struttura non ottimale | Gerarchia H1/H2 corretta |
| [Altro] | [Situazione attuale] | [Situazione migliorata] |

---

### Cosa è incluso nella nostra proposta

- Installazione della nuova versione del sito sul suo WordPress
- Inserimento di tutti i testi e le immagini fornite da lei
- Configurazione del modulo contatto
- Test su desktop, tablet e smartphone
- [Aggiungere altri servizi rilevanti]

---

### Prossimi passi

Per procedere, basta rispondere a questa email (o messaggio) con il suo accordo. Possiamo avere il sito online in [stima tempi, es: 3-5 giorni lavorativi].

Resto a disposizione per qualsiasi domanda o per una videochiamata conoscitiva.

Cordiali saluti,

[Nome / Nome Agenzia]
[Contatto]

---

**P.S.** Le presenterò un'anteprima visiva prima dell'installazione definitiva, così potrà approvare ogni dettaglio.

---

## Note per l'utente

Dopo aver generato questa proposta:
- Personalizza i campi tra [parentesi] con i dati reali
- Aggiungi il tuo contatto, firma e logo
- Se hai già generato il codice con `/wp-divi-clone`, puoi aggiungere uno screenshot del preview come allegato visivo alla proposta
