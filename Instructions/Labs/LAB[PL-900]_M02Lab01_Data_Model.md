---
lab:
  title: 'Lab 1: Modellazione dei dati'
  module: 'Module 2: Introduction to Microsoft Dataverse'
ms.openlocfilehash: 9e26f2eb6b2e6003510c25b5f66e4f43b30a0640
ms.sourcegitcommit: fc79a9b68a8235b37fd90ef84ba8ae1aa2e581f5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2022
ms.locfileid: "144424691"
---
# <a name="module-2-introduction-to-microsoft-dataverse"></a>Modulo 2: Introduzione a Microsoft Dataverse

# <a name="scenario"></a>Scenario

Il Bellows College è un'organizzazione didattica con più edifici nel proprio campus. Le visite al campus sono attualmente registrate su documenti cartacei. Le informazioni non vengono acquisite in modo coerente e non esiste un sistema per raccogliere e analizzare i dati sulle visite in tutto il campus.

L'amministrazione del campus vorrebbe modernizzare il proprio sistema di registrazione dei visitatori, facendo controllare l'accesso agli edifici dal personale addetto alla sicurezza e richiedendo una preregistrazione di tutte le visite da parte degli ospiti.

Durante questo corso verranno sviluppate applicazioni e si useranno le funzionalità di automazione per consentire al personale amministrativo e addetto alla sicurezza del Bellows College di gestire e controllare l'accesso agli edifici del campus.

In questo lab si accederà all'ambiente predisposto in precedenza e verranno creati un database Microsoft Dataverse e una soluzione per tenere traccia delle modifiche. Verrà anche creato un modello di dati a supporto dei requisiti seguenti:

-   R1. Tenere traccia delle posizioni (edifici) delle visite al campus

-   R2. Registrare informazioni di base per identificare i visitatori e tenerne traccia

-   R3. Pianificare, registrare e gestire le visite

Verranno infine importati dati di esempio in Microsoft Dataverse.

# <a name="high-level-lab-steps"></a>Procedura generale per il lab

Per preparare gli ambienti di apprendimento:

* Verranno creati una soluzione e un editore
* Verranno aggiunti i componenti nuovi ed esistenti necessari per soddisfare i requisiti dell'applicazione. Fare riferimento al [documento del modello di dati](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Allfiles/Campus%20Management.png) per una descrizione dei metadati, ovvero tabelle e relazioni. È possibile tenere premuto CTRL e fare clic o clic con il pulsante destro del mouse sul collegamento per aprire il documento del modello di dati in una nuova finestra.
* Creare le tabelle Building e Visit
* Importare i dati per la tabella Visit usando un foglio di calcolo di Excel

## <a name="prerequisites"></a>Prerequisiti:

-   Completamento del **lab 0 del modulo 0 - Convalidare l'ambiente lab**

## <a name="things-to-consider-before-you-begin"></a>Aspetti da considerare prima di iniziare:

-   Convenzioni di denominazione - digitare i nomi con attenzione.

# <a name="exercise-1-create-new-table"></a>Esercizio \#1: Creare una nuova tabella

**Obiettivo:** In questo esercizio verrà creata la nuova tabella personalizzata Visit. 

## <a name="task--1-create-visit-table-and-columns"></a>Attività \#1: Creare la tabella Visit e le colonne

La tabella **Visit** conterrà informazioni sulle visite al campus, inclusi edificio, visitatore, ora pianificata e ora effettiva di ogni visita.

Vogliamo assegnare a ogni visita un numero univoco che possa essere immesso e interpretato facilmente da un visitatore quando richiesto durante il processo di check-in per la visita.

>   Usiamo il comportamento **Indipendente dal fuso orario** per registrare le informazioni di data e ora, perché l'ora di una visita è sempre locale rispetto alla posizione dell'edificio e non deve cambiare se visualizzata da un fuso orario diverso.

1.  Accedere a <https://make.powerapps.com> se l'accesso non è già stato effettuato

2.  Selezionare l'ambiente **[iniziali] Practice** in alto a destra, se non è già selezionato.

3.  Usando il riquadro di spostamento a sinistra, espandere Dataverse e selezionare Tabelle.

4.  Fare clic su **Nuova tabella**.

5.  Immettere **Visit** in **Nome visualizzato**.

6.  Fare clic su **Crea**. Verrà avviato il provisioning della tabella in background e sarà possibile iniziare ad aggiungere altre colonne.

7.  Creare la colonna Scheduled Start

    1.  Dovrebbe essere visualizzata la pagina delle colonne della tabella Visit.

    2.  Assicurarsi che sia selezionata la scheda **Colonne** e fare clic su **Aggiungi colonna**.

    3.  Immettere **Scheduled Start** in **Nome visualizzato**.

    4.  Selezionare **Data e ora** per **Tipo di dati**.

    5.  In **Obbligatorio** selezionare **Obbligatorio**.

    6.  Espandere la sezione **Opzioni avanzate**.

    7.  In **Comportamento** selezionare **Indipendente dal fuso orario**.

    8.  Fare clic su **Fine**.

8.  Creare la colonna Scheduled End

    1.  Fare clic su **Aggiungi colonna**.

    2.  Immettere **Scheduled End** in **Nome visualizzato**.

    3.  Selezionare **Data e ora** per **Tipo di dati**.

    4.  In **Obbligatorio** selezionare **Obbligatorio**.

    5.  Espandere la sezione **Opzioni avanzate**.

    6.  In **Comportamento** selezionare **Indipendente dal fuso orario**.

    7.  Fare clic su **Fine**.

9.  Creare la colonna Actual Start

    1.  Fare clic su **Aggiungi colonna**.

    2.  Immettere **Actual Start** in **Nome visualizzato**.

    3.  Selezionare **Data e ora** per **Tipo di dati**.

    4.  In **Obbligatorio** mantenere **Facoltativo**.

    5.  Espandere la sezione **Opzioni avanzate**.

    6.  In **Comportamento** selezionare **Indipendente dal fuso orario**.

    7.  Fare clic su **Fine**.

10. Creare la colonna Actual End

    1.  Fare clic su **Aggiungi colonna**.

    2.  Immettere **Actual End** in **Nome visualizzato**.

    3.  Selezionare **Data e ora** per **Tipo di dati**.

    4.  In **Obbligatorio** mantenere **Facoltativo**.

    5.  Espandere la sezione **Opzioni avanzate**.

    6.  In **Comportamento** selezionare **Indipendente dal fuso orario**.

    7.  Fare clic su **Fine**.

11. Creare la colonna Code

    1.  Fare clic su **Aggiungi colonna**.

    2.  Immettere **Code** in **Nome visualizzato**.

    3.  Selezionare **Numerazione automatica** per **Tipo di dati**.
    
    4.  Selezionare **Numero prefisso data** per **Tipo di numerazione automatica**.

    5.  Fare clic su **Fine**.

12. Creare la colonna di ricerca Visitor

    1.  Fare clic su **Aggiungi colonna**.

    2.  Immettere **Visitor** in **Nome visualizzato**.

    3.  Selezionare **Ricerca** in **Tipo di dati**.

    4.  Selezionare **Contatto** in **Tabella correlata**.

    5.  Fare clic su **Fine**.

13. Fare clic su **Salva tabella**

# <a name="exercise-2-import-data"></a>Esercizio \#2: Importare dati

**Obiettivo:** in questo esercizio si importeranno dati di esempio nel database Dataverse.

## <a name="task-1-import-the-visitsxls-file"></a>Attività \#1: Importare il file Visits.xls.

In questa attività si importerà una soluzione che contiene il flusso di Power Automate necessario per completare l'importazione dei dati.

1.  È necessario avere a disposizione il file **Visits.xls** archiviato nel desktop. Scaricare [Visits.xls](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/majorupdate_april2022/Allfiles/Visits.xlsx) se non è disponibile.

2.  Se non è già stato eseguito l'accesso, accedere a <https://make.powerapps.com>.

3.  Selezionare l'ambiente **[iniziali] Practice** in alto a destra, se non è già selezionato.

4.  Usando il riquadro di spostamento a sinistra, espandere **Dataverse** e selezionare Tabelle.

5.  Individuare e aprire la tabella **Visit**, creata nell'esercizio precedente.

6.  Usando il menu in alto selezionare la freccia a discesa accanto a **Dati**, selezionare la freccia accanto a **Recupera dati** e quindi selezionare **Recupera dati da Excel**.

7.  Dal menu visualizzato selezionare **Recupera dati** e quindi **Recupera dati da Excel**.

8.  Nel menu visualizzato selezionare il pulsante **Carica**.

9.  Individuare e selezionare il file **Visits.xls** scaricato in precedenza. *(Si noti che possono essere necessari un paio di minuti per il caricamento del file. Non preoccuparsi se viene visualizzato un messaggio che segnala la presenza di errori di mapping. Questi errori verranno corretti tra poco.)*

10. Selezionare **Mappa colonne**.

11. Eseguire il mapping delle colonne come indicato di seguito:

    | Colonne del database Visit | Valori di origine   |
    |------------------|-----------------|
    | Fine effettiva       | Actual end      |
    | Inizio effettivo     | Actual start    |
    | Codice             | Codice            |
    | Nome             | Nome            |
    | Scheduled End    | Fine pianificata   |
    | Start pianificato  | Inizio pianificato |

12. Lasciare tutti gli altri campi su **Non impostato**.

13. Nell'angolo superiore destro della schermata selezionare **Salva modifiche**.

14. Nella schermata **Importa dati** verificare che lo stato del mapping sia Mapping completato e selezionare il pulsante **Importa**.

**Nota:** *per l'importazione dei dati nella tabella potrebbero essere necessari alcuni minuti. Non preoccuparsi se vengono segnalati errori. È normale e non influiranno sul resto del corso.*

## <a name="task-2-verify-data-import"></a>Attività \#2: Verificare l'importazione dei dati

1.  Dopo aver importato i dati, usare il riquadro di spostamento a sinistra della schermata per selezionare di nuovo la tabella **Visit**.

2.  Usando le schede nella parte superiore, selezionare la scheda Dati.

3.  Verificare che nella tabella siano presenti record.

Congratulazioni, sono state create correttamente nuove tabelle ed è stata eseguita l'importazione di dati.
