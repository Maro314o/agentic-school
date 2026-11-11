---
name: setup-studente
description: Avvia o riprende la configurazione scolastica locale dello studente. Per aggiornare solo un orario o aggiungere una fonte, gestisci direttamente la richiesta.
---

# Setup dello studente

Alla prima richiesta nel progetto o su richiesta di rifare il setup, controlla i dati esistenti prima di fare domande. Spiega brevemente che si possono configurare scuola, classe, anno scolastico, registro, orario, libri, altre fonti e, facoltativamente, la stampa: consiglia profilo, registro e orario; gli altri passi sono facoltativi e riprendibili. Raccogli solo ciò che serve alla richiesta corrente e rispondi appena possibile, senza ripetere dati già forniti. Aprire la cartella non avvia il setup.

Salva i dati personali solo in `studente/`, dopo aver verificato che sia ignorata da Git. Se esiste la vecchia configurazione `private-data/`, riusala senza spostarla o sovrascriverla automaticamente e concorda la migrazione. Non chiedere né salvare credenziali, token o password in chat o nel progetto.

## Stato e dati

Usa `studente/setup/profilo.md` per il profilo minimo, `studente/setup/fonti.md` per registro, fonti e relative procedure, e `studente/orario-<classe>/` per orario e fonte. In `studente/setup/stato.json` usa lo schema esistente:

```json
{
  "schema_version": 1,
  "stato": "in_progress",
  "anno_scolastico": null,
  "passi": {
    "profilo": "pending",
    "orario": "pending",
    "integrazioni": "pending",
    "fonti": "pending"
  }
}
```

Registra l'anno solo se indicato o confermato. I passi possono essere `pending`, `complete` o `skipped`; lo stato globale è `complete` quando nessuno è `pending`. Salva le informazioni e lo stato dopo ogni passo. Se lo stato è completo non ripetere il setup; se è in corso riprendi ciò che serve. Se non è leggibile o ha una versione sconosciuta, non sovrascriverlo. Per `fonti`, `complete` significa che lo studente ha concluso per ora la scelta delle altre fonti, non che tutti i libri siano stati aggiunti: potrà aggiungerne altri. Registrare il solo registro non completa automaticamente questo passo. Un passo completato non garantisce che i dati o gli strumenti siano ancora validi.

## Procedura

1. **Contesto.** Riusa profilo, orario e fonti già disponibili verificandone studente, classe, anno, origine e validità. Proponi di registrare scuola, classe e anno scolastico: aiutano a identificare il contesto e le fonti corrette. Chiedi anche indirizzo o gruppo se utile; se lo studente preferisce può rimandare questi dati. Non applicare un orario a date fuori dalla sua validità.
2. **Registro.** Chiedi quale usa e consiglia di collegarlo, lasciando la scelta di rimandare. Verifica gli strumenti disponibili e segui la guida dell'integrazione scelta; vedi `docs/integrazioni.md`. Registra nome e riferimento alla procedura in `fonti.md`, distinguendo disponibile da non configurato. Se non è disponibile non dichiarare di averlo consultato.
3. **Orario.** Proponi file, URL o registro disponibile, oppure la possibilità di rimandare. Verifica classe, anno, validità e versione; se ci sono ambiguità chiedi prima di scegliere. Conserva fonte e orario Markdown con giorni, fasce, materie e docenti disponibili, includendo compresenze e assegnazioni solo se indicate o verificabili. Distingui teoria e laboratorio solo quando sono confermati; segnala abbinamenti o ambiti dedotti senza presentarli come certezze. Non segnare come acquisito un orario non verificato.
4. **Altre fonti.** Libri, slide e piattaforme possono essere aggiunti subito o più avanti. Registra ciò che lo studente indica, con materia, ambito se noto e percorso o riferimento. Se serve configurare una fonte, segui `aggiungere-fonte`; non scaricare raccolte intere.
5. **Riepilogo.** Indica ciò che è stato configurato, ciò che resta da fare e gli eventuali limiti, poi prosegui con la richiesta originale. Usa `skipped` solo se l'utente sceglie di saltare; una fonte non disponibile non equivale a configurata.

Se lo studente chiede di aggiornare l’orario, modifica solo i dati pertinenti; per aggiungere una fonte segui `aggiungere-fonte`; se chiede di rifare il setup, riusa ciò che è valido. Sono richieste in linguaggio naturale, non comandi obbligatori. Non cancellare o sovrascrivere dati esistenti senza chiarire come conservarli.
