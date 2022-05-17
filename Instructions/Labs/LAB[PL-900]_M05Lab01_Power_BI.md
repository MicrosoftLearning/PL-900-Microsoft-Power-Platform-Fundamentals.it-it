---
lab:
  title: 'Lab 5: Come creare un semplice dashboard'
  module: 'Module 5: Get Started with Power BI'
ms.openlocfilehash: 8d104c42de9d4114c668a63a4d8d30cbbcc4b39e
ms.sourcegitcommit: 36c8fda9cdc6f448416d7000e38c1606bea87d2e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2022
ms.locfileid: "144812935"
---
# <a name="module-5-get-started-with-power-bi"></a>Modulo 5: Introduzione a Power BI
## <a name="lab-how-to-build-a-simple-dashboard"></a>Laboratorio: Come creare un semplice dashboard

# <a name="scenario"></a>Scenario

Il Bellows College è un'organizzazione didattica con più edifici nel proprio campus. I visitatori del campus sono attualmente registrati su documenti cartacei. Le informazioni non vengono acquisite in modo coerente e non esiste un sistema per raccogliere e analizzare i dati sulle visite in tutto il campus.

L'amministrazione del campus vorrebbe modernizzare il proprio sistema di registrazione dei visitatori, facendo controllare l'accesso agli edifici dal personale addetto alla sicurezza e richiedendo una preregistrazione di tutte le visite da parte degli ospiti.

Durante questo corso verranno sviluppate applicazioni e si useranno le funzionalità di automazione per consentire al personale amministrativo e addetto alla sicurezza del Bellows College di gestire e controllare l'accesso agli edifici del campus.

In questo lab verrà creato un dashboard di Power BI per la visualizzazione dei dati sulle visite al campus.

# <a name="high-level-lab-steps"></a>Procedura generale per il lab

Verranno eseguite le procedure seguenti per progettare e creare un dashboard di Power BI:

-   Connettersi a Dataverse

-   Trasformare i dati per includere descrizioni accessibili per le righe correlate (ricerche)

-   Creare e pubblicare un report con varie visualizzazioni delle informazioni sulle visite al campus

-   Usare una query in linguaggio naturale per creare ulteriori visualizzazioni

-   Creare una visualizzazione per dispositivi mobili del dashboard di Power BI

## <a name="prerequisites"></a>Prerequisiti

-   Completamento del **lab 0 del modulo 0 - Convalidare l'ambiente lab**

-   Completamento del **lab 1 del modulo 2 - Introduzione a Microsoft Dataverse**

## <a name="things-to-consider-before-you-begin"></a>Aspetti da considerare prima di iniziare

-   Chi sono i destinatari del report?

-   In che modo i destinatari useranno il report? Dispositivo tipico? Posizione?

-   Sono disponibili dati sufficienti per la visualizzazione?

-   Quali sono le possibili caratteristiche che è possibile usare per analizzare i dati sulle visite?

# <a name="exercise-1-create-power-bi-report"></a>Esercizio 1: Creare un report di Power BI

**Obiettivo:** In questo esercizio verrà creato un report di Power BI in base ai dati del foglio di calcolo di Excel usato in un esercizio precedente.

## <a name="task-1-prepare-power-bi-service"></a>Attività \#1: Preparare il servizio Power BI

1.  Scaricare [visits.pbix](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/visits.pbix) e salvarlo nel computer.

2.  Passare a <https://app.powerbi.com/> e accedere, se necessario.

3.  Nell'angolo inferiore sinistro della schermata selezionare **Recupera dati**

4.  Selezionare il pulsante **Recupera** in **File** nella sezione **Crea nuovo contenuto**.

5.  Selezionare **File locale**.

6.  Trovare e selezionare il file **visits.pbix** scaricato in precedenza.

7.  Al termine del caricamento dei dati selezionare il report **visits**. Si noti che il tipo è impostato su **Report**.

8.  Fare clic su **Modifica**. Se la voce di menu **Modifica** non è visibile fare clic su **...** e quindi selezionare **Modifica**.

Il servizio Power BI è stato così configurato per l'uso nei lab. 

## <a name="task-2-create-chart-and-time-visualizations"></a>Attività \#2: Creare le visualizzazioni grafiche per le visite e le informazioni temporali

1.  Fare clic sull'icona **Grafico a torta** nel pannello **Visualizzazioni** per inserire un grafico.

2.  Fare clic sulla freccia a discesa accanto a **bc_name** nel riquadro Campi. Trascinare il campo **Building** nella casella **Legenda**.

3.  Fare clic sulla freccia a discesa accanto a **bc_Visit** nel riquadro Campi. Trascinare il campo **Visit** nella casella **Valori**.

4.  Ridimensionare il grafico a torta usando i punti di controllo in angolo in modo che siano visibili tutti i componenti del grafico.

5.  Fare clic sul report all'esterno del grafico a torta per deselezionarlo e selezionare l'istogramma a colonne in pila nel riquadro **Visualizzazioni**.

6.  Fare clic sulla freccia a discesa accanto a **bc_Visit** nel riquadro Campi. Trascinare il campo **Visit** nella casella **Valori**.

7.  Trascinare il campo **Start** nella casella **Asse**.

8.  Nel riquadro Visualizzazioni fare clic sulla **x** accanto a **Year** e **Quarter** per lasciare solo i totali di **Month** e **Day** per l'asse.

9.  Ridimensionare il grafico nel modo preferito con i punti di controllo in angolo.

10. Testare il report in modo interattivo:

    1.  Fare clic sulle varie fette degli edifici nel grafico a torta e osservare le modifiche nel report temporale.

    2.  Fare clic sull'istogramma. Fare clic sulla freccia a discesa per attivare la modalità **Drill-down** (o fare clic con il pulsante destro del mouse sul grafico e scegliere **Drill-down**), quindi fare clic su una colonna per eseguire il drill-down al livello successivo (giorni). 
    
    3.  Eseguire il drill-up e il drill-down e selezionare varie barre nell'istogramma temporale per osservare le modifiche nel grafico a torta.

11. Salvare il lavoro in corso facendo clic su **Salva**.

# <a name="exercise-2-create-power-bi-dashboard"></a>Esercizio \#2: Creare un dashboard di Power BI

## <a name="task-1-create-power-bi-dashboard"></a>Attività \#1: Creare un dashboard di Power BI

1.  Il report dovrebbe essere ancora aperto dall'attività precedente.

2.  Selezionare **Aggiungi a un dashboard** nel menu. A seconda del layout potrebbe essere necessario fare clic su **...** per visualizzare altre voci di menu.

3.  Selezionare **Nuovo dashboard** nel prompt **Aggiungi a dashboard**.

4.  Immettere **Campus Management** come **Nome dashboard** e fare clic su **Aggiungi oggetto dinamico**.

5.  Selezionare **Area di lavoro personale** in alto e selezionare il dashboard **[cognome] Campus Management**.

6.  Verrà visualizzato un popup per segnalare che il dashboard è stato creato. Selezionare **Vai al dashboard**.

7.  Testare l'interattività del grafico a torta e dell'istogramma visualizzati.

## <a name="task-2-add-visualizations-using-natural-language"></a>Attività \#2: Aggiungere visualizzazioni in linguaggio naturale

1.  Nel dashboard **Campus Management** selezionare la barra **Porre una domanda sui dati** in alto.

2.  Immettere **buildings by number of visits** nell'area Domande e risposte. Verrà visualizzato un grafico a barre.

3.  Selezionare **Aggiungi oggetti visivo**.

4.  Selezionare **Dashboard esistente**, selezionare il dashboard **Campus Management** e fare clic su **Aggiungi**.

5.  Fare clic su **Chiudi Domande e risposte**.

Il dashboard **Campus Management** verrà visualizzato con tre oggetti visivi inclusi. Potrebbe essere necessario scorrere verso il basso per vedere il nuovo oggetto visivo Domande e risposte.

Il dashboard dovrebbe essere simile al seguente:

![](media/5-powerbi-result.png)
