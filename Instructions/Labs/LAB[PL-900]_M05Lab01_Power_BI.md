---
lab:
  title: 'Lab 5: Come creare un semplice dashboard'
  module: 'Module 5: Get Started with Power BI'
---

## Lab 5: Come creare un semplice dashboard

**Tenant WWL - Condizioni per l'utilizzo** Se viene fornito un tenant come parte di un recapito di formazione con docente, si noti che il tenant viene reso disponibile allo scopo di supportare i lab pratici nella formazione con docente. I tenant non devono essere condivisi o usati per scopi esterni ai lab pratici. Il tenant usato in questo corso è un tenant di valutazione e non può essere usato o accessibile dopo che la classe è finita e non sono idonei per l'estensione. I tenant non devono essere convertiti in una sottoscrizione a pagamento. I tenant ottenuti come parte di questo corso rimangono la proprietà di Microsoft Corporation e ci si riserva il diritto di ottenere l'accesso e la ripossess in qualsiasi momento. 

## Scenario

Il Bellows College è un'organizzazione didattica con più edifici nel proprio campus. I visitatori del campus sono attualmente registrati su documenti cartacei. Le informazioni non vengono acquisite in modo coerente e non esiste un sistema per raccogliere e analizzare i dati sulle visite in tutto il campus.

L'amministrazione del campus vorrebbe modernizzare il proprio sistema di registrazione dei visitatori, facendo controllare l'accesso agli edifici dal personale addetto alla sicurezza e richiedendo una preregistrazione di tutte le visite da parte degli ospiti.

Durante questo corso verranno sviluppate applicazioni e si useranno le funzionalità di automazione per consentire al personale amministrativo e addetto alla sicurezza del Bellows College di gestire e controllare l'accesso agli edifici del campus.

In questo lab verranno creati un report e un dashboard di Power BI che visualizza i dati sulle visite al campus.

## Procedura generale per il lab

Verranno eseguite le procedure seguenti per progettare e creare un dashboard di Power BI:

-   Creare un report con varie visualizzazioni delle informazioni sulle visite al campus

-   Usare una query in linguaggio naturale per creare ulteriori visualizzazioni

## Prerequisiti

- Completamento del **lab 0 del modulo 0 - Convalidare l'ambiente lab**
- Completamento del **lab 1 del modulo 2 - Modellazione dei dati**

## Aspetti da considerare prima di iniziare

-   Chi sono i destinatari del report?
-   In che modo i destinatari useranno il report? Dispositivo tipico? Posizione?
-   Sono disponibili dati sufficienti per la visualizzazione?
-   Quali sono le possibili caratteristiche che è possibile usare per analizzare i dati sulle visite?

## Esercizio 1: Creare un report di Power BI

**Obiettivo:** In questo esercizio verrà creato un report di Power BI in base ai dati del foglio di calcolo di Excel usato in un esercizio precedente.

### Attività \#1: Preparare il servizio Power BI

1.  Nella macchina virtuale deve essere archiviato un file visits.pbix in C:/LabFiles. Scaricare [visits.pbix](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/visits.pbix) e salvarlo nel computer, se non è già presente.

2.  Aprire una nuova scheda e passare a <https://app.powerbi.com/> e accedere, se necessario.

3.  Selezionare **Area di lavoro personale** nel riquadro di spostamento a sinistra.

5.  Selezionare **Carica** e quindi **Sfoglia**.

6.  Individuare e selezionare il file **visits.pbix** scaricato in precedenza. 

7.  Al termine del caricamento dei dati, selezionare il report **visite** .

    Si noti che il tipo è impostato su **Report**, non selezionare il set di dati.

8.  Selezionare **Modifica**. 

    Se la voce di menu **Modifica** non è visibile, selezionare i puntini di sospensione **...** e quindi selezionare **Modifica**.

Il servizio Power BI è stato così configurato per l'uso nei lab.


### Attività \#2: Creare le visualizzazioni grafiche per le visite e le informazioni temporali

1.  Fare clic sull'icona **Grafico a torta** nel pannello **Visualizzazioni** per inserire un grafico.

2.  Fare clic sulla freccia a discesa accanto a **bc_Visit** nel riquadro Campi. Trascinare il campo **Building** nella casella **Legenda**.

3.  Trascinare il campo **Visit** nella casella **Valori**.

4.  Ridimensionare il grafico a torta usando i punti di controllo in angolo in modo che siano visibili tutti i componenti del grafico.

5.  Fare clic sul report all'esterno del grafico a torta per deselezionarlo e selezionare l'istogramma a colonne in pila nel riquadro **Visualizzazioni**.

6.  Fare clic sulla freccia a discesa accanto a **bc_Visit** nel riquadro Campi. Trascinare il campo **Visit** nella casella di destinazione **Asse Y**.

7.  Trascinare il campo **Start** nella casella di destinazione **Asse X**.

8.  Nel riquadro Visualizzazioni fare clic sulla **x** accanto a **Year** e **Quarter** per lasciare solo i totali di **Month** e **Day** per l'asse.

9.  Ridimensionare il grafico nel modo preferito con i punti di controllo in angolo.

10. Testare il report in modo interattivo:

    1.  Fare clic sulle varie fette degli edifici nel grafico a torta e osservare le modifiche nel report temporale.

    2.  Fare clic sull'istogramma. Fare clic sulla freccia a discesa per attivare la modalità **Drill-down** (o fare clic con il pulsante destro del mouse sul grafico e scegliere **Drill-down**), quindi fare clic su una colonna per eseguire il drill-down al livello successivo (giorni).

    3.  Eseguire il drill-up e il drill-down e selezionare varie barre nell'istogramma temporale per osservare le modifiche nel grafico a torta.

11. Salvare il lavoro in corso facendo clic su **Salva**.

## Esercizio 2: Creare un dashboard di Power BI

### Attività \#1: Creare un dashboard di Power BI

1.  Il report dovrebbe essere ancora aperto dall'attività precedente.

2.  Selezionare **Aggiungi a un dashboard** nel menu. A seconda del layout potrebbe essere necessario fare clic su **...** per visualizzare altre voci di menu.

3.  Selezionare **Nuovo dashboard** nel prompt **Aggiungi a dashboard**.

4.  Immettere **Campus Management** come **Nome dashboard** e fare clic su **Aggiungi oggetto dinamico**.

5.  Verrà visualizzato un popup per segnalare che il dashboard è stato creato. Selezionare **Vai al dashboard**.

6.  Testare l'interattività del grafico a torta e dell'istogramma visualizzati.

### Attività \#2: Aggiungere visualizzazioni in linguaggio naturale

1.  Nel dashboard **Campus Management** selezionare la barra **Porre una domanda sui dati** in alto.

2.  Immettere **buildings by number of visits** nell'area Domande e risposte. Verrà visualizzato un grafico a barre.

3.  Selezionare **Aggiungi oggetti visivo**.

4.  Selezionare **Dashboard esistente**, selezionare il dashboard **Campus Management** e fare clic su **Aggiungi**.

5.  Fare clic su **Chiudi Domande e risposte**.

Il dashboard **Campus Management** verrà visualizzato con tre oggetti visivi inclusi. Potrebbe essere necessario scorrere verso il basso per vedere il nuovo oggetto visivo Domande e risposte.

Il dashboard dovrebbe essere simile al seguente:

![](media/5-powerbi-result.png)
