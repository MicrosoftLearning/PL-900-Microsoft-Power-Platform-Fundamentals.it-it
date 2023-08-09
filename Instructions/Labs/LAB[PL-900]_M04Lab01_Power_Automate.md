---
lab:
  title: 'Lab 4: Come creare una soluzione automatizzata'
  module: 'Module 4: Get Started with Power Automate'
---

# Lab 4: Come creare una soluzione automatizzata

**Tenant WWL - Condizioni per l'utilizzo** Se viene fornito un tenant come parte di un recapito di formazione con docente, si noti che il tenant viene reso disponibile allo scopo di supportare i lab pratici nella formazione con docente. I tenant non devono essere condivisi o usati per scopi esterni ai lab pratici. Il tenant usato in questo corso è un tenant di valutazione e non può essere usato o accessibile dopo che la classe è finita e non sono idonei per l'estensione. I tenant non devono essere convertiti in una sottoscrizione a pagamento. I tenant ottenuti come parte di questo corso rimangono la proprietà di Microsoft Corporation e ci si riserva il diritto di ottenere l'accesso e la ripossess in qualsiasi momento. 

## Scenario

Il Bellows College è un'organizzazione didattica con più edifici nel proprio campus. I visitatori del campus sono attualmente registrati su documenti cartacei. Le informazioni non vengono acquisite in modo coerente e non esiste un sistema per raccogliere e analizzare i dati sulle visite in tutto il campus.

L'amministrazione del campus vorrebbe modernizzare il proprio sistema di registrazione dei visitatori, facendo controllare l'accesso agli edifici dal personale addetto alla sicurezza e richiedendo una preregistrazione di tutte le visite da parte degli ospiti.

Durante questo corso verranno sviluppate applicazioni e si useranno le funzionalità di automazione per consentire al personale amministrativo e addetto alla sicurezza del Bellows College di gestire e controllare l'accesso agli edifici del campus.

In questo lab si creerà un flusso di Power Automate per inviare un messaggio di posta elettronica a un visitatore quando viene pianificata una visita.

## Procedura generale per il lab

Per completare il progetto sono stati identificati i requisiti seguenti:

- I contatti devono ricevere una notifica tramite posta elettronica quando viene pianificata una visita.

## Prerequisiti

- Completamento del **lab 0 del modulo 0 - Convalidare l'ambiente lab**
- Completamento del **lab 1 del modulo 2 - Modellazione dei dati**
- Completamento del **lab 3 del modulo 2 - Come creare un'app basata su modello**
- Il contatto John Doe creato con un indirizzo di posta elettronica personale popolato.

## Esercizio 1: Creare un flusso di notifica visita

**Obiettivo:** in questo esercizio verrà creato un flusso di Power Automate che implementa il requisito. Il visitatore deve ricevere un messaggio di posta elettronica con il codice univoco assegnato alla visita al momento della creazione.

### Attività \#1: Creare un flusso

1.  Accedere a <https://make.powerapps.com>. Potrebbe essere necessario ripetere l'autenticazione, selezionare **Accedi** e seguire le istruzioni, se necessario.

2.  Selezionare l'ambiente **[iniziali] Practice** in alto a destra, se non è già selezionato.

3.  Nel riquadro di spostamento a sinistra selezionare **Flussi**.

4.  Se richiesto, selezionare **Attività iniziali**.

5.  Selezionare **+ Nuovo flusso** e selezionare **Flusso cloud automatizzato**.

6.  Immettere `Visit Notification` per **Nome flusso**.

7.  In **Scegliere il trigger del flusso** cercare `Dataverse`

8.  Scegliere il trigger **Quando viene aggiunta, modificata o eliminata una riga** e quindi selezionare **Crea**.

9.  Popolare le condizioni di trigger per il flusso:

    1.  Selezionare **Aggiunte** per **Tipo di modifica**

    2.  Selezionare **Visit** per **Nome tabella**.

    3.  Selezionare **Organizzazione** per **Ambito**.

    4.  Nel passaggio del trigger selezionare i puntini di sospensione (**...**) e selezionare **Rinomina**. Rinominare il passaggio del trigger `When a Visit is added` 

        Questa è una procedura consigliata, per consentire all'utente e agli altri editor del flusso di comprendere lo scopo del passaggio senza dover esaminare i dettagli.


### Attività \#2: Creare un passaggio per ottenere la riga del visitatore

1.  Selezionare **+ nuovo passaggio**. Questo passaggio recupererà le informazioni sui visitatori, incluso l'indirizzo di posta elettronica.

2.  Cercare `Dataverse`

3.  Selezionare l'azione **Recupera una riga tramite ID**.

4.  Selezionare **Contatti** per **Nome tabella**.

5.  Selezionare il campo **ID riga**. Si noti che viene visualizzata una finestra per selezionare **Contenuto dinamico** o **Espressioni**.

6.  Nel campo **ID riga** selezionare **Visitor (Value)** nell'elenco **Contenuto dinamico** . In questo passaggio si sta cercando il contatto (Contact) per la riga Visit creata per attivare questo flusso. Poiché l'indirizzo di posta elettronica fa parte della tabella Contact, queste informazioni saranno necessarie per inviare il messaggio di posta elettronica al visitatore.

7.  Nell'azione **Ottieni una riga per ID** selezionare i puntini di sospensione (**...**) e selezionare **Rinomina**. Rinominare questa azione `Get the Visitor`
 
    Questa è una procedura consigliata, per consentire all'utente e agli altri editor del flusso di comprendere lo scopo del passaggio senza dover esaminare i dettagli.


### Attività \#3: Creare un passaggio per inviare un messaggio di posta elettronica al visitatore

1.  Selezionare **+ nuovo passaggio**. Questo è il passaggio che invierà il messaggio di posta elettronica al visitatore.

2.  `mail`Cercare , selezionare l'azione **Invia un messaggio di posta elettronica (V2)** dal **connettore Office 365 Outlook**.

3.  Se viene richiesto di accettare termini e condizioni per l'utilizzo di questa azione, selezionare **Accetta**.

4.  Selezionare **Aggiungi contenuto dinamico** nel campo **A**. 
    
5.  Selezionare **Posta elettronica** nell'elenco del contenuto dinamico.

    > Si noti che è sotto l'intestazione **Get the Visitor**. Questo significa che si sta selezionando l'indirizzo e-mail correlato al visitatore cercato nel passaggio precedente.

7.  Nel campo **Oggetto** immettere `Your scheduled visit to Bellows College`

8.  Immettere il testo seguente in **Corpo**:

    > Il contenuto dinamico deve essere inserito nei campi con nome tra parentesi graffe. È consigliabile copiare e incollare prima tutto il testo e poi aggiungere il contenuto dinamico nelle posizioni corrette.

    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    Dear {First Name},

    You are currently scheduled to visit Bellows Campus from {Scheduled Start} until {Scheduled End}.

    Best regards,

    Campus Administration
    Bellows College
    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

8.  Evidenziare il testo **{First Name}** . Sostituirlo con il campo **First Name** del passaggio **Get the Visitor** .

9.  Evidenziare il testo **{Scheduled Start}** . Sostituirlo con il campo **Scheduled Start** dal passaggio **When a visit is added**.

10.  Evidenziare il testo **{Scheduled End}** . Sostituirlo con il campo **Scheduled End** dal passaggio **When a visit is added**.

11.  Selezionare **Salva**.

Lasciare questa scheda del flusso aperta per la prossima attività. Il flusso dovrebbe essere simile al seguente:

![Esempio di passaggi del flusso.](media/4-Flow.png)


### Attività \#4: Convalidare e testare il flusso

1.  Aprire una nuova scheda nel browser e passare a <https://make.powerapps.com>.

2.  Selezionare l'ambiente **[iniziali] Practice** in alto a destra, se non è già selezionato.

3.  Selezionare **App** e aprire l'app basata sul modello **di Gestione di Bellows Campus** creata in precedenza.

3.  Lasciare aperta questa scheda del browser e tornare alla scheda precedente con il flusso.

4.  Sulla barra dei comandi selezionare **Test**. Selezionare **Manualmente** e quindi **Test**.

5.  Passare alla scheda del browser con l'app basata su modello aperta. 

6.  Usando lo spostamento della mappa della mappa a sinistra, selezionare **Visite**.

6.  Selezionare il pulsante **+ Nuovo** per aggiungere un nuovo record **Visit** .

7.  Completare il record Visit come segue:

    -   **Nome:** `Test Visit`

    -   **Visitor:** John Doe

    -   **Scheduled Start:** Domani alle 8:00

    -   **Scheduled End:** Domani alle 9:00

8.  Selezionare il pulsante **Salva & Chiudi** .

9.  Passare alla scheda del browser in cui è in esecuzione il test di Flow. Dopo un breve ritardo, dovrebbe essere visualizzato il flusso in esecuzione. Durante questa fase è possibile rilevare eventuali problemi nel flusso o verificare che venga eseguito correttamente.

    Dopo un breve ritardo, dovrebbe essere visualizzato un messaggio di posta elettronica nella posta in arrivo, dato che è stato specificato l'indirizzo di posta elettronica personale come indirizzo di posta elettronica di John Doe. Si noti che potrebbe essere inserito nella cartella Posta indesiderata.


## Sfida

- Sperimentare la formattazione nel messaggio di posta elettronica. Come si può rendere più professionale?


