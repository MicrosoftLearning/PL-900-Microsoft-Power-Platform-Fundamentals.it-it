---
lab:
  title: "Lab 3: Come creare un'app canvas"
  module: 'Module 3: Get started with Power Apps'
ms.openlocfilehash: 0ac0874e80deb74b8a4cf0c8075adf6c9b14e375
ms.sourcegitcommit: fc79a9b68a8235b37fd90ef84ba8ae1aa2e581f5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2022
ms.locfileid: "144424771"
---
# <a name="module-3-get-started-with-power-apps"></a>Modulo 3: Introduzione a Power Apps
## <a name="lab-1-how-to-build-a-canvas-app"></a>Lab 1: Come creare un'app canvas

# <a name="scenario"></a>Scenario

Il Bellows College è un'organizzazione didattica con più edifici nel proprio campus. Le visite al campus sono attualmente registrate su documenti cartacei. Le informazioni non vengono acquisite in modo coerente e non esiste un sistema per raccogliere e analizzare i dati sulle visite in tutto il campus.

Attualmente l'amministrazione del campus usa un foglio di calcolo di Excel per tenere traccia della registrazione dei visitatori. Vorrebbe modernizzare il proprio sistema di registrazione dei visitatori, facendo controllare l'accesso agli edifici dal personale addetto alla sicurezza e richiedendo una preregistrazione di tutte le visite da parte degli ospiti.

Durante questo corso verranno sviluppate applicazioni e si useranno le funzionalità di automazione per consentire al personale amministrativo e addetto alla sicurezza del Bellows College di gestire e controllare l'accesso agli edifici del campus.

# <a name="high-level-lab-steps"></a>Procedura generale per il lab

Verrà usata la sequenza seguente per progettare l'app canvas:

-   Creare un'app canvas dai dati nella tabella Visit

-   Configurare la modalità di visualizzazione delle visite nella schermata di esplorazione

-   Apportare alcune modifiche di base all'app

-   Testare la funzionalità dell'app

## <a name="prerequisites"></a>Prerequisiti

-   Completamento del **lab 0 del modulo 0 - Convalidare l'ambiente lab**

# <a name="exercise-1-create-visits-app"></a>Esercizio \#1: Creare l'app per le visite

**Obiettivo:** In questo esercizio si creerà un'app canvas connettendo la tabella Visit iniziale creata in precedenza.

## <a name="task-1-create-a-visits-app"></a>Attività \#1: Creare l'app per le visite

1.  Accedere a <https://make.powerapps.com>. Potrebbe essere necessario ripetere l'autenticazione. Fare clic su **Accedi** e seguire le istruzioni se richiesto.

2.  Selezionare l'ambiente **[iniziali] Practice** in alto a destra, se non è già selezionato.

3.  Se necessario, fare clic sull'icona **Home** sul lato destro della schermata. Nella sezione **Inizia da** selezionare **Dataverse**.

4.  Selezionare la connessione a Dataverse. 

>   **NOTA:** *se non esiste una connessione a Dataverse:*
>   -   Selezionare **Nuova connessione**
>   -   Individuare **Microsoft Dataverse**
>   -   Fare clic su **Crea**

5.  Individuare e selezionare la tabella **Visit** creata nel lab precedente.

6.  Scegliere il pulsante **Connetti**.

7.  Dopo aver creato l'app, nella schermata Benvenuto in Power Apps Studio selezionare la casella **Non visualizzare più questo messaggio** e quindi selezionare **Ignora**.

8.  Al termine della creazione, dovrebbe essere simile all'immagine seguente.

![App canvas creata dai dati Visit.](media/2-canvas-app-from-data.png)

Congratulazioni, è stata creata correttamente un'app Power Apps da una tabella Dataverse. Il passaggio successivo del processo consiste nel personalizzare l'app per il college. La serie successiva di passaggi illustra come implementare alcune personalizzazioni aggiuntive per l'app.

## <a name="task-2-modify-and-theme-the-newly-created-app"></a>Attività \#2: Modificare il tema della nuova app creata

1.  Selezionare il nome dell'app **Visits**.

3.  Sul lato destro della schermata, nella scheda Proprietà, aggiornare la proprietà del controllo **Testo** impostandola su **"Bellows College Visits"** .

4. Nelle proprietà modificare le **dimensioni del carattere** su **24**.

4.  Usando la struttura di spostamento a sinistra, selezionare **DetailsScreen1**.

5.  Selezionare il titolo **Visits**.

6.  Sul lato destro della schermata, nella scheda Proprietà, aggiornare la proprietà del controllo **Testo** impostandola su **"Visit Details"** .

7.  Usando la struttura di spostamento a sinistra, selezionare **EditScreen1**.

8.  Selezionare il titolo **Visits**.

9.  Sul lato destro della schermata, nella scheda Proprietà, sostituire il testo Tabella1 nella proprietà del controllo **Testo** con **"Edit Details".**

10. Usando la struttura di spostamento a sinistra, selezionare **BrowseScreen1**.

11. Nella barra degli strumenti dei comandi selezionare il pulsante **Tema** e nell'elenco visualizzato selezionare il colore del tema **Rosso**.

## <a name="task-3-test-your-visits-app"></a>Attività \#3: Testare l'app Visits

In questa attività si configurerà un modulo per modificare le informazioni sulle singole visite.

1.  Con l'applicazione aperta in Progettazione app selezionare **File**, aggiornare il nome dell'app in **Visits App** e selezionare **Salva**.

2.  Dopo aver salvato l'app, usare la freccia **indietro** per tornare all'app.

3.  Nella finestra di progettazione dell'app selezionare il pulsante **anteprima dell'app** (icona Play) sulla barra dei comandi. *È anche possibile visualizzare l'anteprima dell'app premendo F5.*

4.  Dopo aver aperto l'app, nel campo **Cerca elementi** immettere il testo **Maria**
     *(Si noti come gli elementi nella raccolta vengono filtrati in base a ciò che viene digitato nel campo di ricerca).*

5.  Quando viene visualizzato il record **Contoso Suites** per **Maria Campbell**, fare clic sulla **freccia destra** del record per passare alla schermata **Visit Details**. (**Nota**: *se vengono visualizzati più record di Contoso Suites Maria Campbell, selezionarne uno*)

6.  Per modificare il record, selezionare l'**icona a forma di matita** nell'angolo superiore destro dell'app.

7.  Nella parte superiore della schermata fare clic sull'icona **X** per tornare alla schermata **Dettagli proprietà**

8.  Fare clic sulla **freccia sinistra** per tornare alla schermata Sfoglia.

9. Selezionare **File** e quindi **Salva**.

10. Selezionare **Pubblica**.

# <a name="challenges"></a>Problematiche

-   Aggiungere le colonne seguenti ai moduli in DetailScreen1 e EditScreen1: Actual Start, Actual End, Code, Scheduled Start e Scheduled End
