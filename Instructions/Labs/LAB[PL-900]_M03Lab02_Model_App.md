---
lab:
  title: 'Lab 3: Come creare un''app basata su modello'
  module: 'Module 3: Get started with Power Apps'
---

# Lab 3: Come creare un'app basata su modello

**Tenant WWL - Condizioni per l'utilizzo** Se viene fornito un tenant come parte di un recapito di formazione con docente, si noti che il tenant viene reso disponibile allo scopo di supportare i lab pratici nella formazione con docente. I tenant non devono essere condivisi o usati per scopi esterni ai lab pratici. Il tenant usato in questo corso è un tenant di valutazione e non può essere usato o accessibile dopo che la classe è finita e non sono idonei per l'estensione. I tenant non devono essere convertiti in una sottoscrizione a pagamento. I tenant ottenuti come parte di questo corso rimangono la proprietà di Microsoft Corporation e ci si riserva il diritto di ottenere l'accesso e la ripossess in qualsiasi momento. 

## Scenario

Il Bellows College è un'organizzazione didattica con più edifici nel proprio campus. I visitatori del campus sono attualmente registrati su documenti cartacei. Le informazioni non vengono acquisite in modo coerente e non esiste un sistema per raccogliere e analizzare i dati sulle visite in tutto il campus.

L'amministrazione del campus vorrebbe modernizzare il proprio sistema di registrazione dei visitatori, facendo controllare l'accesso agli edifici dal personale addetto alla sicurezza e richiedendo una preregistrazione di tutte le visite da parte degli ospiti.

Durante questo corso verranno sviluppate applicazioni e si useranno le funzionalità di automazione per consentire al personale amministrativo e addetto alla sicurezza del Bellows College di gestire e controllare l'accesso agli edifici del campus.

In questo lab verrà creata un'app basata su modello di Power Apps per consentire al personale di back office del campus di gestire i record delle visite per l'intero campus.

Procedura generale per il lab

Nell'ambito della creazione dell'app basata su modello verranno eseguite le operazioni seguenti:

- Creare una nuova app basata su modello denominata Bellows Campus Management

- Modificare la struttura di spostamento dell'app per fare riferimento alle tabelle richieste

- Personalizzare i moduli e le visualizzazioni delle tabelle richieste per l'app

Verranno usati i componenti seguenti:

- **Visualizzazioni**: le visualizzazioni consentono all'utente di visualizzare i dati esistenti nelle tabelle dei moduli.

- **Moduli**: in questi componenti l'utente crea nuove righe o aggiorna le righe esistenti nelle tabelle.

Entrambi questi componenti verranno integrati nell'app basata su modello per una migliore esperienza utente.

Prerequisiti

- Completamento del **lab 0 del modulo 0 - Convalidare l'ambiente lab**

- Completamento del **lab 1 del modulo 2 - Modellazione dei dati**

Aspetti da considerare prima di iniziare

- Quali modifiche dobbiamo apportare per migliorare l'esperienza utente?

- Cosa dobbiamo includere in un'app basata su modello basata sul modello di dati creato?

- Quali personalizzazioni possono essere effettuate nella mappa del sito di un'app basata su modello?

Esercizio 1: Personalizzare visualizzazioni e moduli

**Obiettivo:** in questo esercizio verranno personalizzati i moduli e le visualizzazioni delle tabelle personalizzate create che verranno usati nell'app basata su modello.

Attività 1: Modificare il modulo delle visite

1.  Accedere a <https://make.powerapps.com> se l'accesso non è già stato effettuato.

2.  Selezionare l'ambiente **[iniziali] Practice** in alto a destra, se non è già selezionato.

3.  Usando il riquadro di spostamento a sinistra, selezionare **Tabelle** e aprire la tabella **Visit** .

    Se la tabella Visit non viene visualizzata, assicurarsi di essere nell'ambiente corretto (passaggio 2).

4.  Nella sezione **Esperienze dati** selezionare **Moduli** e aprire il modulo **Informazioni** con tipo di modulo **principale** . **Importante:** assicurarsi di selezionare il modulo con il tipo di modulo **Main**. 

    **IMPORTANTE:** dato che tutti i moduli hanno il nome Information per impostazione predefinita, verificare che il modulo selezionato abbia il tipo di modulo **Main** e non un altro. Per impostazione predefinita, il modulo include due campi: Nome e Proprietario.

5.  Sul lato destro della schermata nel pannello **Proprietà** selezionare il campo **Nome visualizzato** e modificarlo in `Main Information`

6.  Selezionare **Colonne tabella** nel riquadro di spostamento a sinistra e aggiungere i campi seguenti sotto il campo **Proprietario** trascinando le colonne nel modulo o semplicemente facendo clic sui nomi delle colonne:

    1. **Visitatore**

    2. **Start pianificato**

    3. **Scheduled End**

    4. **Actual Start**

    5. **Actual End**

7.  Trascinare la colonna **Code** nell'intestazione del modulo.

    L'area dell'intestazione è quella in alto a destra nel modulo. Potrebbe essere necessario comprimere il pannello Proprietà sul lato destro della schermata per visualizzare il campo nel modulo.

8.  Con il campo **Code** ancora selezionato, selezionare la casella di controllo **Sola lettura** nel pannello Proprietà sul lato destro della schermata.

9.  Selezionare il campo **Proprietario**. Nel pannello Proprietà modificare **l'etichetta** in `Host`

10. Selezionare il pulsante **Salva e pubblica** in alto a destra e attendere il completamento del salvataggio e della pubblicazione.

11. Se la visualizzazione Modifica è aperta in una nuova scheda o finestra del browser, chiuderla. In caso contrario, selezionare **🡠 Indietro** nella parte superiore sinistra della schermata. A questo momento si tornerà ai moduli della tabella **Visit** .

12. Utilizzo delle barre di navigazione in alto a sinistra (**tabelle** > **visita** > **moduli**). Selezionare **Visita** per tornare alla schermata **Visita** proprietà tabella. 


Attività 2. Modificare la visualizzazione Visit attivi/e

In questa attività verrà modificata la visualizzazione predefinita Visit attivi/e e si creerà una nuova visualizzazione per le visite del giorno.

1.  Nella sezione **Esperienze dati** selezionare **Visualizzazioni** e aprire la visualizzazione **Visite attive** .

2.  Aggiungere i campi seguenti alla visualizzazione facendo clic sui campi o trascinandoli:

    1. **Codice**

    2. **Visitatore**

    3. **Start pianificato**

    4. **Scheduled End**

3.  Selezionare il menu a discesa nella colonna **Creato** in e selezionare **Rimuovi**. Il campo **Creato su** verrà ora rimosso dalla visualizzazione.

4.  Ridimensionare la larghezza delle singole colonne in base alle esigenze per adattare i dati.

5.  In **Ordina per ...** selezionare la X per rimuovere **Il nome** e selezionare **Invece Inizio pianificato**.

6.  Selezionare **Inizio pianificato** per modificare l'ordinamento in **Più recente.**

7.  Selezionare il pulsante **Salva e pubblica** in alto a destra e attendere il completamento della pubblicazione.


Attività 3: Creare una nuova visualizzazione per le visite del giorno

Vedremo ora come clonare la visualizzazione per creare una nuova visualizzazione per le visite del giorno.

IMPORTANTE: assicurarsi di non chiudere la visualizzazione Visit attivi/e, perché verrà sfruttata per creare la visualizzazione delle visite di oggi.

1.  Selezionare **Salva con nome**.

2.  Modificare il **nome** `Today’s Visits` in e selezionare **Salva**.

3.  Selezionare **Modifica filtri** nel pannello Proprietà.

4.  Selezionare **+ Aggiungi**, selezionare **Aggiungi riga**.

5.  Selezionare **Inizio pianificato** come campo, quindi impostare **Uguale** a **Oggi** come condizione nell'elenco a discesa.

6.  Selezionare il **...** **Altri comandi** nella riga **Stato** e selezionare **Elimina** per eliminare tale condizione di filtro.

7.  Selezionare **Ok** per salvare la condizione. La visualizzazione è ora filtrata per visualizzare solo i record in cui la data di **inizio pianificata** è oggi.

8.  Aggiungere i campi **Actual Start** e **Actual End** alla visualizzazione.

    **Nota:** dato che i dati non sono più filtrati in base allo stato, otterremo un elenco delle visite del giorno che include anche quelle completate. Questi campi serviranno a distinguere le visite completate da quelle in corso.

9.  Selezionare il pulsante **Salva e pubblica** in alto a destra e attendere il completamento della pubblicazione.


Esercizio 2: Creare un'app basata su modello

**Obiettivo:** in questo esercizio si creerà un'app basata su modello, si personalizzerà la mappa del sito e quindi si testerà l'app.

Per semplicità e per ragioni di tempo, non verranno usate alcune delle colonne Visit in questo lab.

Attività n. 1: Creare un'app

1.  Accedere a <https://make.powerapps.com>, se non si è già connessi.

2.  Selezionare l'ambiente **[iniziali] Practice** in alto a destra, se non è già selezionato.

3.  Selezionare **+ Crea** nel riquadro di spostamento a sinistra.

4.  Creare l'applicazione basata su modello:

    1. Selezionare **App vuota** nella sezione **Inizia dalla** schermata **Crea l'app** .

    2. In **App vuota basata su Dataverse** selezionare **Crea**.

    3. Immettere `Bellows Campus Management` per **Nome** e selezionare **Crea**.

5.  Dopo il caricamento della nuova applicazione basata su modello, selezionare il pulsante **+ Aggiungi pagina**.

6.  Nella schermata **Aggiungi pagina** scegliere **Tabella Dataverse** e quindi selezionare il pulsante **Avanti** .

7.  Selezionare le tabelle seguenti:

    1. Visitare

    2. Contatto

8.  Dopo aver creato entrambe le tabelle, selezionare **Aggiungi**.

9.  Usando le icone di spostamento su lato sinistro della schermata, selezionare **Spostamento**.

10. Nel riquadro di spostamento selezionare **Nuovo gruppo** sotto dove è indicato Spostamento. Potrebbe essere necessario espandere il menu a sinistra.

11. Sul lato destro della schermata, nella sezione **Opzioni di visualizzazione** modificare la proprietà **Title** in `Security`

12. Selezionare**Salva** e attendere che le modifiche vengano salvate.

13. Al termine del **salvataggio** selezionare il pulsante **Pubblica** per pubblicare le modifiche.


Attività n. 2: Testare l'app

Avviare l'applicazione

1. Selezionare il pulsante **Riproduci** , l'app basata su modello verrà caricata in una nuova scheda.

Creare un nuovo contatto

2.  L'app verrà aperta nella visualizzazione **Contatti attivi**. In caso contrario, selezionare **Contatti** nel riquadro di spostamento a sinistra.

3.  Selezionare **+ Nuovo** dalla barra dei comandi.

4.  Immettere **First Name (Nome**) e **Last Name (Cognome**) come `John``Doe`

5.  Specificare l'indirizzo e-mail personale per **E-mail**. Verrà usato in un lab futuro, in cui si riceverà un messaggio di posta elettronica.

6.  Selezionare **Salva e chiudi**.

7.  Il nuovo contatto creato dovrebbe essere ora visibile nella visualizzazione **Contatti attivi personali**.

Creare una nuova visita

8.  Selezionare **Visite** nel riquadro di spostamento a sinistra (noto anche come mappa del sito).

9.  Selezionare **+ Nuovo**.

10. Compilare i campi come indicato di seguito:

    1. **Nome**: `New test visit`

    2. **Visitatore**: **selezionare John Doe**

    3. **Inizio pianificato**: selezionare la data di domani e le 2:00 pm come ora di inizio

    4. **Fine pianificata**: selezionare la data di domani e le 13:30 come ora di fine

11. Selezionare **Salva e chiudi**. Verrà creata la Visita e si dovrebbe essere in grado di vederla nella visualizzazione **Visite attive** .

12. Passare alla visualizzazione **Visite di oggi usando l'elenco** a discesa accanto a **Visite attive**. La nuova visita non dovrebbe essere più visibile in questa visualizzazione, perché è pianificata per il giorno successivo.

13. È possibile aggiungere altri record di test.

L'app basata su modello in esecuzione dovrebbe essere simile alla seguente:

![](media/3-model-driven-app.png)

Congratulazioni! È stata creata e configurata la prima app basata su modello.

## Problematiche

- Selezionare visualizzazioni e moduli specifici per Contatti.

