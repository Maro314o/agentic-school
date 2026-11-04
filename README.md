# Agente scolastico

Questa guida è per le persone. Se sei un agente, leggi prima [AGENTS.md](AGENTS.md).

Questo progetto raccoglie istruzioni e procedure per un assistente personale della vita scolastica, utilizzabili con agenti diversi. I dati dello studente e i PDF personali restano locali.

## Installazione e primo avvio

1. Installa Git e un agente capace di leggere file locali; ottieni una copia del progetto e apri la sua cartella nell'agente. Per Codex, apri la cartella nell'app o avvia Codex dalla cartella.
2. L'agente parte da [AGENTS.md](AGENTS.md) e legge le guide e procedure pertinenti alla richiesta. Alcuni agenti caricano automaticamente le istruzioni; negli altri indica esplicitamente `AGENTS.md` nella prima richiesta. Non si presume che tutti gli agenti supportino lo stesso formato di skill o MCP.
3. Alla prima richiesta controlla lo stato in `studente/setup/stato.json` e segue [setup-studente](.agents/skills/setup-studente/SKILL.md). Raccoglie subito solo i dati necessari alla richiesta; i passi facoltativi possono essere ripresi o saltati. Il setup non parte semplicemente aprendo la cartella.
4. Scegli il registro e verifica che l'agente supporti l'integrazione. Puoi configurarlo più tardi. Consulta le [integrazioni consigliate](docs/integrazioni.md); non inserire credenziali in chat.

Profilo, stato, orario e fonti personali sono in `studente/`, esclusa da Git. `studente/setup/fonti.md` identifica le fonti adottate dallo studente e le eventuali procedure personali. `complete` nello stato indica soltanto che i passi sono stati completati o saltati: orario e integrazioni vanno verificati quando servono, anche al cambio d'anno.

Le skill condivise risiedono in `.agents/skills/`; le procedure personali in `studente/skills/` restano locali. Se non vengono caricate automaticamente, l’agente legge il relativo `SKILL.md`. I PDF acquisiti restano nel progetto, normalmente sotto `studente/`. Gli strumenti già installati nell'ambiente possono essere usati senza modificarli; non installare skill del progetto globalmente. Alcune integrazioni possono richiedere configurazione esterna: in tal caso l'agente deve indicarne il perimetro e ottenere un'autorizzazione esplicita.

Puoi chiedere di aggiornare l'orario, aggiungere una fonte o rifare il setup. Per indicizzare un libro o PDF lungo usa [indicizzare-pdf](.agents/skills/indicizzare-pdf/SKILL.md). I PDF sono personali e restano fuori da Git; nuovi originali e indici personali vanno sotto `studente/`. Per estrazione e verifica sono utili `pdfinfo` e `pdftotext` (Poppler); per scansioni può servire OCR locale. Se questi strumenti mancano, l'agente segnala i limiti e non invia documenti a servizi esterni senza autorizzazione.

## Cosa fa l'agente

Con un registro collegato può consultare le informazioni disponibili, come agenda, lezioni e assenze. Su richiesta può ricostruire una giornata persa usando le lezioni e i materiali disponibili, oppure aiutare a svolgere un compito spiegando i passaggi.

## Teoria e laboratorio

Le lezioni di teoria e quelle di laboratorio sono ambiti distinti, anche quando hanno lo stesso nome di materia: possono trattare contenuti e compiti diversi. Per identificare il contesto di una lezione o di una consegna, l'agente deve consultare l'orario del giorno e della fascia oraria pertinente; non deve dedurlo dal solo nome della materia. Deve mantenere separati materiali, appunti e compiti dei due ambiti. Se l'orario non è disponibile o non chiarisce il contesto, deve chiedere una precisazione invece di unire o classificare i dati per supposizione.

Il setup iniziale raccoglie l'orario e le informazioni sulla classe o sul gruppo necessarie a distinguere teoria e laboratorio. La classificazione segue le indicazioni dell'orario; se questo non chiarisce il contesto, l'agente chiede una precisazione.

I materiali personali sono organizzati per materia sotto `studente/materiali/`. Un indice della materia rimanda alle raccolte; libri e raccolte possono avere indici più dettagliati accanto ai file. I materiali già presenti sono riutilizzati senza spostarli automaticamente.

La disponibilità di Teams, OneDrive, Outlook e altre integrazioni dipende dall'ambiente: l'agente la verifica prima dell'uso.

## Struttura

```text
AGENTS.md
README.md
.agents/
  skills/
    setup-studente/
      SKILL.md
    indicizzare-pdf/
      SKILL.md
    aggiungere-fonte/
      SKILL.md
studente/                  # locale, esclusa da Git
  setup/                       # profilo, stato e fonti dello studente
  orario-<classe>/             # orario e fonte
  materiali/<Materia>/         # raccolte e indici personali
  skills/                      # procedure personali facoltative
```

Le procedure comuni sono [`setup-studente`](.agents/skills/setup-studente/SKILL.md) per la configurazione iniziale, [`aggiungere-fonte`](.agents/skills/aggiungere-fonte/SKILL.md) per configurare una fonte e [`indicizzare-pdf`](.agents/skills/indicizzare-pdf/SKILL.md) per indicizzare un PDF quando serve.

## Integrazioni

L'elenco delle [integrazioni consigliate](docs/integrazioni.md) comprende ClasseViva e Teams. Disponibilità e configurazione dipendono dall'agente e dall'integrazione scelta.

## Fonti e dati

L'agente deve distinguere ciò che risulta dal registro o da un materiale del professore da ciò che ricostruisce dal libro. Quando risponde su una lezione o su un libro, indica la fonte e, se disponibile, la pagina. Se un'integrazione non è collegata o una fonte manca, lo dice invece di completare i vuoti con supposizioni.

Non aggiungere al repository credenziali, dati personali dello studente o materiali scolastici privati. I materiali pubblici o forniti per l'uso scolastico devono mantenere attribuzione, versione e licenza. Le credenziali locali e le cartelle di dati privati sono escluse da Git tramite `.gitignore`.

## PDF e storia Git

I PDF restano locali e sono ignorati da Git. Se erano già stati committati, `.gitignore` non li rimuove dalla storia: prima di pubblicare occorre preparare e verificare una storia priva dei PDF, preservando gli originali locali.
