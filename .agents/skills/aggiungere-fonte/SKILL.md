---
name: aggiungere-fonte
description: Configura una fonte scolastica scelta dallo studente o aggiunge una procedura per accedervi e recuperare i materiali; non usare per il setup iniziale completo.
---

# Aggiungere una fonte

1. **Individua la fonte e lo scopo.** Capisci cosa lo studente vuole consultare o importare. Controlla prima `studente/setup/fonti.md`, le procedure personali e i materiali locali: riusa ciò che è pertinente e verifica gli aggiornamenti quando la fonte cambia. Non chiedere di nuovo file già disponibili.
2. **Scegli come accedere.** Verifica gli strumenti disponibili e le guide della fonte; consulta `docs/integrazioni.md` per le opzioni consigliate. Riusa un connettore o una procedura adatti, seguendone la guida. Un file fornito direttamente può essere aggiunto senza una skill o integrazione dedicata. Se un'installazione o configurazione è esterna al progetto, spiegane il perimetro e chiedi l'autorizzazione esplicita. Non chiedere né salvare credenziali, token o password in chat o nel progetto.
3. **Registra la fonte.** In `studente/setup/fonti.md` annota nome, scopo, riferimento, eventuale procedura e stato verificato, senza segreti. Per un registro indica anche che è il registro scelto. Se un accesso non è disponibile, dichiaralo senza presentarlo come configurato. Salva i dati personali in `studente/`, verificando che sia ignorata da Git.
4. **Recupera ciò che serve.** Importa solo i materiali pertinenti alla richiesta, conservandone provenienza e versione o data quando disponibili. Aggiorna gli indici della materia e della raccolta; per libri o PDF complessi segui `indicizzare-pdf`. Non scaricare intere raccolte in anticipo né sovrascrivere dati non verificati. Rispetta le modalità di accesso e di utilizzo applicabili alla fonte.
5. **Documenta solo se serve.** Se il procedimento specifico è complesso o sarà riutilizzato e manca una guida adeguata, proponi o crea, nell'ambito della richiesta, una procedura personale breve in `studente/skills/<nome>/SKILL.md`. Descrivi quando usarla, requisiti, passaggi verificati, limiti e come cercare gli aggiornamenti; collega la procedura in `fonti.md`. Non incorporare credenziali, dati personali o ipotesi non verificate. Non creare una skill per un semplice file o duplicare la documentazione di un'integrazione. Le procedure destinate alla condivisione richiedono una revisione separata prima di entrare in `.agents/skills/`.

Se non riesci a identificare o raggiungere la fonte, spiega cosa hai già controllato e chiedi soltanto il chiarimento o il file mancante. Riepiloga ciò che è disponibile, le prove effettuate e i limiti; non dichiarare funzionante ciò che non hai verificato.
