<p align="center"><img src="logo.jpg" alt="SG Lighting Experience" width="140"></p>

# Site Survey App Easy

Web app per fare **sopralluoghi in location per eventi**, pensata per il telefono e per chi non è tecnico.

Con una sola pagina (`index.html`) si può:

- creare un sopralluogo con i dati della location e i contatti (agenzia, location, catering);
- disegnare la **pianta** con pareti misurate in metri, porte e passaggi, palco, mano libera, zoom e spostamento;
- usare una **pianta esistente (immagine o PDF)** come sfondo;
- posizionare **icone colorate** (corrente, audio, video, luci, rete, strutture, accessi, sicurezza…);
- compilare il **Check** per sezione: carico/scarico, corrente (prese per zona), audio, luci, video (proiettori, LED wall, schermi, monitor), strutture (pedane);
- aggiungere **foto** (da fotocamera o dal telefono) in una libreria riusabile;
- generare un **PDF** con anteprima e scaricarlo.

I dati restano **nel browser del dispositivo** (IndexedDB): non c'è nessun server e nessun account.

---

## Come metterla online con GitHub Pages (senza comandi)

1. Su GitHub crea un nuovo repository (ad esempio `site-survey-app-easy`). Può essere pubblico o privato (le Pages su repository privati richiedono un piano a pagamento).
2. Nel repository premi **Add file → Upload files** e trascina **tutto il contenuto di questa cartella**, compresi i file nascosti `.gitignore` e `.nojekyll` (su alcuni sistemi sono nascosti: attiva "mostra file nascosti"). Poi **Commit changes**.
3. Vai in **Settings → Pages**. In *Build and deployment* scegli **Source: Deploy from a branch**, branch **main**, cartella **/ (root)**, poi **Save**.
4. Dopo uno o due minuti l'app è online all'indirizzo:

   `https://TUO-NOME-UTENTE.github.io/NOME-REPOSITORY/`

   (l'indirizzo esatto compare in cima alla pagina Settings → Pages).

## Come metterla online da terminale

```bash
cd site-survey-app-easy
git init
git add .
git commit -m "Prima versione di Site Survey App Easy"
git branch -M main
git remote add origin https://github.com/TUO-NOME-UTENTE/NOME-REPOSITORY.git
git push -u origin main
```

Poi attiva Pages come al punto 3 qui sopra.

## Aggiornare l'app

Sostituisci `index.html` con la nuova versione (nel repository: apri il file → icona matita o **Add file → Upload files** → stesso nome → Commit). Le Pages si aggiornano da sole in un minuto circa.

## Usarla sul telefono

Apri l'indirizzo delle Pages nel browser del telefono. Per averla a portata di mano: **Condividi → Aggiungi a schermata Home** (iPhone) oppure **Menu → Aggiungi a schermata Home** (Android). È una scorciatoia alla pagina web.

## Cose da sapere

- **Dati locali:** i sopralluoghi sono salvati solo su quel browser e quel dispositivo. Cancellare i dati del sito, o cambiare telefono o browser, li fa sparire. Per conservarli o condividerli usa il **PDF** dal Report.
- **Niente funzionamento offline garantito:** l'app non ha ancora un *service worker*, quindi non è una PWA installabile e serve la connessione per aprirla. Una volta aperta, il lavoro in corso resta nel browser.
- **PDF di sfondo:** la lettura dei PDF vettoriali (ad esempio da CAD) è incorporata nel file e si attiva solo quando carichi un PDF. Le immagini molto grandi vengono ridotte a 1800 px.
- **Foto:** vengono ridotte a 1000 px per non appesantire l'archivio del browser.
- **Fotocamera:** dipende dal browser del telefono. Se non si apre, scatta con l'app Fotocamera e scegli la foto dalla libreria.

## Struttura del repository

```
index.html      l'intera app (HTML, CSS e JavaScript in un solo file)
logo.jpg        logo SG Lighting Experience (usato anche dentro l'app)
README.md       queste istruzioni
.gitignore      file da non versionare
.nojekyll       dice a GitHub Pages di pubblicare il file così com'è
```

## Licenze di terze parti

`index.html` include una copia di **PDF.js** (Mozilla), distribuita con licenza **Apache 2.0** (https://github.com/mozilla/pdf.js). Il resto del codice non ha ancora una licenza: se vuoi renderlo riutilizzabile da altri, aggiungi un file `LICENSE` (ad esempio MIT).
