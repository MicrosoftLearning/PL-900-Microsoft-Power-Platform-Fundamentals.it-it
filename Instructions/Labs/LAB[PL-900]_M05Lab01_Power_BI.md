---
lab:
  title: 'Lab 5: Come creare un semplice dashboard'
  module: 'Module 5: Get Started with Power BI'
---

## <a name="lab-5-how-to-build-a-simple-dashboard"></a>Lab 5: Come creare un semplice dashboard

## <a name="scenario"></a>Scenario

Bellows College is an educational organization with multiple buildings on campus. Campus visitors are currently recorded in paper journals. The information is not captured consistently, and there are no means to collect and analyze data about the visits across the entire campus.

L'amministrazione del campus vorrebbe modernizzare il proprio sistema di registrazione dei visitatori, facendo controllare l'accesso agli edifici dal personale addetto alla sicurezza e richiedendo una preregistrazione di tutte le visite da parte degli ospiti.

Durante questo corso verranno sviluppate applicazioni e si useranno le funzionalità di automazione per consentire al personale amministrativo e addetto alla sicurezza del Bellows College di gestire e controllare l'accesso agli edifici del campus.

In questo lab verranno creati un report e un dashboard di Power BI che visualizza i dati sulle visite al campus.

## <a name="high-level-lab-steps"></a>Procedura generale per il lab

Verranno eseguite le procedure seguenti per progettare e creare un dashboard di Power BI:

-   Creare un report con varie visualizzazioni delle informazioni sulle visite al campus

-   Usare una query in linguaggio naturale per creare ulteriori visualizzazioni

## <a name="prerequisites"></a>Prerequisiti

- Completamento del **lab 0 del modulo 0 - Convalidare l'ambiente lab**
- Completamento del **lab 1 del modulo 2 - Modellazione dei dati**

## <a name="things-to-consider-before-you-begin"></a>Aspetti da considerare prima di iniziare

-   Chi sono i destinatari del report?
-   How will the audience consume the report? Typical device? Location?
-   Sono disponibili dati sufficienti per la visualizzazione?
-   Quali sono le possibili caratteristiche che è possibile usare per analizzare i dati sulle visite?

## <a name="exercise-1-create-power-bi-report"></a>Esercizio 1: Creare un report di Power BI

**Obiettivo:** In questo esercizio verrà creato un report di Power BI in base ai dati del foglio di calcolo di Excel usato in un esercizio precedente.

### <a name="task-1-prepare-power-bi-service"></a>Attività \#1: Preparare il servizio Power BI

1.  Scaricare [visits.pbix](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/visits.pbix) e salvarlo nel computer.

2.  Passare a <https://app.powerbi.com/> e accedere, se necessario.

3.  Nell'angolo inferiore sinistro della schermata selezionare **Recupera dati**

4.  Selezionare il pulsante **Recupera** in **File** nella sezione **Crea nuovo contenuto**.

5.  Selezionare **File locale**.

6.  Trovare e selezionare il file **visits.pbix** scaricato in precedenza.

7.  Al termine del caricamento dei dati, espandere **Area di lavoro personale** e selezionare il report delle **visite** (notare che Tipo è impostato su **Report**).

8.  Click <bpt id="p1">**</bpt>Edit<ept id="p1">**</ept>. If <bpt id="p1">**</bpt>Edit<ept id="p1">**</ept> menu item is not visible click <bpt id="p2">**</bpt>...<ept id="p2">**</ept> and then select <bpt id="p3">**</bpt>Edit<ept id="p3">**</ept>.

Il servizio Power BI è stato così configurato per l'uso nei lab.

### <a name="task-2-create-chart-and-time-visualizations"></a>Attività \#2: Creare le visualizzazioni grafiche per le visite e le informazioni temporali

1.  Fare clic sull'icona **Grafico a torta** nel pannello **Visualizzazioni** per inserire un grafico.

2.  Press the drop-down arrow beside <bpt id="p1">**</bpt>bc_building<ept id="p1">**</ept> in the Fields pane. Drag the <bpt id="p1">**</bpt>Building<ept id="p1">**</ept> field and drop it into <bpt id="p2">**</bpt>Legend<ept id="p2">**</ept> box.

3.  Il Bellows College è un'organizzazione didattica con più edifici nel proprio campus.

4.  Ridimensionare il grafico a torta usando i punti di controllo in angolo in modo che siano visibili tutti i componenti del grafico.

5.  Fare clic sul report all'esterno del grafico a torta per deselezionarlo e selezionare l'istogramma a colonne in pila nel riquadro **Visualizzazioni**.

6.  I visitatori del campus sono attualmente registrati su documenti cartacei.

7.  Trascinare il campo **Start** nella casella di destinazione **Asse X**.

8.  Nel riquadro Visualizzazioni fare clic sulla **x** accanto a **Year** e **Quarter** per lasciare solo i totali di **Month** e **Day** per l'asse.

9.  Ridimensionare il grafico nel modo preferito con i punti di controllo in angolo.

10. Testare il report in modo interattivo:

    1.  Fare clic sulle varie fette degli edifici nel grafico a torta e osservare le modifiche nel report temporale.

    2.  Le informazioni non vengono acquisite in modo coerente e non esiste un sistema per raccogliere e analizzare i dati sulle visite in tutto il campus.

    3.  Eseguire il drill-up e il drill-down e selezionare varie barre nell'istogramma temporale per osservare le modifiche nel grafico a torta.

11. Salvare il lavoro in corso facendo clic su **Salva**.

## <a name="exercise-2-create-power-bi-dashboard"></a>Esercizio 2: Creare un dashboard di Power BI

### <a name="task-1-create-power-bi-dashboard"></a>Attività \#1: Creare un dashboard di Power BI

1.  Il report dovrebbe essere ancora aperto dall'attività precedente.

2.  Select <bpt id="p1">**</bpt>Pin to a dashboard<ept id="p1">**</ept> on the menu. Depending on the layout you may need to press <bpt id="p1">**</bpt>...<ept id="p1">**</ept> to show additional menu items.

3.  Selezionare **Nuovo dashboard** nel prompt **Aggiungi a dashboard**.

4.  Immettere **Campus Management** come **Nome dashboard** e fare clic su **Aggiungi oggetto dinamico**.

5.  A pop-up will prompt you that the dashboard has been created. Select <bpt id="p1">**</bpt>Go to dashboard<ept id="p1">**</ept>.

6.  Testare l'interattività del grafico a torta e dell'istogramma visualizzati.

### <a name="task-2-add-visualizations-using-natural-language"></a>Attività \#2: Aggiungere visualizzazioni in linguaggio naturale

1.  Nel dashboard **Campus Management** selezionare la barra **Porre una domanda sui dati** in alto.

2.  Enter <bpt id="p1">**</bpt>buildings by number of visits<ept id="p1">**</ept> in Q&amp;A area. A bar chart will be displayed.

3.  Selezionare **Aggiungi oggetti visivo**.

4.  Selezionare **Dashboard esistente**, selezionare il dashboard **Campus Management** e fare clic su **Aggiungi**.

5.  Fare clic su **Chiudi Domande e risposte**.

Your <bpt id="p1">**</bpt>Campus Management<ept id="p1">**</ept> dashboard should be displayed with three visuals on it. You may have to scroll down to see the new Q&amp;A visual.

Il dashboard dovrebbe essere simile al seguente:

![](media/5-powerbi-result.png)