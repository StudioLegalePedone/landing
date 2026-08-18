# studiolegalepedone.it — landing page

Pagina statica "sito in aggiornamento" per tenere occupato il dominio, senza framework né dipendenze esterne: un solo file `index.html` (HTML/CSS/JS inline).

## Contenuto volutamente neutro

La pagina non menziona servizi legali attivi né titoli professionali: mostra solo il nome del dominio e la dicitura "sito in aggiornamento". Questo evita ambiguità nel caso venga trovata da qualcuno mentre l'iscrizione all'albo non è attiva. Se in futuro l'attività riprende, basta aggiornare i testi in `index.html`.

## Struttura

```
studiolegalepedone-landing/
├── index.html   # la pagina (tutto inline, nessuna dipendenza)
├── CNAME        # dominio custom per GitHub Pages
└── README.md
```

## Pubblicazione su GitHub Pages

1. Crea un repository su GitHub (es. `studiolegalepedone-landing`) e carica questi file:

   ```bash
   git init
   git add .
   git commit -m "Landing page coming-soon"
   git branch -M main
   git remote add origin https://github.com/<tuo-utente>/studiolegalepedone-landing.git
   git push -u origin main
   ```

2. Nel repository su GitHub: **Settings → Pages**
   - Source: `Deploy from a branch`
   - Branch: `main` / `root`
   - Salva.

3. **DNS del dominio** (dal pannello del tuo registrar):
   - Se `studiolegalepedone.it` è un apex domain (senza `www`), crea 4 record `A` verso gli IP di GitHub Pages:
     ```
     185.199.108.153
     185.199.109.153
     185.199.110.153
     185.199.111.153
     ```
   - Se preferisci usare `www.studiolegalepedone.it`, crea invece un record `CNAME` verso `<tuo-utente>.github.io`.
   - Il file `CNAME` già presente nel repo dice a GitHub Pages quale dominio servire: non serve toccarlo se il dominio resta questo.

4. Dopo la propagazione DNS (di solito da pochi minuti a qualche ora), su **Settings → Pages** attiva "Enforce HTTPS" per il certificato SSL automatico.

## Modificare in futuro

Tutto è in `index.html`: testo in `<main>`, colori nelle variabili CSS (`:root`) in cima al file.
