---
lab:
  title: 'Lab 2: Come creare un''app canvas'
  module: 'Module 3: Get started with Power Apps'
---

# Lab 2: Come creare un'app canvas

**Tenant WWL - Condizioni per l'uso** Se viene fornito un tenant come parte di un recapito di training guidato dall'insegnante, si noti che il tenant viene reso disponibile per supportare i lab pratici nel training guidato dall'insegnante. I tenant non devono essere condivisi o usati per scopi esterni ai lab pratici. Il tenant usato in questo corso è un tenant di valutazione e non può essere usato o accessibile dopo che la classe è finita e non sono idonei per l'estensione. I tenant non devono essere convertiti in una sottoscrizione a pagamento. I tenant ottenuti come parte di questo corso rimangono la proprietà di Microsoft Corporation e si riserva il diritto di ottenere l'accesso e la repossess in qualsiasi momento. 

## Scenario

Il Bellows College è un'organizzazione didattica con più edifici nel proprio campus. Le visite al campus sono attualmente registrate su documenti cartacei. Le informazioni non vengono acquisite in modo coerente e non esiste un sistema per raccogliere e analizzare i dati sulle visite in tutto il campus.

Attualmente l'amministrazione del campus usa un foglio di calcolo di Excel per registrare i visitatori. Vorrebbe modernizzare il proprio sistema di registrazione dei visitatori, facendo controllare l'accesso agli edifici dal personale addetto alla sicurezza e richiedendo una preregistrazione di tutte le visite da parte degli ospiti.

Durante questo corso verranno sviluppate applicazioni e si useranno le funzionalità di automazione per consentire al personale amministrativo e addetto alla sicurezza del Bellows College di gestire e controllare l'accesso agli edifici del campus.


## Procedura generale per il lab

Verrà usata la sequenza seguente per progettare l'app canvas:

- Creare un'app canvas dai dati nella tabella Visit

- Configurare la modalità di visualizzazione delle visite nella schermata di esplorazione

- Apportare alcune modifiche di base all'app

- Testare la funzionalità dell'app

## Prerequisiti

- Completamento del **lab 0 del modulo 0 - Convalidare l'ambiente lab**
- Completamento del **lab 1 del modulo 2 - Modellazione dei dati**


## Esercizio 1: Creare un'app canvas Visits

**Obiettivo:** In questo esercizio si creerà un'app canvas connettendo la tabella Visit creata in precedenza.


### Attività \#1: Creare l'app Visits

1.  Accedere a <https://make.powerapps.com>. Potrebbe essere necessario riutenticare: selezionare **Accedi** e seguire le istruzioni se necessario.

2.  Selezionare l'ambiente **[iniziali] Practice** in alto a destra, se non è già selezionato.

3.  Selezionare **+ Crea** dalla barra di spostamento a sinistra della schermata. Nella sezione **Inizia da** selezionare **Dataverse**.

4.  Selezionare la connessione a Dataverse.

    > **Nota:** *se non esiste una connessione Dataverse:*
    > - Selezionare **+Nuova connessione**
    > - Individuare **Microsoft Dataverse**
    > - Selezionare **Crea**
    > - **Accedere** e selezionare **Consenti accesso**

5.  Individuare e selezionare la tabella **Visit** creata nel lab precedente.

6.  Selezionare il pulsante **Connetti** nell'angolo in basso a destra.

7.  Dopo aver creato l'app, nella schermata Benvenuto in Power Apps Studio selezionare **Non mostrarmi di nuovo** e quindi selezionare **Ignora**.

8.  Al termine della creazione, l'app Canvas dovrebbe essere simile all'immagine seguente:

    ![App canvas creata dai dati Visit.](media/2-canvas-app-from-data.png)

9.  Nella finestra di progettazione app selezionare **il pulsante Anteprima dell'app** (icona Play) sulla barra dei comandi. *È anche possibile visualizzare l'anteprima dell'app premendo F5.* Guarda in giro e vedi come l'app sembra fuori dalla scatola.

10. Chiudere l'anteprima dell'app selezionando la **X** in alto a destra nella schermata.

Congratulazioni, è stata creata correttamente un'app Power Apps da una tabella Dataverse. Il passaggio successivo del processo consiste nel personalizzare l'app in modo che corrisponda al marchio di Bellows College. La serie successiva di passaggi illustra come implementare alcune personalizzazioni aggiuntive per l'app.


### Attività \#2: Modificare il tema della nuova app creata

In questa attività si personalizzerà il testo dell'intestazione in ognuna delle tre schermate dell'app (Sfoglia, Dettagli e Modifica) e si modificherà il tema dell'app. 

1.  È attiva la schermata Sfoglia. Selezionare l'etichetta **Visits** sullo schermo.

1.  Sul lato destro della schermata, nella scheda Proprietà aggiornare la proprietà **Controllo testo** a `Bellows College Visits`

1.  Nella scheda **Proprietà** modificare le **dimensioni del carattere** su **24**. 

1.  Selezionare lo sfondo vuoto della schermata per visualizzare il testo aggiornato nella schermata Sfoglia. 

1.  Usando la **visualizzazione Albero** nel riquadro di spostamento a sinistra, selezionare **DetailScreen1**. 

1.  Selezionare l'etichetta **Visits** sullo schermo.

1.  Sul lato destro della schermata, nella scheda **Proprietà** aggiornare la proprietà **Controllo testo** a `Visit Details`

1.  Fare clic sullo sfondo vuoto della schermata per visualizzare il testo aggiornato nella schermata Dettagli.

1.  Usando la **visualizzazione Albero** nel riquadro di spostamento a sinistra, selezionare **EditScreen1** (potrebbe essere necessario scorrere verso il basso per visualizzare questo elemento nella visualizzazione Albero).

1.  Selezionare l'etichetta **Visits** sullo schermo.

1.  Sul lato destro della schermata, nella scheda **Proprietà** sostituire il testo nella proprietà **Controllo testo** con `Edit Details`

1.  Fare clic sullo sfondo vuoto della schermata per visualizzare il testo aggiornato nella schermata di modifica.

1.  Usando la **visualizzazione Albero**, nel riquadro di spostamento sinistro selezionare **SfogliaScreen1**.

1.  Nella barra degli strumenti dei comandi selezionare il pulsante Tema e nell'elenco visualizzato selezionare il colore **tema** **rosso** .


### Attività \#3: Testare l'app Visits

In questa attività verrà testata la nuova app.

1.  Con l'applicazione aperta nell'app Designer selezionare **Impostazioni**, nella sezione **Generale** aggiornare il nome dell'app **per** selezionare X per `Visits App` chiudere la schermata delle impostazioni e quindi selezionare **Salva**.

2.  Usando la struttura di spostamento a sinistra, selezionare **BrowseScreen1**.

3.  Nella finestra di progettazione app selezionare **il pulsante Anteprima dell'app** (icona Play) sulla barra dei comandi. *È anche possibile visualizzare l'anteprima dell'app premendo F5.*

4.  Dopo aver aperto l'app, nel campo **Elementi** di ricerca immettere il testo `Maria`
     *(Si noti come gli elementi nella raccolta filtrano in base a ciò che viene digitato nel campo di ricerca).*

5.  Dopo aver visualizzato il record **Contoso Suites** per **Maria Campbell** , selezionare una riga per spostarsi e aprire la schermata Dettagli per tale visita. **Nota:** *se vengono visualizzati più record di Contoso Suites Maria Campbell, selezionare uno di essi.*

6.  Per modificare il record, selezionare l'**icona a forma di matita** nell'angolo superiore destro dell'app.

7.  È possibile modificare il **nome** visita qui e selezionare l'icona **Segno di spunta** in alto a destra per salvare la modifica.

8.  Nella parte superiore destra della schermata selezionare l'icona **X** per chiudere la modalità di anteprima e tornare all'editor dell'app canvas.

Congratulazioni! È stata creata e configurata la prima app canvas.

