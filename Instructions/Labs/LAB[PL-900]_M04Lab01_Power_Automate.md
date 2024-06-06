---
lab:
  title: 'Lab 4: Come creare una soluzione automatizzata'
  module: 'Module 4: Describe building automation with Microsoft Power Automate'
---

# Lab 4: Come creare una soluzione automatizzata

**Tenant WWL: condizioni per l'utilizzo** Se, come parte della distribuzione di formazione con istruttore, viene fornito un tenant, tenere presente che il tenant viene reso disponibile allo scopo di supportare le esercitazioni pratiche nel training con docente. I tenant non devono essere condivisi o utilizzati per scopi esterni alle esercitazioni pratiche. Il tenant usato in questo corso è un tenant di valutazione e non può essere usato o risultare accessibile dopo che la lezione è finita e non è idonea per l'estensione. I tenant non devono essere convertiti in un abbonamento a pagamento. I tenant ottenuti come parte di questo corso rimangono di proprietà di Microsoft Corporation e Microsoft si riserva il diritto di ottenere l'accesso e di riprenderne il possesso in qualsiasi momento. 

## Scenario

Il Bellows College è un'organizzazione educativa con più campus e programmi. Molti insegnanti e amministratori del Bellow College devono partecipare agli eventi e acquistare articoli. Storicamente, tenere traccia di queste spese è stata una sfida. 

L'amministrazione del campus vuole modernizzare il sistema di gestione delle spese fornendo ai dipendenti un modo digitale per segnalare le spese. 

In questo corso si creeranno delle applicazioni e si eseguirà l'automazione per consentire ai dipendenti del Bellows College di gestire le spese. 

In questo lab si creerà un flusso di Power Automate per inviare una copia della nota spese ogni volta che ne viene creata una.

## Procedura generale per il lab

Di seguito sono elencati i requisiti da implementare per completare il progetto:

- I dipendenti devono ricevere un’e-mail quando viene inviata una nota spese. 

### Prerequisiti

- Completamento del **Modulo 1 Lab 0 - Convalidare l'ambiente lab**

## Esercizio 1: Creare il flusso di notifica delle note spese

**Obiettivo:** in questo esercizio, verrà creato un flusso di Power Automate che implementa il requisito. 

### Attività 1: Creare un flusso

1. Passare a https://make.powerapps.com

1. Potrebbe essere necessario ripetere l'autenticazione. Selezionare **Accedi** e seguire le istruzioni, se richiesto.

1. Selezionare l'ambiente **Dev One** in alto a destra, se non è già selezionato.

1. Nel riquadro di spostamento a sinistra selezionare **Flussi**.

1. Se richiesto, selezionare **Attività iniziali**.

1. Selezionare **+ Nuovo flusso** e selezionare **Flusso cloud automatizzato**.

1. Immettere Nota spese per **Nome flusso**.

1. In **Scegliere il trigger del flusso** cercare Dataverse

1. Selezionare il trigger **When a row is added, modified or deleted** (Quando una riga viene aggiunta, modificata o eliminata) e quindi selezionare **Crea**.

1. Popolare le condizioni di trigger per il flusso:

    1. Selezionare **Aggiunte** per **Tipo di modifica**
    
    1. Selezionare **Nota spese** per **Nome tabella**

    1. Selezionare **Organizzazione** per **Ambito**

    1. Nel passaggio del trigger, selezionare i puntini di sospensione (**...**), quindi selezionare **Rinomina**. Rinominare il passaggio del trigger `When an Expense Report is added` 

Questa è una procedura consigliata, per consentire all'utente e agli altri editor del flusso di comprendere lo scopo del passaggio senza dover esaminare i dettagli.

### Attività 2. Creare un passaggio per ottenere la riga Nota spese

1. Selezionare **+ Nuovo passaggio**. Questo passaggio recupererà le informazioni della Nota spese, incluso l'indirizzo e-mail.

1. Cercare Dataverse

1. Seleziona l'azione **Recupera una riga tramite ID**.

1. Selezionare **Utenti** come **Nome tabella**

1. Selezionare il campo **ID riga**. Notare che viene visualizzata una finestra per selezionare **Contenuto dinamico** o **Espressioni**.

1. Nel campo **ID riga** selezionare **Proprietario (Valore)** nell'elenco **Contenuto dinamico**. In questo passaggio si sta cercando il Proprietario per la riga Nota spese creata per attivare questo flusso. 

1. Nell'azione **Ottenere una riga per ID**, selezionare i puntini di sospensione (**...**) e selezionare **Rinomina**. Rinominare l'azione Recupera il visitatore

Questa è una procedura consigliata, per consentire all'utente e agli altri editor del flusso di comprendere lo scopo del passaggio senza dover esaminare i dettagli.

### Attività 3: Creare un passaggio per inviare un’e-mail a conferma dell'invio di una nota spese

1. Selezionare **+ Nuovo passaggio**. Questo è il passaggio che invierà un’e-mail all'utente che ha presentato la nota spese.

1. Cercare la posta elettronica e selezionare l'azione **Invia un messaggio di posta elettronica (v2)** dal connettore **Office 365 Outlook**.

1. Se viene richiesto di accettare i termini e le condizioni di utilizzo di questa azione, selezionare **Accetta**.

1. Selezionare il campo **A** e immettere l'indirizzo di posta elettronica personale. (Esistono molti modi per popolare dinamicamente un indirizzo di posta elettronica, ma per questo esercizio verrà assegnato manualmente.)  

1. Nel campo **Oggetto** immettere La nota spese è stata inviata

1. Nel **Corpo dell'e-mail**, immettere il testo seguente:

Il contenuto dinamico deve essere inserito nei campi con nome tra parentesi graffe. È consigliabile copiare e incollare prima tutto il testo e poi aggiungere il contenuto dinamico nelle posizioni corrette.

    Dear {First Name},
    
    Thank you for submitting your expense report for the total amount of {Report Total Amount} with a due date of {Report Due Date}.
    
     
    Best regards,
    Campus Administration
    Bellows College

1. Evidenziare il testo **{First Name}**. Sostituirlo con il campo **Nome** del passaggio **Recupera il visitatore**.

1. Evidenziare il testo **{Report Total Amount}**. Sostituirlo con il campo **Importo totale report** del passaggio **Quando viene inviata una nota spese**.

1. Evidenziare il testo **{Report Due Date}**. Sostituirlo con il campo **Scadenza del report** del passaggio **Quando viene inviata una nota spese**.

1. Seleziona **Salva**.

Lasciare aperta questa scheda del flusso per l'attività successiva. Il flusso sarà simile al seguente:

![Screenshot del flusso appena creato](media/lab-4-create-an-automated-solution-01.png)

### Attività 4 Convalidare e testare il flusso

1. Aprire una nuova scheda nel browser e passare a https://make.powerapps.com

1. Selezionare l'ambiente **Dev One** in alto a destra, se non è già selezionato.

1. Selezionare **App** e aprire l'**app di monitoraggio delle spese**.

1. Lasciare aperta questa scheda del browser e tornare alla scheda precedente con il flusso.

1. Nella barra dei comandi, selezionare **Test**. Selezionare **Manualmente**, quindi selezionare **Test**.

1. Passare alla scheda del browser con l'app basata su modello aperta.

1. Usando la navigazione del sito sulla sinistra, selezionare **Nota spese**.

1. Selezionare il pulsante **+ Nuovo** per aggiungere una nuova riga **Nota spese**.

1. Completare la **riga della nota spese** come indicato di seguito:

    - **Nome report:** Report test

    - **Scadenza report:** Domani 

1. Selezionare il pulsante **Salva e chiudi**.

1. Passare alla scheda del browser in cui è in esecuzione il test del flusso. Dopo un breve ritardo, dovrebbe essere visualizzato il flusso in esecuzione. Durante questa fase è possibile rilevare eventuali problemi nel flusso o verificare che venga eseguito correttamente.

Dopo un breve ritardo, si dovrebbe ricevere un’e-mail nella casella di posta elettronica. 

>**Nota:** Potrebbe essere inserita nella cartella Posta indesiderata.
