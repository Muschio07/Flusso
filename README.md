# Flusso — Task Manager

App Kanban personale con account separati, sincronizzazione cloud e supporto mobile.

**Stack:** HTML/CSS/JS · Supabase (database + auth) · Vercel (hosting)

---

## 🚀 Deploy in 4 step (circa 10 minuti)

### Step 1 — Crea il progetto Supabase

1. Vai su [supabase.com](https://supabase.com) e crea un account gratuito
2. Clicca **New project** → dai un nome (es. `flusso`) → scegli una password → scegli la regione più vicina (es. `West EU`) → **Create new project**
3. Aspetta circa 1 minuto che il progetto si avvii
4. Vai su **SQL Editor** (menu laterale) → **New query**
5. Apri il file `schema.sql` di questo repository, copia tutto il contenuto e incollalo → clicca **Run**
6. Vai su **Project Settings → API** e copia:
   - **Project URL** (es. `https://abcdefgh.supabase.co`)
   - **anon public key** (la chiave lunga che inizia con `eyJ...`)

### Step 2 — Configura l'app

Apri il file `index.html` con un editor di testo (anche il Blocco Note va bene).

Trova queste due righe in fondo al file (cerca `INSERISCI_QUI`):

```js
const SUPABASE_URL  = 'INSERISCI_QUI_IL_TUO_SUPABASE_URL';
const SUPABASE_ANON = 'INSERISCI_QUI_IL_TUO_SUPABASE_ANON_KEY';
```

Sostituiscile con i tuoi valori copiati al passo precedente:

```js
const SUPABASE_URL  = 'https://abcdefgh.supabase.co';
const SUPABASE_ANON = 'eyJhbGciOiJIUzI1NiIs...';
```

Salva il file.

### Step 3 — Carica su GitHub

1. Vai su [github.com](https://github.com) (hai già un account) → **New repository**
2. Nome: `flusso` · Visibilità: **Private** (consigliato) oppure Public → **Create repository**
3. Carica i file: clicca **uploading an existing file** → trascina `index.html` e `schema.sql` → **Commit changes**

### Step 4 — Deploy su Vercel

1. Vai su [vercel.com](https://vercel.com) → **Sign up with GitHub**
2. Clicca **Add New → Project** → seleziona il repository `flusso`
3. Non serve configurare nulla → clicca **Deploy**
4. Dopo circa 30 secondi Vercel ti dà un link tipo `https://flusso-xyz.vercel.app`

**Fatto!** Apri quel link da PC, telefono, tablet — i dati sono sempre sincronizzati.

---

## 📱 Installare su iPhone come app

1. Apri il link Vercel su **Safari** (non Chrome)
2. Tocca l'icona **Condividi** (quadrato con freccia in su)
3. Scorri e tocca **"Aggiungi a schermata Home"**
4. Dai un nome → **Aggiungi**

L'app apparirà nella schermata home e si aprirà a schermo intero come un'app nativa.

---

## 👥 Condividere con altri

Manda semplicemente il link Vercel. Chiunque può registrarsi con la propria email e avrà i propri task privati — completamente separati dai tuoi grazie a Supabase Row Level Security.

---

## ✏️ Modificare l'app

Ogni volta che modifichi `index.html` e fai push su GitHub, Vercel aggiorna automaticamente il sito in meno di 1 minuto.

---

## 🔑 Note sulla sicurezza

La chiave `anon` di Supabase è sicura da includere nel codice frontend — è progettata per essere pubblica. La protezione dei dati avviene tramite le **Row Level Security policies** nel database, che impediscono a un utente di vedere i task di un altro anche se conosce la chiave.

---

## 📁 Struttura file

```
flusso/
├── index.html    # App completa (frontend + logica)
├── schema.sql    # Schema database Supabase
└── README.md     # Questa guida
```
