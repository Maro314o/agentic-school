---
name: indicizzare-pdf
description: Acquisisci localmente un libro o una singola dispensa PDF e crea o aggiorna un indice Markdown con argomenti e riferimenti di pagina. Usa per la prima importazione o per una nuova edizione, non per le domande ordinarie su PDF già indicizzati.
---

# Indicizzare un PDF scolastico

Scegli la profondità dell’indice in base a lunghezza, struttura e utilità per le ricerche, o segui la richiesta esplicita dello studente. Per file brevi può bastare l’indice della raccolta; per libri e documenti complessi crea una mappa di argomenti e pagine senza copiare il testo integrale.

## Prima acquisizione

1. **Scegli il materiale richiesto.** Prima controlla le copie locali e i relativi cataloghi e indici: se esiste il PDF pertinente, verificane fonte ed edizione e riusalo. Se manca o non è utilizzabile, cerca nelle fonti scelte dallo studente e nelle integrazioni disponibili, nel rispetto della richiesta. Solo se non riesci a trovarlo o identificarlo con certezza, spiega cosa hai controllato e chiedi all'utente un file, una fonte o un chiarimento. Se la fonte contiene una raccolta, importa solo il PDF pertinente, senza scaricarla tutta in blocco.
2. **Verifica fonte ed edizione.** Registra titolo, autori se dichiarati, edizione o versione, ISBN se presente, URL della fonte e licenza dichiarata. Conserva il PDF originale senza modificarlo.
3. **Scegli la destinazione.** Aggiorna anche l’indice della materia con il collegamento alla raccolta e una breve descrizione. Conserva i nuovi PDF nella copia del progetto, sotto `studente/materiali/<Materia>/libri/<Libro>/` per i libri e `studente/materiali/<Materia>/<Raccolta>/` per dispense e slide, con indice accanto all'originale. Non disperdere copie permanenti in cartelle globali o esterne al progetto. Riusa i PDF già disponibili nel progetto senza spostarli o sovrascriverli. Tutti i PDF sono esclusi da Git; non aggiungerli forzatamente. Conserva informazioni personali e indici che le contengono sotto `studente/`. Verifica che la destinazione privata sia ignorata da Git e non sovrascrivere edizioni o file non verificati.
4. **Esamina il PDF una volta.** Registra il numero di pagine e verifica se contiene testo estraibile. Usa `pdfinfo` e `pdftotext` quando disponibili. Se il PDF è composto da immagini, usa OCR locale se disponibile; non installare strumenti e non inviare il documento a un servizio OCR remoto senza autorizzazione dell'utente. Se l'OCR non è disponibile, comunica il limite.
5. **Mappa pagine e argomenti.** Usa segnalibri, sommario o indici affidabili per trovare gli argomenti; se mancano, crea una mappa approssimativa e dichiaralo. Per collegare pagine stampate e pagine fisiche PDF, esamina la numerazione e verifica la corrispondenza in più punti, soprattutto ai confini di sezioni e inserti: non presumere un unico offset. Se la numerazione cambia, registra una tabella con intervalli verificati, regola di conversione ed eccezioni; conserva le etichette originali, incluse numerazioni romane e pagine come `347-1`. Se serve una mappa più precisa, associa le singole etichette alle pagine fisiche, anche con estrazione automatica seguita da controlli. Segnala intervalli non verificati, ambiguità e pagine mancanti: controlli a campione non provano che un intervallo intero sia regolare. Non inventare corrispondenze; verifica nel PDF quelle necessarie per la richiesta. Salva la mappa accanto all'indice, anche in un file separato se è grande.
6. **Scrivi `Indice.md` accanto al PDF.** Includi metadati, fonte e licenza, struttura per capitoli o unità, argomenti utili e collegamenti alle pagine fisiche del PDF (per esempio `Libro.pdf#page=17`). Riporta o collega la mappa verificata fra pagine stampate e PDF. Mantieni l'indice orientato alla navigazione; non inserirvi l'estrazione testuale completa.
7. **Rispetta attribuzione e licenza.** Conserva autori, fonte, edizione e licenza. Se la licenza vieta opere derivate, limita l'indice del repository a metadati e riferimenti di navigazione; non pubblicare estratti integrali, appunti adattati o riassunti come materiale complementare.

## Cercare in un PDF già indicizzato

1. Leggi prima `Indice.md` e verifica che titolo ed edizione corrispondano al PDF.
2. Usa l'indice per restringere il capitolo. Per un termine preciso, cerca nel testo locale del PDF e conserva i numeri delle pagine trovate; non passare al modello l'estrazione integrale del libro.
3. Apri solo le pagine pertinenti. Esamina anche la pagina visivamente quando il significato dipende da diagrammi, tabelle, formule o scansioni.
4. Nella risposta indica il libro e, quando disponibili, sia la pagina stampata sia la pagina PDF. Distingui il contenuto del libro dalle informazioni che provengono dalle lezioni o da altri materiali.

## Aggiornare un indice

- Riutilizza l'indice quando il PDF è identico e della stessa edizione.
- Se cambia edizione o cambia il PDF, conserva versioni separate oppure chiedi prima di sostituire file. Ricrea e verifica la mappa: non trasferire l'offset di pagina da un'edizione all'altra.
- Dopo aver scritto l'indice, controlla che PDF e `Indice.md` esistano, verifica alcuni link rispetto alle intestazioni corrispondenti e prova una ricerca reale per confermare che testo estraibile o OCR trovino l'argomento.
