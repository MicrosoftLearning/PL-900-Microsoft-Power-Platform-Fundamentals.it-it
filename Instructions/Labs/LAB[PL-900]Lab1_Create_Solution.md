---
lab:
  title: 'Lab 1: Creare una soluzione'
  learning path: 'Learning Path: Manage the Microsoft Power Platform environment'
  module: 'Module 1: Describe Microsoft Dataverse'
---

## Obiettivo di apprendimento

In questo esercizio si creerà una soluzione Power Platform per archiviare i diversi componenti compilati. In Power Platform le soluzioni vengono usate per raggruppare componenti diversi e per garantire la trasportabilità. La soluzione creata in questo esercizio verrà usata nel resto del corso.

### Scenario

Contoso Consulting è un'organizzazione di servizi professionali specializzata in servizi di consulenza IT e di intelligenza artificiale. Durante tutto l'anno, offrono molti eventi diversi ai loro clienti. Alcuni di questi sono eventi di stile di fiera in cui hanno molti partner sono disponibili e forniscono dettagli su nuovi prodotti, tendenze di mercato e servizi. Altri si verificano durante tutto l'anno e sono webinar rapidi che vengono usati per fornire dettagli sui singoli prodotti.

Contoso vuole usare Power Platform per creare una soluzione di gestione degli eventi che può usare per gestire i diversi eventi che ospitano nel corso dell'anno.

In questo esercizio si crea una soluzione che verrà usata per Application Lifecycle Management (ALM) e per raggruppare tutte le diverse app, siti e flussi creati insieme in modo che possano essere facilmente gestiti e trasportati.

Il tempo stimato per completare questo esercizio è **compreso tra 15 e 20** minuti.

Al termine di questo esercizio, si eseguiranno le operazioni seguenti:

- Creare una soluzione di gestione degli eventi
- Aggiungere le tabelle Account e Contact esistenti alla soluzione.
- Creare una nuova tabella denominata Eventi dall'interno della soluzione.

## Attività 1: Creare una soluzione di gestione degli eventi

1.  Apri [Power Apps Maker Portal](https://make.powerapps.com).
1.  Passare a **Soluzioni**.
1.  Sulla barra dei comandi selezionare **+Nuova soluzione.**
1.  Nella schermata della nuova soluzione configurare come segue:
    - **Nome visualizzato:** Gestione eventi
    - **Nome:** EventManagement
1.  In **Server di pubblicazione** selezionare **+ Nuovo server di pubblicazione**
1.  Configurare il nuovo server di pubblicazione come indicato di seguito
    - **Nome visualizzato:** EventMSLearn
    - **Nome:** EventMSLearn
    - **Prefisso:** mslearn
    - **Prefisso del valore di scelta:** lasciare il valore predefinito

    ![Screenshot della schermata Crea nuovo server di pubblicazione.](media/61fa62c324d424f7c73c8291a0724130.png)

1.  Selezionare il **pulsante Salva** per salvare l'autore.
1.  **Nel campo Server di pubblicazione** selezionare l'editore **EventMSlearn** appena creato.
1.  Selezionare **Imposta come soluzione** preferita.

    ![Screenshot della soluzione completata](media/f968526926661bfa401f10742e6f376f.png)

1.  Selezionare **Crea** per creare la soluzione.

## Attività 2: Aggiungere componenti esistenti a una soluzione.

Ora che è stata creata una soluzione per l'archiviazione dei componenti, verranno aggiunte alcune tabelle esistenti. Verranno aggiunte le tabelle Account e Contatto, in modo che possano essere usate facilmente nelle diverse app, flussi e siti di Gestione eventi. Prima di tutto, aggiungeremo la tabella Account alla soluzione.

1.  Se necessario, passare alla **soluzione Gestione** eventi creata nell'attività precedente.
1.  Sulla barra** dei **comandi selezionare **Aggiungi esistente.**
1.  Dal menu visualizzato selezionare **Tabella.**
1.  Selezionare la **tabella Account** , quindi selezionare **Avanti.**
1.  Nella **schermata Tabelle** selezionate selezionare **Includi tutti gli oggetti.**
1.  Selezionare **Aggiungi**.

    Ora che è disponibile la tabella Account, aggiungeremo la tabella Contact.

1.  Sulla barra dei **comandi selezionare di nuovo il **pulsante Aggiungi esistente**.**
1.  Dal menu visualizzato selezionare **Tabella.**
1.  Selezionare la **tabella Contatto** , quindi selezionare **Avanti.**
1.  Nella **schermata Tabelle** selezionate selezionare **Includi tutti gli oggetti**
1.  Seleziona **Aggiungi**

    ![Screenshot che mostra le tabelle Account e Contact nella soluzione.](media/a53817e242fca7371765583d9e565c36.png)

Congratulazioni. È stata creata una nuova soluzione usando Power Platform. Si continuerà a usare la soluzione per aggiungere altri componenti.
