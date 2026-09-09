# Calzaturificio Baldi — sito multi-pagina + pannello di gestione

## Struttura del sito

```
baldi-site/
├── index.html          → Home: foto + due righe di storia
├── storia.html          → Pagina "La nostra storia"
├── lavorazione.html     → Pagina "La lavorazione"
├── collezione.html      → Pagina "Collezione" (filtri categoria + stagione, pronta per ~50 foto)
├── contatti.html        → Pagina "Contatti"
├── assets/
│   ├── style.css         → stile condiviso da tutte le pagine
│   └── main.js            → menu, traduzioni IT/EN, animazioni
├── data/
│   └── products.json      → i modelli della collezione (li modifichi dal pannello)
├── images/uploads/        → qui arrivano le foto caricate dal pannello
└── admin/
    ├── index.html          → pannello di gestione (Decap CMS)
    └── config.yml          → configurazione del pannello
```

## Categorie per stagione

Quando aggiungi un nuovo modello dal pannello, ricordati di abbinare categoria e stagione secondo questa regola (il pannello non lo controlla in automatico, quindi va rispettata a mano):

- **Primavera / Estate:** Décolleté, Ballerine, Sandalo
- **Autunno / Inverno:** Tronchetto, Stivale, Stivaletto, Mocassino, Décolleté

## Foto attuali

In home c'è la foto della modella che hai fornito. Nella collezione ci sono 11 modelli con le foto prodotto reali che hai fornito (cartella Giappone). Man mano che hai altre foto, le aggiungi o sostituisci dal pannello di gestione (`/admin`) — bastano due click, una per una, anche fino a 50 foto.

## Come pubblicarlo online (GitHub + Netlify, gratuiti)

### 1. GitHub
1. Crea un account su https://github.com/signup
2. Crea un nuovo repository, es. `calzaturificio-baldi-sito`
3. Carica dentro tutti i file e le cartelle di `baldi-site/` (pulsante "uploading an existing file", trascina tutto, poi "Commit changes")

### 2. Netlify
1. Registrati su https://app.netlify.com/signup (puoi entrare con l'account GitHub)
2. "Add new site" → "Import an existing project" → scegli GitHub → seleziona il repository
3. Lascia vuote le impostazioni di build (è un sito statico) → "Deploy site"
4. In un minuto avrai un indirizzo tipo `nome-a-caso.netlify.app` — il sito è online

### 3. Attivare il pannello di gestione
1. Nel pannello Netlify del sito: **Identity → Enable Identity**
2. **Identity → Registration → Invite only**
3. **Identity → Services → Git Gateway → Enable Git Gateway**
4. **Identity → Invite users** → invita `produzione@baldicalature.it`
5. Apri l'email di invito, imposta la password
6. Vai su `https://tuo-sito.netlify.app/admin/` per accedere al pannello

Da lì potrai:
- cambiare la foto grande della home (sezione "Home" nel pannello)
- caricare/sostituire le foto di ogni modello (anche tutte le ~50 quando le avrai pronte)
- impostare categoria (Décolleté / Stivaletto / Mocassino) e stagione (Primavera-Estate / Autunno-Inverno)
- aggiungere o rimuovere modelli con il pulsante "+" nella lista

Ogni salvataggio dal pannello aggiorna `data/products.json` su GitHub, e il sito si aggiorna online in pochi secondi.

## Dominio personalizzato

Per usare un indirizzo tipo `www.calzaturificiobaldi.it` al posto di `netlify.app`: registra il dominio (es. Register.it, Aruba) e collegalo da **Site settings → Domain management** su Netlify. Scrivimi quando sei a quel punto e ti aiuto con la configurazione DNS.

## Se ti blocchi

Scrivimi esattamente a che passaggio sei arrivato (es. "Netlify non trova Git Gateway") e ti guido da lì.
