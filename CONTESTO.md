# Contesto: AeonsEnd_APP

Web app mobile-first (HTML/CSS/JS puro, senza backend), pubblicata su GitHub Pages: https://lorenzvittori.github.io/AeonsEnd_APP/

Serve da **companion digitale per il gioco da tavolo cooperativo *Aeon's End***. Gestisce il **mazzo nemesi** al posto delle carte fisiche, così i giocatori si concentrano sulla partita. L'interfaccia è in italiano.

## Come funziona

- **Setup della partita**: nella pagina iniziale si scelgono numero di giocatori (2–4), nemesi (Carapace Queen, Maggoth, Fenrix, Ageless Walker, Arachnos/World Devourer, ecc.) e numero della battaglia.
- **Costruzione del mazzo**: l'app usa `deck-setup.json` per estrarre a caso, per ogni Tier (1–3), il numero giusto di carte *Basic Nemesis* e *Upgraded Basic Nemesis*, in base a battaglia e numero di giocatori. Poi aggiunge le carte specifiche del nemico e mescola. Le immagini delle carte stanno in `Data/`, i dati in `cards.json` e `nemesis.json`.
- **Turno nemesi**: pesca e risolve le carte. Ci sono tre viste:
  - `VistaCoda`: turno dei giocatori.
  - `VistaRisoluzione`: turno del nemesi.
  - `VistaCartaCoda`: carta vista in grande.

## Tipi di carta

- **Poteri**: hanno un counter di token. Si pagano nel turno dei giocatori ("Rimuovi") oppure si risolvono a 0 token.
- **Minion**: hanno vita (gocce da 5 e da 1) e si possono danneggiare o uccidere.
- **Attacchi**: sono da risolvere subito ("Risolto").

## Altre funzioni

- **Scarto automatico**: le carte risolte, pagate o morte escono dalla coda e vanno nella pila "Scarti", consultabile.
- Counter dei turni nemesi.
- "Undo" illimitato fino all'inizio della partita.
- Salvataggio automatico nel browser, con "Riprendi partita".

## Da fare (da `TODO.md`)

- Segnare quali boss interagiscono con il mazzo nemesi.
- Aggiungere vita nemesi e vita città (servono i valori iniziali).
- Dubbi aperti: carte che guardano o mischiano il mazzo nemesi; interazioni che aggiungono o tolgono carte dal mazzo.

## Note di lavoro

- C'è un prototipo di nuovo design in una cartella separata (`new_design_0.2`), che condivide dati e immagini con l'app principale.
- Ogni richiesta comporta un bump di `version.json`, un commit e un push.
