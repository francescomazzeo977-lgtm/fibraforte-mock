# fibraforte-mock

Simulazione, **solo per test**, del servizio esterno "Fibraforte" che indica se un numero è in SPAM.
Non è il servizio reale e non è affiliato ad esso. Serve a provare una Data Action di Genesys Cloud
che legge lo stato dei numeri (in sostituzione di una tabella dati).

## Endpoint (GitHub Pages, HTTPS)

`GET https://francescomazzeo977-lgtm.github.io/fibraforte-mock/api/numeri.json`

```json
{
  "fonte": "Fibraforte (simulazione per test)",
  "numeri": [
    { "numero": "+390289784197", "stato": "SPAM" },
    { "numero": "+390289784198", "stato": "OK" },
    { "numero": "+390289784199", "stato": "OK" }
  ]
}
```

- L'ordine dell'elenco è l'ordine di preferenza: chi legge sceglie il primo numero con `stato` diverso da `SPAM`.
- Valori di `stato` usati: `OK`, `SPAM`.
- La pagina `index.html` mostra gli stessi dati in una tabella.

## Cambiare lo stato di un numero

Modificare `api/numeri.json` e fare commit su `main`: GitHub Pages ripubblica in circa un minuto.
La cache può mantenere la versione precedente per alcuni minuti.

## Note

- Nessuna autenticazione: il repository è pubblico, contiene solo dati di prova.
- `robots.txt` e `noindex` chiedono ai motori di ricerca di non indicizzare il sito.
