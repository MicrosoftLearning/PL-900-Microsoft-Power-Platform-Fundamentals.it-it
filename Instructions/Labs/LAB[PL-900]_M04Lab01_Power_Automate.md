---
lab:
  title: 'Lab 6: Come creare una soluzione automatizzata'
  module: 'Module 4: Get Started with Power Automate'
ms.openlocfilehash: c37bbf2975aa1964493e93716d0b3aeb32030c99
ms.sourcegitcommit: fc79a9b68a8235b37fd90ef84ba8ae1aa2e581f5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2022
ms.locfileid: "144424638"
---
# <a name="module-4-get-started-with-power-automate"></a>Modulo 4: Introduzione a Power Automate
## <a name="lab-how-to-build-an-automated-solution"></a>Laboratorio: Come creare una soluzione automatizzata

## <a name="scenario"></a>Scenario

Il Bellows College è un'organizzazione didattica con più edifici nel proprio campus. I visitatori del campus sono attualmente registrati su documenti cartacei. Le informazioni non vengono acquisite in modo coerente e non esiste un sistema per raccogliere e analizzare i dati sulle visite in tutto il campus.

L'amministrazione del campus vorrebbe modernizzare il proprio sistema di registrazione dei visitatori, facendo controllare l'accesso agli edifici dal personale addetto alla sicurezza e richiedendo una preregistrazione di tutte le visite da parte degli ospiti.

Durante questo corso verranno sviluppate applicazioni e si useranno le funzionalità di automazione per consentire al personale amministrativo e addetto alla sicurezza del Bellows College di gestire e controllare l'accesso agli edifici del campus.

In questo lab verranno creati flussi di Power Automate per automatizzare le varie parti della gestione del campus.

# <a name="high-level-lab-steps"></a>Procedura generale per il lab

Per completare il progetto sono stati identificati i requisiti seguenti:

-   Il personale addetto alla sicurezza deve ricevere notifica nel caso i visitatori prolunghino la visita oltre il periodo pianificato.

## <a name="prerequisites"></a>Prerequisiti

-   Completamento del **lab 0 del modulo 0 - Convalidare l'ambiente lab**

-   Completamento del **lab 1 del modulo 2 - Introduzione a Microsoft Dataverse**

-   Contatto John Doe creato con un indirizzo di posta elettronica personale in

## <a name="things-to-consider-before-you-begin"></a>Aspetti da considerare prima di iniziare

-   Come si possono misurare i prolungamenti delle visite e applicare criteri rigidi?

# <a name="exercise-1-create-visit-notification-flow"></a>Esercizio \#1: Creare un flusso di notifica visita

**Obiettivo:** in questo esercizio verrà creato un flusso di Power Automate che implementa il requisito. Il visitatore deve ricevere un'e-mail con il codice univoco assegnato alla visita.

## <a name="task-1-create-a-flow"></a>Attività \#1: Creare un flusso

1.  Accedere a <https://make.powerapps.com>. Potrebbe essere necessario ripetere l'autenticazione. Fare clic su **Accedi** e seguire le istruzioni se richiesto.

2.  Selezionare l'ambiente **[iniziali] Practice** in alto a destra, se non è già selezionato.

2.  Nel riquadro di spostamento a sinistra selezionare **Flussi**.

4.  Se richiesto, selezionare **Attività iniziali**.

5.  Fare clic su **Nuovo flusso** e selezionare **Flusso cloud automatizzato**.

6.  In **Scegliere il trigger del flusso** cercare **Dataverse**.

7.  Selezionare il trigger **When a row is added, modified or deleted** (Quando una riga viene aggiunta, modificata o eliminata) e quindi fare clic su **Crea**.

8.  Popolare le condizioni di trigger per il flusso:

    1.  Selezionare **Aggiunte** per **Tipo di modifica**

    2.  Selezionare **Visit** per **Nome tabella**.

    3.  Selezionare **Organizzazione** per **Ambito**.

    4.  Nel passaggio del trigger fare clic sui puntini di sospensione ( **...** ) e fare clic su **Rinomina**.
        Rinominare il trigger **"When a visit is added"** (Quando viene aggiunta una visita). Questa è una procedura consigliata, per consentire all'utente e agli altri editor del flusso di comprendere lo scopo del passaggio senza dover esaminare i dettagli.

## <a name="task-2-create-a-step-to-get-the-visitor-row"></a>Attività \#2: Creare un passaggio per ottenere la riga del visitatore

1.  Selezionare **Nuovo passaggio**. Questo passaggio è necessario per recuperare le informazioni sui visitatori, incluso l'indirizzo e-mail.

2.  Cercare **Dataverse**.

3.  Selezionare l'azione **Recupera una riga tramite ID**.

4.  Selezionare **Contatti** per **Nome tabella**.

5.  Nel campo **ID riga** selezionare **Visitor (Valore)** nell'elenco del contenuto dinamico.

6.  In questa azione fare clic sui puntini di sospensione ( **...** ) e scegliere **Rinomina**.
        Rinominare l'azione **"Get the Visitor"** . Questa è una procedura consigliata, per consentire all'utente e agli altri editor del flusso di comprendere lo scopo del passaggio senza dover esaminare i dettagli.

## <a name="task-3-create-a-step-to-send-an-email-to-the-visitor"></a>Attività \#3: Creare un passaggio per inviare un messaggio di posta elettronica al visitatore

1.  Fare clic su **Nuovo passaggio**. Questo è il passaggio che creerà e invierà l'e-mail al visitatore.

2.  Cercare *mail*, selezionare il connettore **Office 365 Outlook** e l'azione **Invia un messaggio di posta elettronica (v2)** .

3.  Se viene richiesto di accettare i termini e le condizioni per usare questa azione, fare clic su **Accetta**.

4.  Selezionare **Aggiungi contenuto dinamico** nel campo **A**. 
    
5.  Selezionare **Posta elettronica** nell'elenco del contenuto dinamico.
        > Notice that it is beneath the **Get the visitor** header. This means you
        are selecting the Email that is related to the Visitor that you looked
        up in the previous step.

5.  Immettere **Your scheduled visit to Bellows College** nel campo **Oggetto**.

6.  Immettere il testo seguente in **Corpo**:

>   Il contenuto dinamico deve essere inserito nei campi con nome tra parentesi graffe. È consigliabile copiare e incollare prima tutto il testo e poi aggiungere il contenuto dinamico nelle posizioni corrette.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
   Dear {First Name},

   You are currently scheduled to visit Bellows Campus from {Scheduled Start} until {Scheduled End}.

   Best regards,

   Campus Administration
   Bellows College
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

7.  Evidenziare il testo **{First Name}** . Sostituirlo con il campo **First Name** del passaggio **Get the Visitor** .

8.  Evidenziare il testo **{Scheduled Start}** . Sostituirlo con il campo **Scheduled Start** del passaggio **Get the Visitor** .

9.  Evidenziare il testo **{Scheduled End}** . Sostituirlo con il campo **Scheduled End** del passaggio **Get the Visitor** .

10.  Selezionare il nome di flusso in alto e rinominarlo `Visit
        Notification`.

11.  Fare clic su **Save** (Salva).

Lasciare questa scheda del flusso aperta per la prossima attività. Il flusso dovrebbe essere simile al seguente:

![Esempio di passaggi del flusso.](media/4-Flow.png)

## <a name="task-2-validate-and-test-the-flow"></a>Attività \#2: Convalidare e testare il flusso

1.  Aprire una nuova scheda nel browser e passare a <https://make.powerapps.com>.

2.  Selezionare l'ambiente **[iniziali] Practice** in alto a destra, se non è già selezionato.

3.  Fare clic su **App** e selezionare l'app **Campus Management Model-driven** creata in precedenza.

3.  Lasciare aperta questa scheda e tornare alla scheda precedente con il flusso.

4.  Sulla barra dei comandi fare clic su **Test**. Selezionare **Manualmente** e quindi **Salva e verifica**.

5.  Usando la struttura di spostamento a sinistra, selezionare **Visit**.

6. Fare clic sul pulsante **+ Nuovo** per aggiungere un nuovo record **Visit**.

7. Completare il record Visit come segue:

    -   **Nome:** Test Visit

    -   **Visitor:** John Doe

    -   **Scheduled Start:** Domani alle 8:00

    -   **Scheduled End:** Domani alle 9:00

8. Selezionare il pulsante **Salva e chiudi**.

Dopo un breve ritardo, dovrebbe essere visualizzato un messaggio di posta elettronica nella posta in arrivo, dato che è stato specificato l'indirizzo di posta elettronica personale come indirizzo di posta elettronica di John Doe. 

# <a name="challenges"></a>Problematiche

-   Sperimentare con la formattazione nel messaggio di posta elettronica. Come si potrebbe ottenere un aspetto più professionale? 
