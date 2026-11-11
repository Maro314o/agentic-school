# Sviluppare e verificare l'agente scolastico

Questa guida riguarda chi modifica la base condivisa del progetto. Le istruzioni per l'uso scolastico e il setup sono nel README e in AGENTS.md.

## Istruzioni semplici

Mantieni poche guide e skill, con testo breve ma abbastanza preciso da permettere all'agente di svolgere i compiti previsti. Evita ripetizioni, file e rimandi non necessari; separa una procedura solo quando la distinzione facilita davvero l'uso o la manutenzione. La brevità non deve omettere informazioni necessarie né rendere ambigue le istruzioni.

## Verifica delle modifiche

Prima di considerare conclusa una modifica, verifica il comportamento interessato con scenari ripetibili e dati fittizi, inclusi i casi in cui mancano fonti o integrazioni. Quando utile, prova anche il flusso su una configurazione scolastica reale, scelta dal suo proprietario, per individuare problemi che gli esempi non mostrano.

Adatta le prove alla modifica. Per i flussi principali verifica: primo avvio e ripresa senza domande ripetute; registro assente o non configurato; ricerca locale e materiale aggiornato alla fonte; distinzione tra teoria e laboratorio; indice di una raccolta breve e pagine di un libro con numerazione irregolare. Controlla anche che dati personali e `test-path` siano ignorati da Git. Una verifica del formato delle skill non dimostra che un agente segua correttamente il flusso: prova gli scenari con un agente e documenta cosa non è stato verificato.

Il percorso della configurazione reale è facoltativo e personale. Chi sviluppa può creare nella cartella principale del progetto un file chiamato `test-path`, contenente una sola riga con il percorso assoluto della propria configurazione di prova. Il file è ignorato da Git e non è presente nelle nuove installazioni. Ogni contributore inserisce il proprio percorso; le istruzioni condivise non devono contenerlo. Se il file manca, è vuoto o il percorso non esiste, usa i test con dati fittizi e segnala che la prova sulla configurazione reale non è stata eseguita.

La configurazione reale contiene dati personali: leggili solo quanto necessario, non copiarli nei risultati condivisi e non modificarli durante i test senza richiesta o autorizzazione. Per prove che scrivono, usa dati fittizi o una copia isolata. Non pubblicare credenziali, materiali personali o risultati che li contengono.

Tieni traccia delle modifiche con commit Git: prima di un commit controlla stato e diff, verifica che i file siano destinati alla condivisione e annota gli scenari provati e gli eventuali limiti. Se esiste il file locale `.pubblicazione-locale.md`, consulta anche le preferenze di pubblicazione del proprietario.
