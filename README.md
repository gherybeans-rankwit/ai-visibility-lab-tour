# AI Visibility Lab · sito del tour

Sito vetrina del roadshow AI Visibility Lab di RankWit. È un'unica pagina statica: `index.html`, senza dipendenze da installare (carica solo i font da Google Fonts).

## Cosa contiene

- **Home**: mappa delle tappe, calendario, come si partecipa, report, argomenti delle sessioni, modulo "Avvisami o proponi una città", partner, domande frequenti, modulo contatti.
- **Pagine separate**: `#hotel`, `#destinations` e una pagina per ogni tappa (`#casentino`, `#firenze`, ...).

## Aggiornare le tappe

Le tappe sono nell'array `TAPPE` in cima allo script di `index.html`.

- `dataISO` (AAAA-MM-GG): giorno della tappa. Dal giorno dopo la tappa risulta "Conclusa" in automatico (ora italiana). Senza `dataISO` risulta "Prossimamente".
- `lat`, `lon`: posizione del punto sulla mappa.
- `breve`, `tabellone`: nomi corti per mappa e calendario quando il nome è lungo.
- Una tappa senza `intro` mostra la pagina "Informazioni disponibili a breve" con il modulo Avvisami. Con `intro`, `sede`, `formato`, `costo`, `agenda` diventa una pagina completa (vedi Firenze e Rimini).

## Da collegare

- **Moduli (Avvisami e Contatti)**: entrambi usano la funzione `inviaRichiesta(rec)`, che oggi salva nel database dell'anteprima su claude.ai. Sul sito va sostituita con una chiamata al vostro backend o CRM. Il resto dei moduli (campi, controlli, conferma) non cambia.
- **Indirizzi `/hotel` e `/destinations`**: la pagina li riconosce già. Serve che l'hosting rimandi tutti i percorsi a `index.html` (il file `_redirects` lo fa su Netlify e Cloudflare Pages). Su GitHub Pages funzionano solo i link con `#`.
