---
lab:
  title: 'Lab2: Come creare un''app canvas'
  module: 'Module 3: Describe how to build applications with Microsoft Power Apps'
---

# Lab2: Come creare un'app canvas

**Tenant WWL: condizioni per l'utilizzo** Se, come parte della distribuzione di formazione con istruttore, viene fornito un tenant, tenere presente che il tenant viene reso disponibile allo scopo di supportare le esercitazioni pratiche nel training con docente. I tenant non devono essere condivisi o utilizzati per scopi esterni alle esercitazioni pratiche. Il tenant usato in questo corso è un tenant di valutazione e non può essere usato o risultare accessibile dopo che la lezione è finita e non è idonea per l'estensione. I tenant non devono essere convertiti in un abbonamento a pagamento. I tenant ottenuti come parte di questo corso rimangono di proprietà di Microsoft Corporation e Microsoft si riserva il diritto di ottenere l'accesso e di riprenderne il possesso in qualsiasi momento. 

## Scenario

Il Bellows College è un'organizzazione educativa con più campus e programmi. Molti insegnanti e amministratori del Bellow College devono partecipare agli eventi e acquistare articoli. Storicamente, tenere traccia di queste spese è stata una sfida. 

L'amministrazione del campus vuole modernizzare il sistema di gestione delle spese fornendo ai dipendenti un modo digitale per segnalare le spese. 

In questo corso si creeranno delle applicazioni e si eseguirà l'automazione per consentire ai dipendenti del Bellows College di gestire le spese. 


## Procedura generale per il lab

Seguire la sequenza seguente per progettare l'app canvas:

- Creare un'app Canvas per il report delle spese 

- Configurare la modalità di visualizzazione delle note di spesa nella schermata di esplorazione

- Apportare alcune modifiche di base all'app

- Testare la funzionalità dell'app

## Prerequisiti

- Completamento del **Modulo 1 Lab 0 - Convalidare l'ambiente lab**

## Esercizio 1: Creare un'app Canvas per il Report delle spese

### Obiettivo: In questo esercizio si creerà un'app Canvas connettendosi a una tabella per il Report delle spese.

### Attività 1: Creare l'app per il Report delle spese

1. Passare a https://make.powerapps.com

1. Potrebbe essere necessario ripetere l'autenticazione. Selezionare **Accedi** e seguire le istruzioni, se richiesto.

1. Selezionare l'ambiente **Dev One** in alto a destra, se non è già selezionato.

1. Selezionare **+ Crea** dal riquadro di spostamento a sinistra della schermata. Nella sezione **Inizia da** selezionare **Dataverse**.

1. Selezionare la connessione a Dataverse.

    >**Nota**: Se non esiste una connessione a Dataverse:

    >   - Selezionare **Nuova connessione**

    >   - Individuare **Microsoft Dataverse**

    >   - Selezionare **Crea**.

    >   - **** Accedere e selezionare **Consenti accesso**

1. Individuare e selezionare la tabella **Report delle spese**.

1. Selezionare il pulsante **Connetti** nell'angolo in basso a destra.

1. Dopo aver creato l'app, nella schermata Benvenuto in Power Apps Studio, selezionare la casella **Non visualizzare più questo messaggio** e quindi selezionare **Ignora**.

1. Nella finestra di progettazione dell'app, selezionare il pulsante **Anteprima dell'app** (icona di riproduzione) sulla barra dei comandi. (È anche possibile visualizzare in anteprima l'app premendo il tasto F5.) Esplorare l'app per scoprirne l'aspetto predefinito.

1. Chiudere l'anteprima dell'app selezionando la **X** in alto a destra nella schermata.

Congratulazioni, è stata creata correttamente un'app Power Apps da una tabella Dataverse. Il passaggio successivo del processo consiste nel personalizzare l'app in modo che corrisponda alla personalizzazione delle organizzazioni. La serie successiva di passaggi illustra come implementare alcune personalizzazioni aggiuntive per l'app.

### Attività 2: Modificare il tema della nuova app creata

In questa attività si personalizzerà il testo dell'intestazione in ognuna delle tre schermate dell'app (Sfoglia, Dettagli e Modifica) e si modificherà il tema dell'app.

1. È attiva la schermata Sfoglia. Selezionare l'etichetta **Report delle spese** nella schermata.

1. Sul lato destro della schermata, nella scheda Proprietà, aggiornare la proprietà del controllo **Testo** impostandola su Il mio report delle spese

1. Nella scheda **Proprietà**, modificare le **Dimensioni del carattere** in **24**.

1. Selezionare lo sfondo vuoto della schermata per visualizzare il testo aggiornato nella schermata di esplorazione.

1. Usando la **visualizzazione struttura ad albero** nel riquadro di spostamento a sinistra, selezionare **DetailScreen1**.

1. Selezionare l'etichetta **Report delle spese** nella schermata.

1. Sul lato destro della schermata, nella scheda **Proprietà**, aggiornare la proprietà del controllo **Testo** impostandola su Dettagli del report

1. Fare clic sullo sfondo vuoto della schermata per visualizzare il testo aggiornato nella schermata Dettagli.

1. Usando la **visualizzazione struttura ad albero ** nel riquadro di spostamento a sinistra, selezionare **EditScreen1** (potrebbe essere necessario scorrere verso il basso per visualizzare questo elemento nella visualizzazione struttura ad albero).

1. Selezionare l'etichetta **Report delle spese** nella schermata.

1. Sul lato destro della schermata, nella scheda **Proprietà**, sostituire il testo Tabella1 nella proprietà del controllo **Testo** con Modifica dettagli

1. Fare clic sullo sfondo vuoto della schermata per visualizzare il testo aggiornato nella schermata di modifica.

1. Usando la **visualizzazione struttura ad albero**, nel riquadro di spostamento a sinistra, selezionare **BrowseScreen1**.

1. Nella barra degli strumenti dei comandi, selezionare il pulsante **Tema** e, nell'elenco visualizzato selezionare il colore del tema **Rosso**.

### Attività 3: Testare l'app Report delle spese

In questa attività verrà testata la nuova app.

1. Con l'applicazione aperta in Progettazione app, selezionare **Impostazioni** (potrebbe essere necessario selezionare... per visualizzare l'icona delle Impostazioni), nella sezione **Generale** aggiornare il nome dell'app nell’App Report delle spese selezionare la **X** per chiudere la schermata delle impostazioni e quindi selezionare **Salva**.

1. Usando la struttura di spostamento a sinistra, selezionare **BrowseScreen1**.

1. Nella finestra di progettazione dell'app, selezionare il pulsante **Anteprima dell'app** (icona di riproduzione) sulla barra dei comandi. (È anche possibile visualizzare l'anteprima dell'app premendo il tasto F5).

1. Una volta aperta l'app, nel campo **Cerca elementi** immettere il testo Trip (Si noti come gli elementi della galleria filtrano in base a ciò che viene digitato nel campo di ricerca).

1. Una volta visualizzato il record **Trip to Power Platform Conference**, selezionare una riga per spostarsi e aprire la schermata Dettagli per tale spesa.
 
    >**Nota**: Se vengono visualizzati più record Trip to Power Platform Conference, selezionarli.

1. Per modificare il record, selezionare l'**icona a forma di matita** nell'angolo superiore destro dell'app.

1. È possibile modificare il **Nome report** qui e selezionare l'icona **Segno di spunta** in alto a destra per salvare la modifica.

1. In alto a destra della schermata, selezionare l'icona **X** per tornare all'editor dell'app canvas.

Complimenti. È stata creata e configurata la prima app canvas.

 
