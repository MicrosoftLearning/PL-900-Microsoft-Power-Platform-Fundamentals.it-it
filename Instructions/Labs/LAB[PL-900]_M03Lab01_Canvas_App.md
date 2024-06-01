---
lab:
  title: 'Lab2: Come creare un''app canvas'
  module: 'Module 3: Describe how to build applications with Microsoft Power Apps'
---

# Lab2: Come creare un'app canvas

**Tenant WWL: condizioni per l'utilizzo** Se, come parte della distribuzione di formazione con istruttore, viene fornito un tenant, tenere presente che il tenant viene reso disponibile allo scopo di supportare le esercitazioni pratiche nel training con docente. I tenant non devono essere condivisi o utilizzati per scopi esterni alle esercitazioni pratiche. Il tenant usato in questo corso è un tenant di valutazione e non può essere usato o accessibile dopo che la classe è finita e non è idonea per l'estensione. I tenant non devono essere convertiti in un abbonamento a pagamento. I tenant ottenuti come parte di questo corso rimangono di proprietà di Microsoft Corporation e Microsoft si riserva il diritto di ottenere l'accesso e di riprenderne il possesso in qualsiasi momento. 

## Scenario

Bellows College è un'organizzazione educativa con più campus e programmi. Molti insegnanti e amministratori di Bellow College devono partecipare agli eventi e acquistare articoli. Storicamente, tenere traccia di queste spese è stata una sfida. 

L'amministrazione campus vuole modernizzare il sistema di gestione delle spese fornendo ai dipendenti un modo digitale per segnalare le spese. 

In questo corso si creeranno applicazioni ed eseguiranno l'automazione per consentire ai dipendenti di Bellows College di gestire le spese. 


## Procedura generale per il lab

Seguire la sequenza seguente per progettare l'app canvas:

- Creare un'app canvas per il report spese 

- Configurare la modalità di visualizzazione delle note spese nella schermata di esplorazione

- Apportare alcune modifiche di base all'app

- Testare la funzionalità dell'app

## Prerequisiti

- Completamento del modulo 1 Lab 0 - Convalidare l'ambiente **lab**

## Esercizio 1: Creare un'app Canvas expense reports

### Obiettivo: in questo esercizio si creerà un'app canvas connettendosi a una tabella Expense Reports.

### Attività 1: Creare l'app Expense Reports

1. Passare a https://make.powerapps.com

1. Potrebbe essere necessario ripetere l'autenticazione: selezionare **Accedi** e seguire le istruzioni, se necessario.

1. Selezionare l'ambiente **Dev One** in alto a destra, se non è già selezionato.

1. Selezionare **+ Crea** dal riquadro di spostamento a sinistra della schermata. Nella sezione **Inizia da** selezionare **Dataverse**.

1. Selezionare la connessione a Dataverse.

    >**Nota**: se non esiste una connessione Dataverse:

    >   - Selezionare **Nuova connessione**

    >   - Individuare **Microsoft Dataverse**

    >   - Selezionare **Crea**.

    >   - **** Accedere e selezionare **Consenti accesso**

1. Individuare e selezionare la **tabella Expense reports (Report** spese).

1. Selezionare il pulsante **Connetti** nell'angolo in basso a destra.

1. Dopo aver creato l'app, nella schermata Benvenuto in Power Apps Studio, selezionare la casella **Non visualizzare più questo messaggio** e quindi selezionare **Ignora**.

1. Nella finestra di progettazione dell'app, selezionare il pulsante **Anteprima dell'app** (icona di riproduzione) sulla barra dei comandi. (È anche possibile visualizzare in anteprima l'app premendo il tasto F5.) Esplorare l'app per scoprirne l'aspetto predefinito.

1. Chiudere l'anteprima dell'app selezionando la **X** in alto a destra nella schermata.

Congratulazioni, è stata creata correttamente un'app Power Apps da una tabella Dataverse. Il passaggio successivo del processo consiste nel personalizzare l'app in modo che corrisponda alla personalizzazione delle organizzazioni. La serie successiva di passaggi illustra come implementare alcune personalizzazioni aggiuntive per l'app.

### Attività 2: Modificare il tema della nuova app creata

In questa attività si personalizzerà il testo dell'intestazione in ognuna delle tre schermate dell'app (Sfoglia, Dettagli e Modifica) e si modificherà il tema dell'app.

1. È attiva la schermata Sfoglia. Selezionare l'etichetta **Expense Reports** nella schermata.

1. Sul lato destro della schermata, nella scheda Proprietà aggiornare la **proprietà Controllo testo** a My Expense Reports

1. Nella scheda **Proprietà**, modificare le **Dimensioni del carattere** in **24**.

1. Selezionare lo sfondo vuoto della schermata per visualizzare il testo aggiornato nella schermata di esplorazione.

1. Usando la **visualizzazione struttura ad albero** nel riquadro di spostamento a sinistra, selezionare **DetailScreen1**.

1. Selezionare l'etichetta **Expense Reports** nella schermata.

1. Sul lato destro della schermata, nella **scheda Proprietà** aggiornare la **proprietà Controllo testo** in Dettagli report

1. Fare clic sullo sfondo vuoto della schermata per visualizzare il testo aggiornato nella schermata Dettagli.

1. Usando la **visualizzazione struttura ad albero ** nel riquadro di spostamento a sinistra, selezionare **EditScreen1** (potrebbe essere necessario scorrere verso il basso per visualizzare questo elemento nella visualizzazione struttura ad albero).

1. Selezionare l'etichetta **Expense Reports** nella schermata.

1. Sul lato destro della schermata, nella **scheda Proprietà** sostituire il testo nella **proprietà Controllo testo** con Modifica dettagli

1. Fare clic sullo sfondo vuoto della schermata per visualizzare il testo aggiornato nella schermata di modifica.

1. Usando la **visualizzazione struttura ad albero**, nel riquadro di spostamento a sinistra, selezionare **BrowseScreen1**.

1. Nella barra degli strumenti dei comandi, selezionare il pulsante **Tema** e, nell'elenco visualizzato selezionare il colore del tema **Rosso**.

### Attività 3: Testare l'app Expense Reports

In questa attività verrà testata la nuova app.

1. Con l'applicazione aperta in Progettazione app, selezionare **Impostazioni** (potrebbe essere necessario selezionare ... per visualizzare l'icona delle impostazioni), nella **sezione Generale** aggiornare il nome dell'app in Expense Report App selezionare la **X** per chiudere la schermata delle impostazioni e quindi selezionare **Salva**.

1. Usando la struttura di spostamento a sinistra, selezionare **BrowseScreen1**.

1. Nella finestra di progettazione dell'app, selezionare il pulsante **Anteprima dell'app** (icona di riproduzione) sulla barra dei comandi. (È anche possibile visualizzare l'anteprima dell'app premendo il tasto F5).

1. Una volta aperta l'app, nel **campo Elementi di ricerca** immettere il testo Trip (Si noti come gli elementi nel filtro della raccolta in base a ciò che viene digitato nel campo di ricerca).

1. Una volta visualizzato il **record Trip to Power Platform Conference** , selezionare una riga per spostarsi e aprire la schermata Dettagli per tale spesa.
 
    >**Nota**: se vengono visualizzati più di un record Trip to Power Platform Conference, selezionarli.

1. Per modificare il record, selezionare l'**icona a forma di matita** nell'angolo superiore destro dell'app.

1. È possibile modificare il nome** del **report qui e selezionare l'icona **Segno di spunta** in alto a destra per salvare la modifica.

1. In alto a destra della schermata, selezionare l'icona **X** per tornare all'editor dell'app canvas.

Complimenti. È stata creata e configurata la prima app canvas.

 
