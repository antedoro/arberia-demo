# Arberia Theme Demo Site

This is the Arberia Theme for Hugo demo site. All information here are useful to show the theme features and install the theme if you want.

- Arberia Demo Site Repository: [https://github.com/antedoro/arberia-demo](https://github.com/antedoro/arberia-demo)
- Arberia Theme Repository: [https://github.com/antedoro/arberia](https://github.com/antedoro/arberia)
---

## ⚡ Installazione rapida di Hugo

Per usare questo progetto hai bisogno di **Hugo Extended** versione **>= 0.148.1**.

### 1. Controlla se hai già Hugo installato

```bash
hugo version
```

### 2. Installa Hugo (se non c’è)

- **macOS** (Homebrew):
  ```bash
  brew install hugo
  ```
- **Linux** (Snap):
  ```bash
  sudo snap install hugo --channel=extended
  ```
- **Windows**: Scarica l’ultima release da [Hugo Releases](https://github.com/gohugoio/hugo/releases).

### 3. Clona il repo, aggiorna i submoduli e installa npm

```bash
git clone https://github.com/antedoro/arberia-demo.git
cd arberia-demo
# Inizializza e aggiorna il submodulo Arberia
git submodule update --init --recursive
npm install
```

### 4. Aggiornare il submodulo Arberia

Se vuoi aggiornare il tema Arberia all'ultima versione:

```bash
cd themes/arberia
git pull origin main
cd ../../
```

---

## 🚀 Comandi rapidi con npm

Abbiamo definito alcuni script nel file `package.json` per semplificare l'uso di Hugo.

### 🔹 Avvio in locale (con bozze)

```bash
npm run serve
```

- Avvia un server di sviluppo su `http://localhost:1313`.
- Mostra anche i contenuti **draft** (`-D`).

---

### 🔹 Build per la produzione

```bash
npm run build
```

- Genera il sito ottimizzato nella cartella `public/`.
- Applica la minificazione di HTML, CSS e JS.
- È lo stesso comando che usa **Netlify** durante il deploy.

---

### 🔹 Pulizia cartella `public/`

```bash
npm run clean
```

- Elimina la cartella `public/`.
- Utile se vuoi rigenerare il sito da zero senza file vecchi.

---

## 📌 Riepilogo comandi

| Comando         | Descrizione                          |
| --------------- | ------------------------------------ |
| `npm run serve` | Avvia il server locale con bozze     |
| `npm run build` | Crea la build ottimizzata per online |
| `npm run clean` | Cancella la cartella `public/`       |

---

## 📝 Deploy su Netlify

Assicurati di avere questo file `netlify.toml` nella root del progetto:

```toml
[build]
  publish = "public"
  command = "hugo --minify"

[build.environment]
  HUGO_VERSION = "0.148.1"
  HUGO_ENV = "production"
  HUGO_ENABLEGITINFO = "true"
```

- Netlify userà Hugo 0.148.1 extended e genererà il sito minificato.
- La cartella `public/` sarà il deploy effettivo.

---

## ℹ️ Note

- In locale usa `npm run serve` per lavorare al sito.
- Su Netlify viene eseguito `npm run build`.
- Se hai dubbi o bug, apri una issue qui: [arberia-demo/issues](https://github.com/antedoro/arberia-demo/issues).

