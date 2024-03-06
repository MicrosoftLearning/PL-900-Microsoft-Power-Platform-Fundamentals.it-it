---
lab:
  title: 'Lab 4: Come creare una soluzione automatizzata'
  module: 'Module 4: Get Started with Power Automate'
---

# Lab 4: Come creare una soluzione automatizzata

**Tenant WWL: condizioni per l'utilizzo** Se, come parte della distribuzione di formazione con istruttore, viene fornito un tenant, tenere presente che il tenant viene reso disponibile allo scopo di supportare le esercitazioni pratiche nel training con docente. I tenant non devono essere condivisi o utilizzati per scopi esterni alle esercitazioni pratiche. Il tenant utilizzato in questo corso è un tenant di valutazione e non può essere utilizzato o reso accessibile dopo il termine della lezione e non è idoneo per l'estensione. I tenant non devono essere convertiti in un abbonamento a pagamento. I tenant ottenuti come parte di questo corso rimangono di proprietà di Microsoft Corporation e Microsoft si riserva il diritto di ottenere l'accesso e di riprenderne il possesso in qualsiasi momento. 

## Scenario

Bellows College è un'organizzazione educativa con più edifici nel campus. I visitatori del campus sono attualmente registrati in giornali di registrazione cartacei. Le informazioni non vengono acquisite in modo coerente e non ci sono mezzi per raccogliere e analizzare i dati sulle visite nell'intero campus.

L'amministrazione del campus vorrebbe modernizzare il proprio sistema di registrazione dei visitatori, facendo controllare l'accesso agli edifici dal personale addetto alla sicurezza e richiedendo una preregistrazione di tutte le visite da parte degli ospiti.

In questo corso verranno create applicazioni ed eseguita l'automazione per consentire al personale amministrativo e di sicurezza di Bellows College di gestire e controllare l'accesso agli edifici del campus.

In questo lab si creerà un flusso di Power Automate per inviare un messaggio di posta elettronica a un visitatore quando viene pianificata una visita.

## Procedura generale per il lab

Di seguito sono elencati i requisiti da implementare per completare il progetto:

- I contatti devono ricevere una notifica tramite posta elettronica quando viene pianificata una visita.

## Prerequisiti

- Completamento del modulo 1 Lab 0 - Convalidare l'ambiente **lab**
- Completamento del **lab 1 del modulo 2 - Modellazione dei dati**
- Completamento del **lab 3 del modulo 2 - Come creare un'app basata su modello**
- Il contatto John Doe è stato creato con un indirizzo e-mail personale.

## Esercizio 1: Creare un flusso di notifica visita

**Obiettivo:** in questo esercizio, verrà creato un flusso di Power Automate che implementa il requisito. Il visitatore deve ricevere un messaggio di posta elettronica con il codice univoco assegnato alla visita al momento della creazione.

### Attività \#1: creare un flusso

1.  Passare a `https://make.powerapps.com`

2.  Potrebbe essere necessario ripetere l'autenticazione, selezionare **Accedi** e seguire le istruzioni, se necessario.

3.  Selezionare l'ambiente **Dev One** in alto a destra, se non è già selezionato.

4.  Nel riquadro di spostamento a sinistra selezionare **Flussi**.

5.  Se richiesto, selezionare **Attività iniziali**.

6.  Selezionare **+ Nuovo flusso** e selezionare **Flusso cloud automatizzato**.

7.  Immettere `Visit Notification` per **Nome flusso**.

8.  In **Scegliere il trigger del flusso**, cercare `Dataverse`.

9.  Selezionare il trigger **Quando una riga viene aggiunta, modificata o eliminata**, quindi selezionare **Crea**.

10.  Popolare le condizioni di trigger per il flusso:

    1.  Selezionare **Aggiunte** per **Tipo di modifica**

    2.  Selezionare **Visite** per **Nome tabella**

    3.  Selezionare **Organizzazione** per **Ambito**

    4.  Nel passaggio del trigger, selezionare i puntini di sospensione (**...**), quindi selezionare **Rinomina**. Rinominare il passaggio del trigger `When a Visit is added` 

        Questa è una buona prassi, in modo che l'utente e gli altri editor di flussi possano capire lo scopo del passaggio senza dover approfondire i dettagli.


### Attività \#2: Creare un passaggio per ottenere la riga del visitatore

1.  Selezionare **+ Nuovo passaggio**. Questo passaggio recupera le informazioni sul Visitatore, compreso l'indirizzo e-mail.

2.  Cercare `Dataverse`

3.  Seleziona l'azione **Recupera una riga tramite ID**.

4.  Selezionare **Contatti** come **Nome tabella**

5.  Selezionare il campo **ID riga**. Notare che viene visualizzata una finestra per selezionare **Contenuto dinamico** o **Espressioni**.

6.  Nel campo **ID riga**, selezionare **Visitatore (valore)** dall'elenco **Contenuto dinamico**. In questo passaggio si sta cercando il contatto (Contact) per la riga Visit creata per attivare questo flusso. Poiché l'indirizzo di posta elettronica fa parte della tabella Contact, queste informazioni saranno necessarie per inviare il messaggio di posta elettronica al visitatore.

7.  Nell'azione **Ottenere una riga per ID**, selezionare i puntini di sospensione (**...**) e selezionare **Rinomina**. Rinominare questa azione `Get the Visitor`
 
    Questa è una buona prassi, in modo che l'utente e gli altri editor di flussi possano capire lo scopo del passaggio senza dover approfondire i dettagli.


### Attività \#3: Creare un passaggio per inviare un'e-mail al visitatore

1.  Selezionare **+ Nuovo passaggio**. Questo è il passaggio che invierà il messaggio di posta elettronica al visitatore.

2.  Cercare `mail`, selezionare l'azione **Invia un'e-mail (V2)** dal connettore **Office 365 Outlook**.

3.  Se viene richiesto di accettare i termini e le condizioni di utilizzo di questa azione, selezionare **Accetta**.

4.  Selezionare **Aggiungi contenuto dinamico** nel campo **A**. 
    
5.  Selezionare **Posta elettronica** nell'elenco del contenuto dinamico.

    > Notare che si trovano sotto l'intestazione **Includi visitatore**. Ciò significa che si sta selezionando l'e-mail correlata al visitatore cercato nel passaggio precedente.

7.  Nel campo **Oggetto** immettere `Your scheduled visit to Bellows College`

8.  Nel **Corpo dell'e-mail**, immettere il testo seguente:

    > Il contenuto dinamico deve essere inserito nei campi con nome tra parentesi graffe. È consigliabile copiare e incollare prima tutto il testo e poi aggiungere il contenuto dinamico nelle posizioni corrette.

    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    Dear {First Name},

    You are currently scheduled to visit Bellows Campus from {Scheduled Start} until {Scheduled End}.

    Best regards,

    Campus Administration
    Bellows College
    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

8.  Evidenziare il testo **{First Name}**. Sostituirlo con il campo **First Name** del passaggio **Get the Visitor **.

9.  Evidenziare il testo **{Scheduled Start}**. Sostituirlo con il campo **Scheduled Start** dal passaggio **When a visit is added**.

10.  Evidenziare il testo **{Scheduled End}**. Sostituirlo con il campo **Scheduled End** dal passaggio **When a visit is added**.

11.  Seleziona **Salva**.

Lasciare aperta questa scheda del flusso per l'attività successiva. Il flusso dovrebbe avere un aspetto simile al seguente:

![Example of flow steps.](media/4-Flow.png)


### Attività \#4: Convalidare e testare il flusso

1.  Aprire una nuova scheda nel browser e passare a `https://make.powerapps.com`

2.  Selezionare l'ambiente **Dev One** in alto a destra, se non è già selezionato.

3.  Selezionare **App** e aprire l'app **Bellows Campus Management** basata sul modello creata in precedenza.

3.  Lasciare aperta questa scheda del browser e tornare alla scheda precedente con il flusso.

4.  Nella barra dei comandi, selezionare **Test**. Selezionare **Manualmente**, quindi selezionare **Test**.

5.  Passare alla scheda del browser con l'app basata su modello aperta. 

6.  Usando la navigazione della mappa del sito a sinistra, selezionare **Visite**.

6.  Selezionare il pulsante **+ Nuovo** per aggiungere un nuovo record **Visita**.

7.  Completare il record Visit come segue:

    -   **Nome**: `Test Visit`

    -   **Visitatore:** John Doe

    -   **Inizio pianificato:** domani alle 8:00

    -   **Fine pianificata:** domani alle 9:00

8.  Selezionare il pulsante **Salva e chiudi**.

9.  Passare alla scheda del browser in cui è in esecuzione il test del flusso. Dopo un breve ritardo, dovrebbe essere visualizzato il flusso in esecuzione. Durante questa fase è possibile rilevare eventuali problemi nel flusso o verificare che venga eseguito correttamente.

    Dopo un breve ritardo, dovrebbe essere visualizzato un messaggio di posta elettronica nella posta in arrivo, dato che è stato specificato l'indirizzo di posta elettronica personale come indirizzo di posta elettronica di John Doe. Si noti che potrebbe essere inserito nella cartella Posta indesiderata.


## Proposta

- Sperimentare con la formattazione dell'e-mail. Come è possibile renderla più professionale?


