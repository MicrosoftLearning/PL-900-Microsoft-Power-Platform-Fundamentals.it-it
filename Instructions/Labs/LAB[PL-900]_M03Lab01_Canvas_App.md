---
lab:
  title: 'Lab 2: Come creare un''app canvas'
  module: 'Module 3: Get started with Power Apps'
---

# <a name="lab-2-how-to-build-a-canvas-app"></a>Lab 2: Come creare un'app canvas

## <a name="scenario"></a>Scenario

Bellows College is an educational organization with multiple buildings on campus. Campus visits are currently recorded in paper journals. The information is not captured consistently, and there are no means to collect and analyze data about the visits across the entire campus.

Currently, campus administration is leveraging an Excel spreadsheet to track visitor registration. They would like to modernize their visitor registration system where access to the buildings is controlled by security personnel and all visits are required to be pre-registered and recorded by their hosts.

Durante questo corso verranno sviluppate applicazioni e si useranno le funzionalità di automazione per consentire al personale amministrativo e addetto alla sicurezza del Bellows College di gestire e controllare l'accesso agli edifici del campus.

## <a name="high-level-lab-steps"></a>Procedura generale per il lab

Verrà usata la sequenza seguente per progettare l'app canvas:

- Creare un'app canvas dai dati nella tabella Visit

- Configurare la modalità di visualizzazione delle visite nella schermata di esplorazione

- Apportare alcune modifiche di base all'app

- Testare la funzionalità dell'app

## <a name="prerequisites"></a>Prerequisiti

- Completamento del **lab 0 del modulo 0 - Convalidare l'ambiente lab**
- Completamento del **lab 1 del modulo 2 - Modellazione dei dati**

## <a name="exercise-1-create-visits-canvas-app"></a>Esercizio 1: Creare un'app canvas Visits

**Obiettivo:** in questo esercizio si creerà un'app canvas connettendo la tabella Visits creata in precedenza.

### <a name="task-1-create-the-visits-app"></a>Attività \#1: Creare l'app Visits

1.  Navigate to <ph id="ph1">&lt;https://make.powerapps.com&gt;</ph>. You may need to reauthenticate - click <bpt id="p1">**</bpt>Sign in<ept id="p1">**</ept> and follow instructions if needed.

2.  Selezionare l'ambiente **[iniziali] Practice** in alto a destra, se non è già selezionato.

3.  If necessary, click the <bpt id="p1">**</bpt>Home<ept id="p1">**</ept> icon on the left side of the screen. Under the <bpt id="p1">**</bpt>Start from<ept id="p1">**</ept> section, select <bpt id="p2">**</bpt>Dataverse<ept id="p2">**</ept>.

4.  Selezionare la connessione a Dataverse.

    > **NOTA:** *se non esiste una connessione a Dataverse:*
    > - Selezionare **Nuova connessione**
    > - Individuare **Microsoft Dataverse**
    > - Fare clic su **Crea**

5.  Individuare e selezionare la tabella **Visit** creata nel lab precedente.

6.  Selezionare il pulsante **Connetti** nell'angolo in basso a destra.

7.  Dopo aver creato l'app, nella schermata Benvenuto in Power Apps Studio selezionare la casella **Non visualizzare più questo messaggio** e quindi selezionare **Ignora**.

8.  Al termine della creazione, dovrebbe essere simile all'immagine seguente.

![App canvas creata dai dati Visit.](media/2-canvas-app-from-data.png)

9. Il Bellows College è un'organizzazione didattica con più edifici nel proprio campus.

10. Chiudere l'anteprima dell'app selezionando la **X** in alto a destra nella schermata.

Le visite al campus sono attualmente registrate su documenti cartacei.

### <a name="task-2-modify-and-theme-the-newly-created-app"></a>Attività \#2: Modificare il tema della nuova app creata

In questa attività si personalizzerà il testo dell'intestazione in ognuna delle tre schermate dell'app (Sfoglia, Dettagli e Modifica) e si modificherà il tema dell'app.

1.  Le informazioni non vengono acquisite in modo coerente e non esiste un sistema per raccogliere e analizzare i dati sulle visite in tutto il campus.

1.  Sul lato destro della schermata, nella scheda Proprietà, aggiornare la proprietà del controllo **Testo** impostandola su **"Bellows College Visits"** .

1. Nelle proprietà modificare le **dimensioni del carattere** su **24**.

1.  Fare clic sullo sfondo vuoto della schermata per visualizzare il testo aggiornato nella schermata Sfoglia.

1.  Usando la visualizzazione struttura ad albero nel riquadro di spostamento a sinistra, selezionare **DetailScreen1**.

1.  Selezionare l'etichetta **Visits** sullo schermo.

1.  Sul lato destro della schermata, nella scheda Proprietà, aggiornare la proprietà del controllo **Testo** impostandola su **"Visit Details"** .

1.  Fare clic sullo sfondo vuoto della schermata per visualizzare il testo aggiornato nella schermata Dettagli.

1.  Usando la visualizzazione struttura ad albero nel riquadro di spostamento a sinistra, selezionare **EditScreen1** (potrebbe essere necessario scorrere verso il basso per visualizzare questo elemento nella visualizzazione struttura ad albero).

1.  Selezionare l'etichetta **Visits** sullo schermo.

1.  Sul lato destro della schermata, nella scheda Proprietà, sostituire il testo Tabella1 nella proprietà del controllo **Testo** con **"Edit Details".**

1.  Fare clic sullo sfondo vuoto della schermata per visualizzare il testo aggiornato nella schermata di modifica.

1. Usando la visualizzazione struttura ad albero nel riquadro di spostamento a sinistra, selezionare **BrowseScreen1**.

1. Nella barra degli strumenti dei comandi selezionare il pulsante **Tema** e nell'elenco visualizzato selezionare il colore del tema **Rosso**.

### <a name="task-3-test-your-visits-app"></a>Attività \#3: Testare l'app Visits

In questa attività verrà testata la nuova app.

1.  Con l'applicazione aperta in Progettazione app selezionare **File**, aggiornare il nome dell'app in **Visits App** e selezionare **Salva**.

2.  Selezionare la freccia **Indietro** per tornare all'app.

3.  Usando la struttura di spostamento a sinistra, selezionare **BrowseScreen1**.

4.  In the app designer, select the <bpt id="p1">**</bpt>preview the app<ept id="p1">**</ept> button (Play icon) on the command bar. <bpt id="p1">*</bpt>(You can also preview the app by pressing F5 on your keyboard.)<ept id="p1">*</ept>

4.  Dopo aver aperto l'app, nel campo **Cerca elementi** immettere il testo **Maria**
     *(Si noti come gli elementi nella raccolta vengono filtrati in base a ciò che viene digitato nel campo di ricerca).*

5.  Attualmente l'amministrazione del campus usa un foglio di calcolo di Excel per registrare i visitatori.

6.  Per modificare il record, selezionare l'**icona a forma di matita** nell'angolo superiore destro dell'app.

7.  È possibile modificare il nome della visita qui e fare clic sull'icona Segno di spunta in alto a destra per salvare la modifica.

8.  In alto a destra della schermata fare clic sull'icona **X** per tornare all'editor dell'app canvas.

Vorrebbe modernizzare il proprio sistema di registrazione dei visitatori, facendo controllare l'accesso agli edifici dal personale addetto alla sicurezza e richiedendo una preregistrazione di tutte le visite da parte degli ospiti.

## <a name="challenges"></a>Problematiche

- Aggiungere le colonne seguenti ai moduli in DetailScreen1 e EditScreen1: Actual Start, Actual End, Code, Scheduled Start e Scheduled End