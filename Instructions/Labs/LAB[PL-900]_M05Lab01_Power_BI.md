---
lab:
  title: 'Lab 5: Come creare un dashboard semplice'
  module: 'Module 5: Get Started with Power BI'
---

## Lab 5: Come creare un dashboard semplice

**Tenant WWL: condizioni per l'utilizzo** Se, come parte della distribuzione di formazione con istruttore, viene fornito un tenant, tenere presente che il tenant viene reso disponibile allo scopo di supportare le esercitazioni pratiche nel training con docente. I tenant non devono essere condivisi o utilizzati per scopi esterni alle esercitazioni pratiche. Il tenant utilizzato in questo corso è un tenant di valutazione e non può essere utilizzato o reso accessibile dopo il termine della lezione e non è idoneo per l'estensione. I tenant non devono essere convertiti in un abbonamento a pagamento. I tenant ottenuti come parte di questo corso rimangono di proprietà di Microsoft Corporation e Microsoft si riserva il diritto di ottenere l'accesso e di riprenderne il possesso in qualsiasi momento. 

## Scenario

Bellows College è un'organizzazione educativa con più edifici nel campus. I visitatori del campus sono attualmente registrati in giornali di registrazione cartacei. Le informazioni non vengono acquisite in modo coerente e non ci sono mezzi per raccogliere e analizzare i dati sulle visite nell'intero campus.

L'amministrazione del campus vorrebbe modernizzare il proprio sistema di registrazione dei visitatori, facendo controllare l'accesso agli edifici dal personale addetto alla sicurezza e richiedendo una preregistrazione di tutte le visite da parte degli ospiti.

In questo corso verranno create applicazioni ed eseguita l'automazione per consentire al personale amministrativo e di sicurezza di Bellows College di gestire e controllare l'accesso agli edifici del campus.

In questo lab verranno creati un report e un dashboard di Power BI che visualizza i dati sulle visite al campus.

## Procedura generale per il lab

Verranno eseguite le procedure seguenti per progettare e creare un dashboard di Power BI:

-   Creare un report con varie visualizzazioni delle informazioni sulle visite al campus

-   Utilizzare una query in linguaggio naturale dell'utente per creare visualizzazioni aggiuntive

## Prerequisiti

- Completamento del **lab 0 del modulo 0 - Convalidare l'ambiente lab**
- Completamento del **lab 1 del modulo 2 - Modellazione dei dati**

## Aspetti da considerare prima di iniziare

-   Chi sono i destinatari del report?
-   In che modo i destinatari utilizzeranno il report? Qual è il dispositivo tipico? Luogo?
-   Sono disponibili dati sufficienti da visualizzare?
-   Quali sono le eventuali caratteristiche che è possibile utilizzare per analizzare i dati relativi alle visite?

## Esercizio 1: Creare un report di Power BI

**Obiettivo:** in questo esercizio verrà creato un report di Power BI in base ai dati del foglio di calcolo di Excel usato in un esercizio precedente.

### Attività \#1: Preparare il servizio Power BI

1.  Nella macchina virtuale deve essere archiviato un file visits.pbix nella cartella AllFiles sul desktop. Scaricare [visits.pbix](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/visits.pbix) e salvarlo nel computer, se non è già presente.

2.  Aprire una nuova scheda e passare a `https://app.powerbi.com`; se necessario, effettuare l'accesso.

3.  Nel riquadro di spostamento a sinistra, selezionare **Area di lavoro personale**.

5.  Selezionare **Carica** e quindi **Sfoglia**.

6.  Trovare e selezionare il file **visits.pbix** scaricato in precedenza. 

7.  Al termine del caricamento dei dati, selezionare il report **Visite**.

    > **Nota:** il tipo è impostato su **Report**, non selezionare il set di dati.

8.  Seleziona **Modifica**. 

    Se la voce di menu **Modifica** non è visibile fare clic sui puntini di sospensione **...** e quindi selezionare **Modifica**.

Ora è stato configurato il servizio Power BI da utilizzare per i lab.


### Attività \#2: Creare le visualizzazioni grafiche e le informazioni temporali

1.  Per inserire un grafico, fare clic sull'icona **Grafico a torta** nel pannello **Visualizzazioni**.

2.  Espandere **bc_Visit** nel riquadro **Campi**. Trascinare il campo **Creazione** nella casella **Legenda**.

3.  Trascinare il campo **Visita** nella casella **Valori**.

4.  Ridimensionare il grafico a torta utilizzando le maniglie angolari in modo che tutti i componenti del grafico siano visibili.

5.  Fare clic sul report all'esterno del grafico a torta per deselezionarlo e selezionare l'icona **Istogramma in pila** nel riquadro **Visualizzazioni**.

6.  Se non è già stato fatto, espandere **bc_Visit** nel riquadro **Campi**. Trascinare il campo **Visit** nella casella di destinazione **Asse Y**.

7.  Trascinare il campo **Start** nella casella di destinazione **Asse X**.

8.  Ne riquadro **Visualizzazioni**, selezionare la **x** accanto a **Year** e **Quarter** per lasciare solo i totali di **Month** e **Day** per l'asse X.

9.  Ridimensionare il grafico in base alle esigenze utilizzando le maniglie angolari.

10. Testare l'interattività del report:

    1.  Selezionare sezioni di compilazione diverse nel grafico a torta e osservare le modifiche nell'istogramma in pila.

    2.  Selezionare l'istogramma in pila. Selezionare la freccia su per eseguire il **Drill-up**. Selezionare la freccia a discesa per attivare la modalità **Drill-down** e quindi selezionare una colonna per eseguire il drill-down al livello successivo, ovvero i giorni.

    3.  Eseguire il drill-up e il drill-down e selezionare varie barre nell'istogramma in pila per osservare le modifiche nel report a torta.

11. Salvare il lavoro in corso selezionando **Salva questo report**.


## Esercizio 2: Creare un dashboard di Power BI

### Attività\#1: Creare un dashboard di Power BI

1.  Il report dovrebbe essere ancora aperto dall'attività precedente.

2.  Selezionare **Aggiungi a un dashboard** nel menu. A seconda del layout potrebbe essere necessario selezionare il menu **con i puntini di sospensione ...** per visualizzare altre opzioni.

3.  Selezionare **Nuovo dashboard** nel prompt **Aggiungi al dashboard**.

4.  Immettere `Campus Management` come **Nome dashboard** e selezionare **Aggiungi oggetto dinamico**.

5.  Verrà visualizzato un popup per segnalare che il dashboard è stato creato. Selezionare **Vai al dashboard**.

6.  Testare l'interattività dei grafici a torta e a barre visualizzati.


### Attività\#2: Aggiungere visualizzazioni utilizzando il linguaggio naturale

1.  Nella dashboard **Campus Management**, selezionare la barra **Fai una domanda relativa ai dati** nella parte superiore.

2.  Immettere `buildings by number of visits` nell'area domande e risposte. Verrà visualizzato un grafico a barre.

3.  Selezionare **Aggiungi oggetto visivo**.

4.  Selezionare **Dashboard esistente**, selezionare il dashboard **Campus Management**, selezionare **Aggiungi**.

5.  Selezionare **Esci da domande e risposte**.

Il dashboard **Campus Management** verrà visualizzato con tre oggetti visivi inclusi. Potrebbe essere necessario scorrere verso il basso per visualizzare i nuovi oggetti visivi delle domande e risposte.

Il dashboard dovrebbe avere un aspetto simile al seguente:

![](media/5-powerbi-result.png)

