# Privacy Policy e avvertenze d'uso — Apri Cancello

Pagina web della **privacy policy** dell'app **Apri Cancello** (con le avvertenze d'uso),
in italiano e inglese, in un unico file statico autonomo: [`index.html`](index.html).
Modellata su quella di Alert4Pills (stesso stile e stessa struttura).

- **Un solo URL** per Google Play: pulsanti IT / EN in alto e auto-rilevamento della lingua del browser.
- **Nessuna dipendenza esterna** (CSS e JavaScript nel file): funziona su GitHub Pages o su qualunque hosting statico, anche aprendola in locale con il browser.
- Tema chiaro/scuro automatico.

## Cosa dice (e deve restare vero)

La pagina riflette il comportamento reale dell'app (verificato nel codice il 2026-10-27):

- dati solo **in locale** (elenco cancelli, cancello predefinito, registro delle aperture con data e ora, numero chiamato, nome del cancello, SIM ed esito); nessun server, nessuna condivisione, nessuna analisi, nessuna pubblicita';
- **backup automatico di Android disattivato** (`allowBackup="false"`);
- il permesso **`INTERNET`** e' dichiarato nel manifest (lo aggiunge l'IDE per i componenti FMX) ma l'app **non lo usa**: la sbarra animata e' un HTML interno mostrato da un visualizzatore web di sistema (`LoadFromStrings(..., 'about:blank')`);
- permessi di telefono: **fare chiamate** (`CALL_PHONE`), **stato del telefono** (`READ_PHONE_STATE`), **terminare la chiamata** (`ANSWER_PHONE_CALLS`);
- avvertenze: la chiamata e' una normale telefonata (puo' avere un costo), l'app non e' un dispositivo di sicurezza, l'apertura automatica del cancello predefinito parte solo a un avvio da zero dopo un conto alla rovescia annullabile.

**Se l'app cambia** (per esempio aggiunge accesso alla rete, backup, un account, la raccolta di dati o nuovi permessi),
aggiornare **questa pagina e la dichiarazione Data Safety** di Google Play Console *prima* del rilascio di quella versione.

## Titolare

I dati sono nell'oggetto `CONTROLLER` all'inizio del blocco `<script>` di [`index.html`](index.html):
**IN THE NET di Gasperoni Robert**, Strada di Paderna 2 (San Marino), SM05524, robert@inthenet.sm, https://www.inthenet.sm.
Per cambiarli basta modificare quell'oggetto. Aggiornare anche la data in `EFFECTIVE` e il numero in `VERSION` a ogni modifica del testo.

## Pubblicazione su GitHub Pages

### Opzione A — repository dedicato (consigliata, URL piu' pulito)

1. Creare un repository **pubblico**, per esempio `apricancello-privacy`.
2. Copiare `index.html` nella radice del repository.
3. Su GitHub: **Settings → Pages → Build and deployment → Source: Deploy from a branch**, branch `main`, cartella `/ (root)`, **Save**.
4. Dopo qualche minuto l'URL sara': `https://robertgasperoni.github.io/apricancello-privacy/`

### Opzione B — sul sito https://www.inthenet.sm

Caricare `index.html` in una sottocartella (per esempio `/apricancello/privacy/`): l'URL sara' `https://www.inthenet.sm/apricancello/privacy/`.

In entrambi i casi **aprire l'URL da un telefono** e controllare che i pulsanti IT / EN funzionino.

## Dove inserire l'URL

- **Google Play Console** → *Contenuti dell'app → Norme sulla privacy* (e nella *Scheda dello Store*): incollare l'URL pubblico.
- (Consigliato) anche **dentro l'app**, come link «Privacy policy» nella schermata di configurazione: oggi non c'e'. Se lo vuoi, e' una modifica da pianificare con la procedura del progetto (requisito, spec, sviluppo della schermata).

## Coerenza con Google Play Data Safety

Nel modulo *Sicurezza dei dati* dichiarare «nessun dato raccolto, nessun dato condiviso». Il motivo: tutto resta sul telefono e non c'e' nessuna trasmissione.
Se in revisione Google chiede del permesso `INTERNET`, la risposta e' nel paragrafo 3 della pagina.
