# Sito Web - Dizionario di Italiano

Questo è il sito web per l'app "Dizionario di Italiano" da pubblicare su GitHub Pages.

## 📁 Struttura del Sito

```
site/
├── index.html          # Homepage principale
├── privacy.html        # Privacy Policy
├── support.html        # Pagina di Supporto / FAQ
├── terms.html          # Termini di Servizio
├── styles.css          # Foglio di stile CSS
├── images/             # Directory per screenshot e immagini
└── README.md           # Questo file
```

## 🚀 Come Pubblicare su GitHub Pages

### 1. Crea un Repository su GitHub

1. Vai su [github.com](https://github.com) e crea un nuovo repository
2. Puoi chiamarlo `dizionario-italiano` o un altro nome a tua scelta
3. Puoi renderlo pubblico o privato (GitHub Pages funziona con entrambi)

### 2. Carica i File

Ci sono due modi per caricare i file:

#### Metodo A: Via Web Interface
1. Nel tuo repository, clicca su "Add file" → "Upload files"
2. Trascina tutti i file dalla directory `site/`
3. Fai commit dei file

#### Metodo B: Via Git (Consigliato)
```bash
# Dalla directory site/
cd "/Users/ginosarnieri/Documents/PROGETTI/Dizionario_italiano/Dizionario di Italiano/site"

# Inizializza git (se non già fatto)
git init

# Aggiungi i file
git add .

# Fai il primo commit
git commit -m "Initial commit: sito web Dizionario di Italiano"

# Aggiungi il remote (sostituisci con il tuo URL)
git remote add origin https://github.com/TUO-USERNAME/dizionario-italiano.git

# Push al repository
git branch -M main
git push -u origin main
```

### 3. Attiva GitHub Pages

1. Nel tuo repository su GitHub, vai su **Settings**
2. Nella barra laterale, clicca su **Pages**
3. In "Source", seleziona:
   - Branch: `main`
   - Folder: `/ (root)`
4. Clicca su **Save**
5. Dopo alcuni minuti, il tuo sito sarà disponibile a: `https://TUO-USERNAME.github.io/dizionario-italiano/`

### 4. (Opzionale) Dominio Personalizzato

Se vuoi usare un dominio personalizzato (es. `dizionarioitaliano.com`):

1. Acquista un dominio da un provider (GoDaddy, Namecheap, ecc.)
2. Nelle impostazioni del dominio, configura i DNS:
   - Aggiungi un record `A` che punta a:
     - `185.199.108.153`
     - `185.199.109.153`
     - `185.199.110.153`
     - `185.199.111.153`
   - O un record `CNAME` che punta a `TUO-USERNAME.github.io`
3. In GitHub Pages settings, inserisci il tuo dominio personalizzato nel campo "Custom domain"
4. Abilita "Enforce HTTPS"

## 📸 Aggiungere Screenshot

Per completare il sito, aggiungi gli screenshot dell'app nella directory `images/`:

### Screenshot Necessari:
- `app-screenshot-1.png` - Screenshot principale per la hero section
- `screenshot-1.png` - Ricerca nel dizionario
- `screenshot-2.png` - Coniugatore verbi
- `screenshot-3.png` - Preferiti
- `screenshot-4.png` - Categorie

### Dimensioni Consigliate:
- Screenshot mobile: 1242 x 2688 px (iPhone resolution)
- Puoi ridimensionarli a 800px di larghezza per web

### Come Aggiungere Screenshot:
1. Prendi screenshot dall'app usando il simulatore o dispositivo fisico
2. Salva le immagini nella directory `site/images/`
3. Assicurati che i nomi corrispondano a quelli referenziati nell'HTML
4. Fai commit e push delle immagini al repository

## 🔧 Personalizzazioni

### Modificare i Link App Store
Quando l'app sarà pubblicata su App Store, aggiorna i link in `index.html`:

Cerca:
```html
<a href="#" class="btn btn-primary">
```

Sostituisci con:
```html
<a href="https://apps.apple.com/app/idXXXXXXXX" class="btn btn-primary">
```

### Modificare le Email di Contatto
Sostituisci `support@example.com` con il tuo indirizzo email reale in:
- `index.html` (footer)
- `privacy.html` (sezione contatti)
- `support.html` (card contatti e footer)
- `terms.html` (footer)

### Modificare i Colori
I colori principali sono definiti in `styles.css` nelle variabili CSS (`:root`):
```css
:root {
    --primary-color: #007AFF;      /* Colore principale (blu iOS) */
    --secondary-color: #5856D6;    /* Colore secondario (viola) */
    --text-color: #1d1d1f;         /* Testo principale */
    --text-secondary: #6e6e73;     /* Testo secondario */
}
```

## 📱 Design Responsive

Il sito è completamente responsive e si adatta automaticamente a:
- 📱 Mobile (< 480px)
- 📱 Tablet (481px - 768px)
- 💻 Desktop (> 768px)

## 🎨 Caratteristiche del Sito

- ✅ Design moderno in stile Apple
- ✅ Completamente responsive
- ✅ Animazioni smooth
- ✅ Hero section accattivante con gradient
- ✅ Griglia features con 9 funzionalità principali
- ✅ Sezione screenshots
- ✅ Privacy Policy completa (GDPR compliant)
- ✅ FAQ dettagliate nella pagina Support
- ✅ Termini di Servizio completi
- ✅ Footer con link utili
- ✅ Ottimizzato per SEO (meta tags)

## 🔍 SEO

Il sito include già:
- Meta description
- Meta keywords
- Title tag ottimizzati
- Struttura semantica HTML5
- Link interni

Per migliorare ulteriormente il SEO:
1. Aggiungi un file `sitemap.xml`
2. Aggiungi un file `robots.txt`
3. Registra il sito su Google Search Console
4. Ottimizza le immagini (usa WebP se possibile)

## 📊 Analytics (Opzionale)

Per tracciare le visite al sito, puoi aggiungere Google Analytics:

1. Crea un account su [analytics.google.com](https://analytics.google.com)
2. Ottieni il tuo tracking ID
3. Aggiungi questo codice prima di `</head>` in ogni pagina HTML:

```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```

## 🐛 Testing

Prima di pubblicare, testa il sito localmente:

### Metodo 1: Python Simple Server
```bash
cd site/
python3 -m http.server 8000
```
Poi apri: `http://localhost:8000`

### Metodo 2: PHP Built-in Server
```bash
cd site/
php -S localhost:8000
```

### Metodo 3: VS Code Live Server
Se usi VS Code, installa l'estensione "Live Server" e clicca con il tasto destro su `index.html` → "Open with Live Server"

## 📝 Checklist Prima della Pubblicazione

- [ ] Screenshot aggiunti nella directory `images/`
- [ ] Link App Store aggiornati (quando disponibili)
- [ ] Email di contatto aggiornate
- [ ] Privacy Policy rivista e personalizzata
- [ ] Termini di Servizio rivisti
- [ ] Testato su mobile
- [ ] Testato su tablet
- [ ] Testato su desktop
- [ ] Link verificati (nessun link rotto)
- [ ] Testo corretto (no errori di battitura)

## 🆘 Supporto

Se hai problemi con la pubblicazione o con GitHub Pages:
- [Documentazione GitHub Pages](https://docs.github.com/en/pages)
- [Risoluzione problemi GitHub Pages](https://docs.github.com/en/pages/getting-started-with-github-pages/troubleshooting-404-errors-for-github-pages-sites)

## 📄 Licenza

© 2026 Dizionario di Italiano. Tutti i diritti riservati.
