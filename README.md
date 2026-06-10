# Prestiti PWA — Istruzioni di installazione

## File inclusi
- `index.html` — app completa
- `manifest.json` — configurazione PWA
- `sw.js` — service worker (funzionamento offline)
- `icon-192.png` e `icon-512.png` — **da creare tu** (vedi sotto)

---

## 1. Crea le icone

Crea due immagini PNG quadrate con l'icona della tua app:
- `icon-192.png` — 192×192 px
- `icon-512.png` — 512×512 px

Puoi usare qualsiasi editor (Canva, Figma, ecc.) oppure un emoji 📦 su sfondo scuro.

---

## 2. Aggiungi la tua API Key Anthropic

L'app chiede la API Key al primo avvio (scheda **Config**).
Ottienila su: https://console.anthropic.com/settings/keys

La key viene salvata **solo nel tuo dispositivo** (localStorage), mai inviata altrove.

---

## 3. Pubblica online (gratis)

### Opzione A — Netlify Drop (più semplice, 30 secondi)
1. Vai su https://app.netlify.com/drop
2. Trascina l'intera cartella `prestiti-pwa`
3. Ottieni un URL tipo `https://nome-casuale.netlify.app`

### Opzione B — GitHub Pages
1. Crea un repository su GitHub (es. `prestiti-app`)
2. Carica tutti i file
3. Vai in Settings → Pages → Branch: main → Save
4. URL: `https://tuonome.github.io/prestiti-app`

### Opzione C — Vercel
1. Vai su https://vercel.com/new
2. Import da GitHub o upload diretto

---

## 4. Installa sul telefono come app

### iPhone / iPad
1. Apri l'URL in **Safari**
2. Tocca l'icona **Condividi** (rettangolo con freccia su)
3. Scorri e tocca **"Aggiungi a schermata Home"**
4. L'app apparirà come icona nativa

### Android
1. Apri l'URL in **Chrome**
2. Tocca i tre puntini → **"Aggiungi a schermata Home"**
   (oppure comparirà automaticamente un banner "Installa app")

---

## 5. Sincronizzazione Google Drive (opzionale)

Per abilitare la sync Drive nella versione standalone:

1. Vai su https://console.cloud.google.com
2. Crea un progetto → Abilita **Google Drive API**
3. Crea credenziali OAuth2 (tipo: Web Application)
4. Aggiungi il tuo URL di hosting agli "Authorized JavaScript origins"
5. Copia il **Client ID**
6. In `index.html`, decommenta il blocco `<script>` in fondo
7. Sostituisci `IL_TUO_GOOGLE_CLIENT_ID` con il tuo Client ID

---

## Note

- I dati vengono salvati localmente sul dispositivo (IndexedDB/localStorage)
- Le foto vengono compresse a max 800px per risparmiare spazio
- L'app funziona offline dopo la prima visita (service worker)
- Il riconoscimento AI richiede connessione internet e API Key valida
