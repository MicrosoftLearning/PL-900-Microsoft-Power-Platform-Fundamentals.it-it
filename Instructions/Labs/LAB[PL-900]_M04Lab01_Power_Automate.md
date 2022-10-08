---
lab:
  title: 'Lab 4: Come creare una soluzione automatizzata'
  module: 'Module 4: Get Started with Power Automate'
---

# <a name="lab-4-how-to-build-an-automated-solution"></a>Lab 4: Come creare una soluzione automatizzata

## <a name="scenario"></a>Scenario

Bellows College is an educational organization with multiple buildings on campus. Campus visitors are currently recorded in paper journals. The information is not captured consistently, and there are no means to collect and analyze data about the visits across the entire campus.

L'amministrazione del campus vorrebbe modernizzare il proprio sistema di registrazione dei visitatori, facendo controllare l'accesso agli edifici dal personale addetto alla sicurezza e richiedendo una preregistrazione di tutte le visite da parte degli ospiti.

Durante questo corso verranno sviluppate applicazioni e si useranno le funzionalità di automazione per consentire al personale amministrativo e addetto alla sicurezza del Bellows College di gestire e controllare l'accesso agli edifici del campus.

In questo lab si creerà un flusso di Power Automate per inviare un messaggio di posta elettronica a un visitatore quando viene pianificata una visita.

## <a name="high-level-lab-steps"></a>Procedura generale per il lab

Per completare il progetto sono stati identificati i requisiti seguenti:

- I contatti devono ricevere una notifica tramite posta elettronica quando viene pianificata una visita.

## <a name="prerequisites"></a>Prerequisiti

- Completamento del **lab 0 del modulo 0 - Convalidare l'ambiente lab**
- Completamento del **lab 1 del modulo 2 - Modellazione dei dati**
- Completamento del **lab 3 del modulo 2 - Come creare un'app basata su modello**
- Contatto John Doe creato con un indirizzo di posta elettronica personale

## <a name="exercise-1-create-visit-notification-flow"></a>Esercizio 1: Creare un flusso di notifica visita

<bpt id="p1">**</bpt>Objective:<ept id="p1">**</ept> In this exercise, you will create a Power Automate flow that implements the requirement. The visitor should be sent an email that includes the unique code assigned to the visit when a visit is created.

### <a name="task-1-create-a-flow"></a>Attività \#1: Creare un flusso

1.  Navigate to <ph id="ph1">&lt;https://make.powerapps.com&gt;</ph>. You may need to reauthenticate - click <bpt id="p1">**</bpt>Sign in<ept id="p1">**</ept> and follow instructions if needed.

2.  Selezionare l'ambiente **[iniziali] Practice** in alto a destra, se non è già selezionato.

3.  Nel riquadro di spostamento a sinistra selezionare **Flussi**.

4.  Se richiesto, selezionare **Attività iniziali**.

5.  Fare clic su **Nuovo flusso** e selezionare **Flusso cloud automatizzato**.

6.  Immettere "Visit Notification" per **Nome flusso**.

7.  In **Scegliere il trigger del flusso** cercare **Dataverse**.

8.  Selezionare il trigger **When a row is added, modified or deleted** (Quando una riga viene aggiunta, modificata o eliminata) e quindi fare clic su **Crea**.

9.  Popolare le condizioni di trigger per il flusso:

    1.  Selezionare **Aggiunte** per **Tipo di modifica**

    2.  Selezionare **Visit** per **Nome tabella**.

    3.  Selezionare **Organizzazione** per **Ambito**.

    4.  On the trigger step, click the ellipsis (<bpt id="p1">**</bpt>...<ept id="p1">**</ept>) and click <bpt id="p2">**</bpt>Rename<ept id="p2">**</ept>. Rename this trigger <bpt id="p1">**</bpt>"When a visit is added"<ept id="p1">**</ept>. This is a good practice, so you and other flow editors can understand the purpose of the step without having to dive into the details.

### <a name="task-2-create-a-step-to-get-the-visitor-row"></a>Attività \#2: Creare un passaggio per ottenere la riga del visitatore

1.  Il Bellows College è un'organizzazione didattica con più edifici nel proprio campus.

2.  Cercare **Dataverse**.

3.  Selezionare l'azione **Recupera una riga tramite ID**.

4.  Selezionare **Contatti** per **Nome tabella**.

5.  I visitatori del campus sono attualmente registrati su documenti cartacei.

6.  Le informazioni non vengono acquisite in modo coerente e non esiste un sistema per raccogliere e analizzare i dati sulle visite in tutto il campus.

7.  On this action, click the ellipsis (<bpt id="p1">**</bpt>...<ept id="p1">**</ept>) and click <bpt id="p2">**</bpt>Rename<ept id="p2">**</ept>.
        Rename this action <bpt id="p1">**</bpt>"Get the Visitor"<ept id="p1">**</ept>. This is a good practice, so you and other flow editors can understand the purpose of the step without having to dive into the details.

### <a name="task-3-create-a-step-to-send-an-email-to-the-visitor"></a>Attività \#3: Creare un passaggio per inviare un messaggio di posta elettronica al visitatore

1.  Click <bpt id="p1">**</bpt>+ New step<ept id="p1">**</ept>. This is the step that will send an email to the visitor.

2.  Cercare *mail*, selezionare il connettore **Office 365 Outlook** e l'azione **Invia un messaggio di posta elettronica (v2)** .

3.  Se viene richiesto di accettare i termini e le condizioni per usare questa azione, fare clic su **Accetta**.

4.  Selezionare **Aggiungi contenuto dinamico** nel campo **A**. 
    
5.  Selezionare **Posta elettronica** nell'elenco del contenuto dinamico.
        > Notice that it is beneath the **Get the visitor** header. This means you
        are selecting the Email that is related to the Visitor that you looked
        up in the previous step.

6.  Immettere **Your scheduled visit to Bellows College** nel campo **Oggetto**.

7.  Immettere il testo seguente in **Corpo**:

>   Dynamic content needs to be placed where fields are named in brackets. It is recommended to copy &amp; paste all text first and then add dynamic content in the correct places.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
   Dear {First Name},

   You are currently scheduled to visit Bellows Campus from {Scheduled Start} until {Scheduled End}.

   Best regards,

   Campus Administration
   Bellows College
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

8.  Highlight the <bpt id="p1">**</bpt>{First Name}<ept id="p1">**</ept> text. Replace it with the <bpt id="p1">**</bpt>First Name<ept id="p1">**</ept> field from the <bpt id="p2">**</bpt>Get the Visitor<ept id="p2">**</ept> step.

9.  Highlight the <bpt id="p1">**</bpt>{Scheduled Start}<ept id="p1">**</ept> text. Replace it with the <bpt id="p1">**</bpt>Scheduled Start<ept id="p1">**</ept> field <bpt id="p2">**</bpt>When a visit is added<ept id="p2">**</ept> step.

10.  Highlight the <bpt id="p1">**</bpt>{Scheduled End}<ept id="p1">**</ept> text. Replace it with the <bpt id="p1">**</bpt>Scheduled End<ept id="p1">**</ept> field from the <bpt id="p2">**</bpt>When a visit is added<ept id="p2">**</ept> step.

11.  Fare clic su **Salva**.

Leave this flow tab open for the next task. You flow should look approximately like the following:

![Esempio di passaggi del flusso.](media/4-Flow.png)

### <a name="task-4-validate-and-test-the-flow"></a>Attività \#4: Convalidare e testare il flusso

1.  Aprire una nuova scheda nel browser e passare a <https://make.powerapps.com>.

2.  Selezionare l'ambiente **[iniziali] Practice** in alto a destra, se non è già selezionato.

3.  Fare clic su **App** e selezionare l'app **Bellows Campus Management** basata su modello creata in precedenza.

3.  Lasciare aperta questa scheda del browser e tornare alla scheda precedente con il flusso.

4.  On the command bar, click <bpt id="p1">**</bpt>Test<ept id="p1">**</ept>. Select <bpt id="p1">**</bpt>Manually<ept id="p1">**</ept> and then click <bpt id="p2">**</bpt>Test<ept id="p2">**</ept>.

5.  Passare alla scheda del browser con l'app basata su modello aperta. 

6.  Usando la struttura di spostamento a sinistra, selezionare**Visit**.

6. Fare clic sul pulsante **+ Nuovo** per aggiungere un nuovo record **Visit**.

7. Completare il record Visit come segue:

    -   **Nome:** Test Visit

    -   **Visitor:** John Doe

    -   **Scheduled Start:** Domani alle 8:00

    -   **Scheduled End:** Domani alle 9:00

8. Selezionare il pulsante **Salva e chiudi**.

9. Navigate to the browser tab with your flow test running. After a short delay, you should see the flow running. This is where you can catch any issues in the flow or confirm that it ran successfully.

After a short delay, you should see an email in your inbox, since you populated John Doe's email as your personal email. Note that it may go to your Junk Email folder.

## <a name="challenges"></a>Problematiche

- Play around with the formatting on the email. How can you make it more professional looking?