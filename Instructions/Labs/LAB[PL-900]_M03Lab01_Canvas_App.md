---
lab:
  title: 'Lab2: Come creare un''app canvas'
  module: 'Module 3: Get started with Power Apps'
---

# Lab2: Come creare un'app canvas

**Tenant WWL: condizioni per l'utilizzo** Se, come parte della distribuzione di formazione con istruttore, viene fornito un tenant, tenere presente che il tenant viene reso disponibile allo scopo di supportare le esercitazioni pratiche nel training con docente. I tenant non devono essere condivisi o utilizzati per scopi esterni alle esercitazioni pratiche. Il tenant utilizzato in questo corso è un tenant di valutazione e non può essere utilizzato o reso accessibile dopo il termine della lezione e non è idoneo per l'estensione. I tenant non devono essere convertiti in un abbonamento a pagamento. I tenant ottenuti come parte di questo corso rimangono di proprietà di Microsoft Corporation e Microsoft si riserva il diritto di ottenere l'accesso e di riprenderne il possesso in qualsiasi momento. 

## Scenario

Bellows College è un'organizzazione educativa con più edifici nel campus. Attualmente, le visite al campus sono registrate in formato cartaceo. Le informazioni non vengono acquisite in modo coerente e non ci sono mezzi per raccogliere e analizzare i dati sulle visite nell'intero campus.

Attualmente l'amministrazione del campus usa un foglio di calcolo di Excel per registrare i visitatori. Vorrebbe modernizzare il proprio sistema di registrazione dei visitatori, facendo controllare l'accesso agli edifici dal personale addetto alla sicurezza e richiedendo una preregistrazione di tutte le visite da parte degli ospiti.

In questo corso verranno create applicazioni ed eseguita l'automazione per consentire al personale amministrativo e di sicurezza di Bellows College di gestire e controllare l'accesso agli edifici del campus.


## Procedura generale per il lab

Seguire la sequenza seguente per progettare l'app canvas:

- Creare un'app canvas dai dati nella tabella Visit

- Configurare la modalità di visualizzazione delle visite nella schermata di esplorazione

- Apportare alcune modifiche di base all'app

- Testare la funzionalità dell'app

## Prerequisiti

- Completamento del modulo 1 Lab 0 - Convalidare l'ambiente **lab**
- Completamento del **lab 1 del modulo 2 - Modellazione dei dati**


## Esercizio 1: Creare un'app canvas Visits

**Obiettivo:** in questo esercizio verrà creata un'app canvas connettendo la tabella Visits creata in precedenza.


### Attività \#1: Creare l'app Visits

1.  Passare a `https://make.powerapps.com`

2.  Potrebbe essere necessario ripetere l'autenticazione: selezionare **Accedi** e seguire le istruzioni, se necessario.

3.  Selezionare l'ambiente **Dev One** in alto a destra, se non è già selezionato.

4.  Selezionare **+ Crea** dal riquadro di spostamento a sinistra della schermata. Nella sezione **Inizia da** selezionare **Dataverse**.

5.  Selezionare la connessione a Dataverse.

    > **Nota:**  *se non esiste una connessione a Dataverse:*
    > - Selezionare **Nuova connessione**
    > - Individuare **Microsoft Dataverse**
    > - Selezionare **Crea**.
    > - **** Accedere e selezionare **Consenti accesso**

6.  Individuare e selezionare la tabella **Visit** creata nel lab precedente.

7.  Selezionare il pulsante **Connetti** nell'angolo in basso a destra.

8.  Dopo aver creato l'app, nella schermata Benvenuto in Power Apps Studio, selezionare la casella **Non visualizzare più questo messaggio** e quindi selezionare **Ignora**.

9.  Al termine della creazione, l'app canvas dovrebbe avere un aspetto simile all'immagine seguente:

    ![App canvas creata dai dati Visit.](media/2-canvas-app-from-data.png)

10.  Nella finestra di progettazione dell'app, selezionare il pulsante **Anteprima dell'app** (icona di riproduzione) sulla barra dei comandi. *(È anche possibile visualizzare in anteprima l'app premendo il tasto F5.)* Esplorare l'app per scoprirne l'aspetto predefinito.

11. Chiudere l'anteprima dell'app selezionando la **X** in alto a destra nella schermata.

Congratulazioni, è stata creata correttamente un'app Power Apps da una tabella Dataverse. Il passaggio successivo del processo consiste nel personalizzare l'app per il College Bellows. La serie successiva di passaggi illustra come implementare alcune personalizzazioni aggiuntive per l'app.


### Attività\#2: Modificare il tema della nuova app creata

In questa attività si personalizzerà il testo dell'intestazione in ognuna delle tre schermate dell'app (Sfoglia, Dettagli e Modifica) e si modificherà il tema dell'app. 

1.  È attiva la schermata Sfoglia. Selezionare l'etichetta **Visits** sullo schermo.

1.  Sul lato destro della schermata, nella scheda Proprietà, aggiornare la proprietà del controllo **Testo** impostandola su `Bellows College Visits`

1.  Nella scheda **Proprietà**, modificare le **Dimensioni del carattere** in **24**. 

1.  Selezionare lo sfondo vuoto della schermata per visualizzare il testo aggiornato nella schermata di esplorazione. 

1.  Usando la **visualizzazione struttura ad albero** nel riquadro di spostamento a sinistra, selezionare **DetailScreen1**. 

1.  Selezionare l'etichetta **Visits** sullo schermo.

1.  Sul lato destro della schermata, nella scheda **Proprietà**, aggiornare la proprietà del controllo **Testo** impostandola su `Visit Details`

1.  Fare clic sullo sfondo vuoto della schermata per visualizzare il testo aggiornato nella schermata Dettagli.

1.  Usando la **visualizzazione struttura ad albero ** nel riquadro di spostamento a sinistra, selezionare **EditScreen1** (potrebbe essere necessario scorrere verso il basso per visualizzare questo elemento nella visualizzazione struttura ad albero).

1.  Selezionare l'etichetta **Visits** sullo schermo.

1.  Sul lato destro della schermata, nella scheda **Proprietà**, sostituire il testo nella proprietà del controllo **Testo** con `Edit Details`

1.  Fare clic sullo sfondo vuoto della schermata per visualizzare il testo aggiornato nella schermata di modifica.

1.  Usando la **visualizzazione struttura ad albero**, nel riquadro di spostamento a sinistra, selezionare **BrowseScreen1**.

1.  Nella barra degli strumenti dei comandi, selezionare il pulsante **Tema** e, nell'elenco visualizzato selezionare il colore del tema **Rosso**.


### Attività\#3: Testare l'app Visits

In questa attività verrà testata la nuova app.

1.  Con l'applicazione aperta in Progettazione app, selezionare **Impostazioni**, nella sezione **Generale** aggiornare il nome dell'app in `Visits App`, selezionare la **X** per chiudere la schermata delle impostazioni e quindi selezionare **Salva**.

2.  Usando la struttura di spostamento a sinistra, selezionare **BrowseScreen1**.

3.  Nella finestra di progettazione dell'app, selezionare il pulsante **Anteprima dell'app** (icona di riproduzione) sulla barra dei comandi. *(È anche possibile visualizzare l'anteprima dell'app premendo il tasto F5).*

4.  Dopo aver aperto l'app, nel campo **Cerca elementi**, immettere il testo `Maria`
     *(Notare come gli elementi nella raccolta vengono filtrati in base a ciò che viene digitato nel campo di ricerca).*

5.  Dopo aver visualizzato il record **Contoso Suites** per **Maria Campbell**, selezionare una riga per passare ad aprire la Schermata dei dettagli per tale visita. (**Nota**: *se vengono visualizzati più record di Contoso Suites Maria Campbell, selezionarne uno*.)

6.  Per modificare il record, selezionare l'**icona a forma di matita** nell'angolo superiore destro dell'app.

7.  Qui è possibile modificare il **nome della visita** e selezionare l'icona **Segno di spunta** in alto a destra per salvare la modifica.

8.  In alto a destra della schermata, selezionare l'icona **X** per tornare all'editor dell'app canvas.

Complimenti. È stata creata e configurata la prima app canvas.

