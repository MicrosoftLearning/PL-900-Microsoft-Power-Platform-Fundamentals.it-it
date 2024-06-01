---
lab:
  title: 'Lab 5: Come creare un dashboard semplice'
  module: 'Module 5: Describe the capabilities of Microsoft Power BI'
---

## Lab 5: Come creare un dashboard semplice

**Tenant WWL: condizioni per l'utilizzo** Se, come parte della distribuzione di formazione con istruttore, viene fornito un tenant, tenere presente che il tenant viene reso disponibile allo scopo di supportare le esercitazioni pratiche nel training con docente. I tenant non devono essere condivisi o utilizzati per scopi esterni alle esercitazioni pratiche. Il tenant usato in questo corso è un tenant di valutazione e non può essere usato o accessibile dopo che la classe è finita e non è idonea per l'estensione. I tenant non devono essere convertiti in un abbonamento a pagamento. I tenant ottenuti come parte di questo corso rimangono di proprietà di Microsoft Corporation e Microsoft si riserva il diritto di ottenere l'accesso e di riprenderne il possesso in qualsiasi momento. 

## Scenario

Bellows College è un'organizzazione educativa con più edifici nel campus. I visitatori del campus sono attualmente registrati in giornali di registrazione cartacei. Le informazioni non vengono acquisite in modo coerente e non ci sono mezzi per raccogliere e analizzare i dati sulle visite nell'intero campus.

L'amministrazione del campus vorrebbe modernizzare il proprio sistema di registrazione dei visitatori, facendo controllare l'accesso agli edifici dal personale addetto alla sicurezza e richiedendo una preregistrazione di tutte le visite da parte degli ospiti.

In questo lab verranno creati un report e un dashboard di Power BI che visualizza i dati sulle visite al campus.

**Passaggi generali del lab**

Verranno eseguite le procedure seguenti per progettare e creare un dashboard di Power BI:

- Creare un report con varie visualizzazioni delle informazioni sulle visite al campus

- Utilizzare una query in linguaggio naturale dell'utente per creare visualizzazioni aggiuntive

### Prerequisiti

- Completamento del modulo 1 Lab 0 - Convalidare l'ambiente **lab**

**Aspetti da considerare prima di iniziare**

- Chi sono i destinatari del report?

- In che modo i destinatari utilizzeranno il report? Qual è il dispositivo tipico? Luogo?

- Sono disponibili dati sufficienti da visualizzare?

- Quali sono le eventuali caratteristiche che è possibile utilizzare per analizzare i dati relativi alle visite?

## Esercizio 1: Creare un report di Power BI

**Obiettivo:** in questo esercizio verrà creato un report di Power BI in base ai dati del foglio di calcolo di Excel usato in un esercizio precedente.

### Attività 1: Preparare il servizio Power BI

1. Nella macchina virtuale deve essere archiviato un file visits.pbix nella cartella AllFiles sul desktop. Scaricare [visits.pbix](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/visits.pbix) e salvarlo nel computer, se non è già presente.

1. Aprire una nuova scheda e passare a https://app.powerbi.com; se necessario, effettuare l'accesso.

1. Nel riquadro di spostamento a sinistra, selezionare **Area di lavoro personale**.

1. Selezionare **Carica** e quindi **Sfoglia**.

1. Trovare e selezionare il file **visits.pbix** scaricato in precedenza.

1. Al termine del caricamento dei dati, selezionare il report **Visite**.

    >**Nota:** il tipo è impostato su **Report**, non selezionare il set di dati.

1. Seleziona **Modifica**

Se la voce di menu **Modifica** non è visibile fare clic sui puntini di sospensione **...** e quindi selezionare **Modifica**.

Ora è stato configurato il servizio Power BI da utilizzare per i lab.

### Attività 2: Creare le visualizzazioni grafiche per le visite e le informazioni temporali

1. Per inserire un grafico, fare clic sull'icona **Grafico a torta** nel pannello **Visualizzazioni**.

1. Espandere **bc_Visit** nel riquadro **Campi**. Trascinare il campo **Creazione** nella casella **Legenda**.

1. Trascinare il campo **Visita** nella casella **Valori**.

1. Ridimensionare il grafico a torta utilizzando le maniglie angolari in modo che tutti i componenti del grafico siano visibili.

1. Fare clic sul report all'esterno del grafico a torta per deselezionarlo e selezionare l'icona **Istogramma in pila** nel riquadro **Visualizzazioni**.

1. Se non è già stato fatto, espandere **bc_Visit** nel riquadro **Campi**. Trascinare il campo **Visit** nella casella di destinazione **Asse Y**.

1. Trascinare il campo **Start** nella casella di destinazione **Asse X**.

1. Ne riquadro **Visualizzazioni**, selezionare la **x** accanto a **Year** e **Quarter** per lasciare solo i totali di **Month** e **Day** per l'asse X.

1. Ridimensionare il grafico in base alle esigenze utilizzando le maniglie angolari.

1. Testare l'interattività del report:

    - Selezionare sezioni di compilazione diverse nel grafico a torta e osservare le modifiche nell'istogramma in pila.

    - Selezionare l'istogramma in pila. Selezionare la freccia su per eseguire il **Drill-up**. Selezionare la freccia a discesa per attivare la modalità **Drill-down** e quindi selezionare una colonna per eseguire il drill-down al livello successivo, ovvero i giorni.

    - Eseguire il drill-up e il drill-down e selezionare varie barre nell'istogramma in pila per osservare le modifiche nel report a torta.

1. Salvare il lavoro in corso selezionando **Salva questo report**.

## Esercizio 2: Creare un dashboard di Power BI

### Attività 1: Creare un dashboard di Power BI

1. Il report dovrebbe essere ancora aperto dall'attività precedente.

1. Selezionare **Aggiungi a un dashboard** nel menu. A seconda del layout potrebbe essere necessario selezionare il menu **con i puntini di sospensione ...** per visualizzare altre opzioni.

1. Selezionare **Nuovo dashboard** nel prompt **Aggiungi al dashboard**.

1. Immettere Campus Management (Gestione campus) come **Nome** dashboard e selezionare **Aggiungi live**.

1. Verrà visualizzato un popup per segnalare che il dashboard è stato creato. Selezionare **Vai al dashboard**.

1. Testare l'interattività dei grafici a torta e a barre visualizzati.

### Attività 2: Aggiungere visualizzazioni in linguaggio naturale

1. Nella dashboard **Campus Management**, selezionare la barra **Fai una domanda relativa ai dati** nella parte superiore.

1. Immettere edifici per numero di visite nell'area Q&A. Verrà visualizzato un grafico a barre.

1. Selezionare **Aggiungi oggetto visivo**.

1. Selezionare **Dashboard esistente**, selezionare il dashboard **Campus Management**, selezionare **Aggiungi**.

1. Selezionare **Esci Q&amp;A**.

Il dashboard **Campus Management** verrà visualizzato con tre oggetti visivi inclusi. Potrebbe essere necessario scorrere verso il basso per visualizzare i nuovi oggetti visivi delle domande e risposte.

Il dashboard dovrebbe avere un aspetto simile al seguente:

[![Screenshot del dashboard appena creato](media/lab-5-power-bi-01.png)](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Instructions/Labs/media/5-powerbi-result.png)

 
