---
lab:
  title: 'Lab 1: Modellazione dei dati'
  module: 'Module 2: Introduction to Microsoft Dataverse'
ms.openlocfilehash: 9edefbdf214d5a0f2e0693ffdf024dfc05c032c5
ms.sourcegitcommit: dbffa13e13419f5b9aadc894eb95fd16215b2ebf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2022
ms.locfileid: "146458363"
---
# <a name="module-2-introduction-to-microsoft-dataverse"></a>Modulo 2: Introduzione a Microsoft Dataverse

# <a name="scenario"></a>Scenario

Il Bellows College è un'organizzazione didattica con più edifici nel proprio campus. Le visite al campus sono attualmente registrate su documenti cartacei. Le informazioni non vengono acquisite in modo coerente e non esiste un sistema per raccogliere e analizzare i dati sulle visite in tutto il campus.

L'amministrazione del campus vorrebbe modernizzare il proprio sistema di registrazione dei visitatori, facendo controllare l'accesso agli edifici dal personale addetto alla sicurezza e richiedendo una preregistrazione di tutte le visite da parte degli ospiti.

Durante questo corso verranno sviluppate applicazioni e si useranno le funzionalità di automazione per consentire al personale amministrativo e addetto alla sicurezza del Bellows College di gestire e controllare l'accesso agli edifici del campus.

In questo lab si accederà all'ambiente predisposto in precedenza e verranno creati un database Microsoft Dataverse e una soluzione per tenere traccia delle modifiche. Verrà anche creato un modello di dati a supporto dei requisiti seguenti:

-   R1. Tenere traccia delle informazioni per le visite al campus pianificate

-   R2. Registrare informazioni di base per identificare i visitatori e tenerne traccia

-   R3. Pianificare, registrare e gestire le visite

Verranno infine importati dati di esempio in Microsoft Dataverse.

# <a name="high-level-lab-steps"></a>Procedura generale per il lab

Per preparare gli ambienti di apprendimento:

* Verranno creati una soluzione e un editore
* Verranno aggiunti i componenti nuovi ed esistenti necessari per soddisfare i requisiti dell'applicazione. Fare riferimento al [documento del modello di dati](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Allfiles/Campus%20Management.png) per una descrizione dei metadati, ovvero tabelle e relazioni. È possibile tenere premuto CTRL e fare clic o clic con il pulsante destro del mouse sul collegamento per aprire il documento del modello di dati in una nuova finestra.
* Creare la tabella Visit
* Importare i dati per la tabella Visit usando un foglio di calcolo di Excel

## <a name="prerequisites"></a>Prerequisiti:

-   Completamento del **lab 0 del modulo 0 - Convalidare l'ambiente lab**

## <a name="things-to-consider-before-you-begin"></a>Aspetti da considerare prima di iniziare:

-   Convenzioni di denominazione - digitare i nomi con attenzione.

# <a name="exercise-1-create-new-table"></a>Esercizio \#1: Creare una nuova tabella

**Obiettivo:** In questo esercizio verrà creata la nuova tabella personalizzata per le visite. 

## <a name="task--1-create-visit-table-and-columns"></a>Attività \#1: Creare la tabella Visit e le colonne

La tabella **Visit** conterrà informazioni sulle visite al campus, inclusi visitatore, ora pianificata e ora effettiva di ogni visita.

Vogliamo assegnare a ogni visita un numero univoco che possa essere immesso e interpretato facilmente da un visitatore quando richiesto durante il processo di check-in per la visita.

>   Usiamo il comportamento **Indipendente dal fuso orario** per registrare le informazioni di data e ora, perché l'ora di una visita è sempre locale rispetto alla posizione dell'edificio e non deve cambiare se visualizzata da un fuso orario diverso.

1. Accedere a [https://make.powerapps.com](https://make.powerapps.com/) se l'accesso non è già stato effettuato

2. Selezionare l'ambiente **[iniziali] Practice** in alto a destra, se non è già selezionato.

3. Usando il riquadro di spostamento a sinistra, espandere Dataverse e selezionare Tabelle.

4. Fare clic su **Nuova tabella**.

5. Immettere **Visit** in **Nome visualizzato**.

6. Fare clic su **Save** (Salva). Verrà avviato il provisioning della tabella in background e sarà possibile iniziare ad aggiungere altre colonne.

7. Una volta creata la tabella, nella sezione **Schema** selezionare **Colonne**. 

8. Selezionare **Nuova colonna** ed eseguire la configurazione nel modo seguente: 

    - Immettere **Scheduled Start** in **Nome visualizzato**.

    - Selezionare **Data e ora** per **Tipo di dati**.

    - In **Obbligatorio** selezionare **Obbligatorio per l'azienda**.

    - Espandere la sezione **Opzioni avanzate**.

    - In **Comportamento** selezionare **Indipendente dal fuso orario**.

    - Fare clic su **Salva**.

9. Creare la colonna Scheduled End 

    - Fare clic su **Aggiungi colonna**.

    - Immettere **Scheduled End** in **Nome visualizzato**.

    - Selezionare **Data e ora** per **Tipo di dati**.

    - In **Obbligatorio** selezionare **Obbligatorio per l'azienda**.

    - Espandere la sezione **Opzioni avanzate**.

    - In **Comportamento** selezionare **Indipendente dal fuso orario**.

    - Fare clic su **Salva**.

10. Creare la colonna Actual Start

    - Fare clic su **Aggiungi colonna**.

    - Immettere **Actual Start** in **Nome visualizzato**.

    - Selezionare **Data e ora** per **Tipo di dati**.

    - In **Obbligatorio** mantenere **Facoltativo**.

    - Espandere la sezione **Opzioni avanzate**.

    - In **Comportamento** selezionare **Indipendente dal fuso orario**.

    - Fare clic su **Salva**.

11. Creare la colonna Actual End

    - Fare clic su **Aggiungi colonna**.

    - Immettere **Actual End** in **Nome visualizzato**.

    - Selezionare **Data e ora** per **Tipo di dati**.

    - In **Obbligatorio** mantenere **Facoltativo**.

    - Espandere la sezione **Opzioni avanzate**.

    - In **Comportamento** selezionare **Indipendente dal fuso orario**.

    - Fare clic su **Salva**.

12. Creare la colonna Code

    - Fare clic su **Aggiungi colonna**.

    - Immettere **Code** in **Nome visualizzato**.

    - Selezionare **Numerazione automatica** per **Tipo di dati**.

    - Selezionare **Numero prefisso data** per **Tipo di numerazione automatica**.

    - Fare clic su **Salva**.

13. Creare la colonna di ricerca Visitor

    - Fare clic su **Aggiungi colonna**.

    - Immettere **Visitor** in **Nome visualizzato**.

    - Selezionare **Ricerca** in **Tipo di dati**.

    - Selezionare **Contatto** in **Tabella correlata**.

    - Espandere la sezione **Opzioni avanzate**.

    - Immettere **visitor_id** per **Nome relazione**.

    - Fare clic su **Salva**.

 

Esercizio 2. Importare dati

**Obiettivo:** in questo esercizio si importeranno dati di esempio nel database Dataverse.

Attività 1: Importare il file Visits.xls.

In questa attività verranno importati i dati sulle visite da un file di Excel.

1. È necessario avere a disposizione il file **Visits.xls** archiviato nel desktop. Scaricare [Visits.xls](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/Visits.xlsx) se non è disponibile.

2. Se non è già stato eseguito l'accesso, accedere a [https://make.powerapps.com](https://make.powerapps.com/).

3. Selezionare l'ambiente **[iniziali] Practice** in alto a destra, se non è già selezionato.

4. Usando il riquadro di spostamento a sinistra, espandere **Dataverse** e selezionare Tabelle.

Questa operazione può essere visualizzata come Dati > Tabelle sullo schermo.

5. Individuare e aprire la tabella **Visit** creata nell'esercizio precedente.

6. Usando il menu in alto selezionare la freccia verso il basso accanto a **Importa** e selezionare **Importare i dati da Excel**.

7. Nel menu visualizzato selezionare il pulsante **Carica**.

8. Individuare e selezionare il file **Visits.xls** scaricato in precedenza. Si noti che possono essere necessari un paio di minuti per il caricamento del file. Non preoccuparsi se viene visualizzato un messaggio che segnala la presenza di errori di mapping. Questi errori verranno corretti tra poco.

9. Selezionare **Mappa colonne**.

10. Eseguire il mapping delle colonne come indicato di seguito:

| Colonne del database Visit| Valori di origine |
| - |
| Fine effettiva| Actual end |
| Inizio effettivo| Actual start |
| Codice| Codice |
| Nome| Nome |
| Scheduled End| Fine pianificata |
| Start pianificato| Inizio pianificato |


11. Lasciare tutti gli altri campi su **Non impostato**.

12. Nell'angolo superiore destro della schermata selezionare **Salva modifiche**.

13. Nella schermata **Importa dati** verificare che lo stato del mapping sia "Mapping completato".

14. Selezionare **Importa** nell'angolo superiore destro per completare l'importazione dei dati.

**Nota:** per l'importazione dei dati nella tabella potrebbero essere necessari alcuni minuti. Non preoccuparsi se vengono segnalati errori. È normale e non influiranno sul resto del corso.

Attività 2. Verificare l'importazione dei dati

1. Dopo aver importato i dati, usare il riquadro di spostamento a sinistra della schermata per selezionare di nuovo la tabella **Visit**.

2. Verificare che i dati importati siano visualizzati nella sezione **Visita colonne e dati**. 

Congratulazioni, è stata creata correttamente una nuova tabella ed è stata eseguita l'importazione di dati.
