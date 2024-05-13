---
lab:
  title: 'Lab 3: Come creare un''app basata su modello'
  module: 'Module 3: Get started with Power Apps'
---

# Lab 3: Come creare un'app basata su modello

**Tenant WWL: condizioni per l'utilizzo** Se, come parte della distribuzione di formazione con istruttore, viene fornito un tenant, tenere presente che il tenant viene reso disponibile allo scopo di supportare le esercitazioni pratiche nel training con docente. I tenant non devono essere condivisi o utilizzati per scopi esterni alle esercitazioni pratiche. Il tenant usato in questo corso è un tenant di valutazione e non può essere usato o accessibile dopo che la classe è finita e non è idonea per l'estensione. I tenant non devono essere convertiti in un abbonamento a pagamento. I tenant ottenuti come parte di questo corso rimangono di proprietà di Microsoft Corporation e Microsoft si riserva il diritto di ottenere l'accesso e di riprenderne il possesso in qualsiasi momento. 

## Scenario

Bellows College è un'organizzazione educativa con più campus e programmi. Molti insegnanti e amministratori di Bellow College devono partecipare agli eventi e acquistare articoli. Storicamente, tenere traccia di queste spese è stata una sfida.

L'amministrazione campus vuole modernizzare il sistema di gestione delle spese fornendo ai dipendenti un modo digitale per segnalare le spese.

In questo corso si creeranno applicazioni ed eseguiranno l'automazione per consentire ai dipendenti di Bellows College di gestire le spese.

## Procedura generale per il lab

Nell'ambito della creazione dell'app basata su modello, verranno completate le seguenti operazioni:

- Creare una nuova app basata su modello denominata Bellows Expense Management

- Modificare la navigazione dell'app per fare riferimento alle tabelle richieste

- Personalizzare i moduli e le viste delle tabelle necessari per l'app

Verranno utilizzati i seguenti componenti:

- **Viste**: le viste consentono all'utente di visualizzare i dati esistenti nella tabella del modulo.

- **Moduli**: qui l'utente può creare/aggiornare nuove righe nelle tabelle.

Entrambi verranno integrati nell'app basata su modello per una migliore esperienza utente.

### Prerequisiti

- Completamento del modulo 1 Lab 0 - Convalidare l'ambiente **lab**

**Aspetti da considerare prima di iniziare**

- Quali modifiche sono necessarie per migliorare l'esperienza utente?

- Cosa è necessario includere in un'app basata su modello sulla base al modello di dati creato?

- Quali personalizzazioni possono essere effettuate sulla mappa del sito di un'app basata su modello?

## Esercizio 1: Personalizzare visualizzazioni e moduli

**Obiettivo:** in questo esercizio, verranno personalizzate le viste e i moduli delle tabelle create in modo personalizzato che verranno utilizzate nell'app basata su modello.

### Attività n. 1: Modifica modulo report spese

1. Se non si è già, accedere a https://make.powerapps.com

1. Selezionare l'ambiente **Dev One** in alto a destra se non è già selezionato.

1. Usando il riquadro di spostamento a sinistra, selezionare **Tabelle** e aprire la **tabella Expense Report** .

Se non viene visualizzata la tabella Report spese, assicurarsi di essere nell'ambiente corretto (passaggio 2).

1. Nella sezione **Esperienze con i dati**, selezionare **Moduli** e aprire il modulo **Informazioni** con il tipo di modulo **Principale**. (**Importante:**  assicurarsi di selezionare il modulo con il tipo di modulo **Principale**).

    >**IMPORTANTE:**  poiché tutti i moduli hanno il nome Informazioni per impostazione predefinita, verificare che il modulo selezionato abbia il tipo di modulo **Principale** e non un altro. Per impostazione predefinita, il modulo include due campi: Nome e Proprietario.

1. Sul lato destro della schermata nel **pannello Proprietà** selezionare il **campo Nome** visualizzato e modificarlo in Informazioni report

1. Selezionare **Colonne tabella** nel riquadro di spostamento a sinistra e aggiungere i campi seguenti sotto il campo **Proprietario** trascinando le colonne nel modulo o semplicemente facendo clic sui nomi delle colonne:

    - **Descrizione**

    - **Scopo del report**

    - **Scadenza report**

    - **Importo totale report**

1. Trascinare la colonna **Motivo stato** nell'intestazione del modulo.

L'intestazione si trova nell'area in alto a destra del modulo. Potrebbe essere necessario comprimere il pannello Proprietà sul lato destro della schermata per visualizzare il campo nel modulo.

1. Selezionare il campo **Proprietario**. Nel pannello Proprietà modificare l'etichetta **** in Richiedente

1. Selezionare il pulsante **Salva e pubblica** in alto a destra e attendere il completamento del salvataggio e della pubblicazione.

1. Se la visualizzazione di modifica è aperta in una nuova scheda o finestra del browser, chiuderla. In caso contrario, selezionare **🡠 Indietro** in alto a sinistra della schermata. A questo momento si tornerà ai moduli della **tabella Expense Report** .

1. Utilizzo delle barre di navigazione in alto a sinistra (**Tabelle > ****Expense Report > ****Forms).** Selezionare **Expense Report (Report** spese) per tornare alla **schermata delle proprietà della tabella expense report** .

## Attività n. 2: Modifica visualizzazione Report spese attive

In questa attività verrà modificata la visualizzazione predefinita Active Expense Reports e verrà creata una nuova visualizzazione per le note spese dovute oggi.

1. **Nella sezione Esperienze** dati selezionare **Visualizzazioni** e aprire la **visualizzazione Report** spese attivi.

1. Aggiungere i seguenti campi alla vista facendo clic su di essi o trascinandoli:

    - **Scopo del report**

    - **Scadenza report**

    - **Totale report**

1. Selezionare il menu a discesa nella colonna **Creato il** e selezionare **Rimuovi**. Il campo **Creato il** verrà ora rimosso dalla vista.

1. Ridimensionare le larghezze delle singole colonne per adattarle ai dati.

1. In **Ordina per …** selezionare la X per rimuovere **Nome** e selezionare **Invece Importo** totale report.

1. Selezionare **Report Total Amount (Importo** totale report) per modificare l'ordinamento impostando **Su Più grande su Più piccolo**.

1. Selezionare il pulsante **Salva e pubblica** in alto a destra e attendere il completamento della pubblicazione.

### Attività n. 3: Creare una nuova visualizzazione per i report a scadenza oggi

Ora cloneremo la vista per creare una nuova visualizzazione per i report a causa di oggi.

>    **IMPORTANTE:** assicurarsi di non chiudere la visualizzazione Report spese attivi, perché verrà sfruttata per creare la visualizzazione Report a scadenza oggi.

1. Seleziona **Salva con nome**.

1. Modificare il **nome** in Expense Reports Due Today e selezionare **Salva**.

1. Nel pannello Proprietà, selezionare **Modifica filtri**.

1. Selezionare **+ Aggiungi** e **Aggiungi riga**.

1. Selezionare **Segnala data** di scadenza come campo, quindi modificare **Uguale** a **Oggi** come condizione nell'elenco a discesa.

1. Selezionare  **…** **Altri comandi** sulla riga **Stato** e selezionare **Elimina** per eliminare la condizione di filtro.

1. Selezionare **OK** per salvare la condizione. La visualizzazione è ora filtrata in modo da visualizzare solo i record in cui la data** di scadenza del **report è oggi.

1. Aggiungere il **campo Importo** rimborso alla visualizzazione.

1. Selezionare il pulsante **Salva e pubblica** in alto a destra e attendere il completamento della pubblicazione.

## Esercizio 2: Creare un'app basata su modello

**Obiettivo:** in questo esercizio si creerà un'app basata su modello, si personalizzerà la mappa del sito e quindi si testerà l'app.

Per semplicità e tempo, non verranno affrontate tutte le colonne Expense Report in questo lab.

### Attività n.1: Creare l'app

1. Se non si è già, accedere a https://make.powerapps.com

1. Selezionare l'ambiente **Dev One** in alto a destra, se non è già selezionato.

1. Selezionare **+ Crea** nel riquadro di spostamento a sinistra.

1. Creare l'applicazione basata su modello:

    - Selezionare **App vuota** nella sezione **Inizia da** della schermata **Crea la tua app**.

    - In **App vuota basata su Dataverse** selezionare **Crea**.

    - Immettere Gestione spese dipendente per **Nome** e selezionare **Crea**.

1. Dopo il caricamento della nuova applicazione basata su modello, selezionare il pulsante **+ Aggiungi pagina**.

1. Nella schermata **Aggiungi pagina**, scegliere **Tabella di Dataverse**, quindi selezionare il pulsante **Avanti**.

1. Selezionare le tabelle seguenti:

    - Spese

    - Contatto

1. Una volta disponibili entrambe le tabelle, selezionare **Aggiungi**.

1. Usando le icone di spostamento su lato sinistro della schermata, selezionare **Spostamento**.

1. Nel riquadro di spostamento, selezionare **Nuovo gruppo** sotto la dicitura Navigazione. Potrebbe essere necessario espandere il menu a sinistra.

1. Sul lato destro della schermata, nella **sezione Opzioni** di visualizzazione modificare la **proprietà Title** in Report

1. Selezionare**Salva** e attendere che le modifiche vengano salvate.

1. Al termine del** salvataggio** selezionare il pulsante **Pubblica** per pubblicare le modifiche. Attendere il completamento della pubblicazione.

## Attività n. 2: Testare l'app

**Avviare l'applicazione**

1. Selezionare il pulsante **Riproduci**, l'app basata su modello verrà caricata in una nuova scheda.

**Creare un nuovo contatto**

1. L'app verrà aperta nella visualizzazione **Contatti attivi**. In caso contrario, selezionare **Contatti** nel riquadro di spostamento sinistro.

1. Selezionare **+ Nuovo** dalla barra dei comandi.

1. Immettere **First Name (Nome** ) come John e **Last Name (Cognome** ) come Doe

1. Indicare l'e-mail personale come **E-mail**. Verrà usata in un lab futuro in cui si riceverà un messaggio e-mail.

1. Seleziona **Salva e chiudi**.

1. Il nuovo contatto creato dovrebbe essere ora visibile nella visualizzazione **Contatti attivi personali**.

**Creare un nuovo report spese**

1. Selezionare **Expense Reports (Note** spese) nel riquadro di spostamento a sinistra (noto anche come mappa del sito).

1. Selezionare **+ Nuovo**.

1. Compilare i campi come segue:

    - **Nome** report: nuovo report di test

    - **Scopo** report: selezionare **Conferenza**

    - **Data di scadenza** del report: selezionare Data odierna

1. Seleziona **Salva e chiudi**. Verrà creato il nuovo report di test e sarà possibile visualizzarlo nella **visualizzazione Report** spese attive.

1. Modificare la visualizzazione **in Expense Reports Due Today** usando l'elenco a discesa accanto a **Report** spese attive. 

1. È possibile aggiungere altri record di test.

L'app basata su modello in esecuzione dovrebbe avere un aspetto simile al seguente:

![Screenshot dell'app basata su modello appena creata.](media/lab-3-create-a-model-app-01.png)

Complimenti. È stata creata e configurata la prima app basata su modello.
