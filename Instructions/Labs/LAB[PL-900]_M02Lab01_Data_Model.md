---
lab:
  title: 'Lab 1: Modellazione dei dati'
  module: 'Module 2: Introduction to Microsoft Dataverse'
---

# Lab 1: Modellazione dei dati

**Tenant WWL - Condizioni per l'utilizzo** Se viene fornito un tenant come parte di un recapito di formazione con docente, si noti che il tenant viene reso disponibile allo scopo di supportare i lab pratici nella formazione con docente. I tenant non devono essere condivisi o usati per scopi esterni ai lab pratici. Il tenant usato in questo corso è un tenant di valutazione e non può essere usato o accessibile dopo che la classe è finita e non sono idonei per l'estensione. I tenant non devono essere convertiti in una sottoscrizione a pagamento. I tenant ottenuti come parte di questo corso rimangono la proprietà di Microsoft Corporation e ci si riserva il diritto di ottenere l'accesso e la ripossess in qualsiasi momento. 

## Scenario

Il Bellows College è un'organizzazione didattica con più edifici nel proprio campus. Le visite al campus sono attualmente registrate su documenti cartacei. Le informazioni non vengono acquisite in modo coerente e non esiste un sistema per raccogliere e analizzare i dati sulle visite in tutto il campus.

L'amministrazione del campus vorrebbe modernizzare il proprio sistema di registrazione dei visitatori, facendo controllare l'accesso agli edifici dal personale addetto alla sicurezza e richiedendo una preregistrazione di tutte le visite da parte degli ospiti.

Durante questo corso verranno sviluppate applicazioni e si useranno le funzionalità di automazione per consentire al personale amministrativo e addetto alla sicurezza del Bellows College di gestire e controllare l'accesso agli edifici del campus.

In questo lab verrà creato un modello di dati per supportare i requisiti seguenti:

- R1 : tenere traccia delle informazioni per le visite pianificate al campus.

- R2: registrare le informazioni di base per identificare e tenere traccia dei visitatori.

- R3: pianificare, registrare e gestire le visite.

Verranno infine importati dati di esempio in Microsoft Dataverse.

Procedura generale per il lab

Per preparare gli ambienti di apprendimento:

- Fare riferimento al [documento del modello di dati](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Allfiles/Campus%20Management.png) per una descrizione dei metadati, ovvero tabelle e relazioni. È possibile tenere premuto CTRL+ clic con il pulsante sinistro del mouse o fare clic con il pulsante destro del mouse sul collegamento per aprire il documento del modello di dati in una nuova finestra.
- Creare la tabella Visit
- Importare i dati di Visit usando un foglio di calcolo di Excel


## Prerequisiti

- Completamento del **lab 0 del modulo 0 - Convalidare l'ambiente lab**

Aspetti da considerare prima di iniziare

- Convenzioni di denominazione - digitare i nomi con attenzione.

Esercizio 1: Creare una nuova tabella

**Obiettivo:** In questo esercizio verrà creata la nuova tabella personalizzata per le visite.

Attività n. 1: Creare tabelle e colonne visit

La tabella **Visit** conterrà informazioni sulle visite al campus, inclusi visitatore, ora pianificata e ora effettiva di ogni visita.

Vogliamo assegnare a ogni visita un numero univoco che possa essere immesso e interpretato facilmente da un visitatore quando richiesto durante il processo di check-in per la visita.

1.  Se non è già stato eseguito l'accesso, accedere <https://make.powerapps.com> 

1.  Nel menu **Ambiente** in alto a destra verificare che l'ambiente **di pratica** sia selezionato. 

1.  Usando lo spostamento a sinistra, selezionare **Tabelle**.

1.  Selezionare **+ Nuova tabella** e scegliere **+ Nuova tabella**. 

1.  Per **Nome visualizzato** immettere `Visit`

1.  Selezionare **Salva**. 

1.  Nella sezione **Schema** selezionare **Colonne**. 

# Creare la colonna Scheduled Start

1.  Selezionare **+ Nuova colonna**. 

1.  Immettere `Scheduled Start` per **Nome visualizzato**. 

1.  Selezionare **Data e ora** per **Tipo di dati**. 

1.  Modificare **Obbligatorio** in **Business obbligatorio**. 

1.  Espandere **Opzioni avanzate**. 

1.  In **Regolazione fuso orario** selezionare **Fuso orario indipendente**. 

    > **Nota:** Usiamo il comportamento **indipendente del fuso** orario per registrare le informazioni di data e ora, perché l'ora di una visita è sempre locale per la posizione dell'edificio e non deve cambiare quando viene visualizzato da un fuso orario diverso. 

1.  Selezionare **Salva**. 

# Creare la colonna Scheduled End

1.  Selezionare **+ Nuova colonna**. 

1.  Immettere `Scheduled End` per **Nome visualizzato**.

1.  Selezionare **Data e ora** per **Tipo di dati**.

1.  In **Obbligatorio** selezionare **Obbligatorio per l'azienda**.

1.  Espandere **Opzioni avanzate**.

1.  In **Regolazione fuso orario** selezionare **Fuso orario indipendente**.

1.  Selezionare **Salva**. 

# Creare la colonna Actual Start

1.  Selezionare **+ Nuova colonna**. 

1.  Immettere `Actual Start` per **Nome visualizzato**.

1.  Selezionare **Data e ora** per **Tipo di dati**.

1.  In **Obbligatorio** mantenere **Facoltativo**.

1.  Espandere **Opzioni avanzate**.

1.  In **Regolazione fuso orario** selezionare **Fuso orario indipendente**. 

1.  Selezionare **Salva**. 

# Creare la colonna Actual End

1.  Selezionare **+ Nuova colonna**.

1.  Immettere **Actual End** in **Nome visualizzato**.

1.  Selezionare **Data e ora** per **Tipo di dati**.

1.  In **Obbligatorio** mantenere **Facoltativo**.

1.  Espandere **Opzioni avanzate**.

1.  In **Regolazione fuso orario** selezionare **Fuso orario indipendente**.

1.  Selezionare **Salva**.

# Creare la colonna Code

1.  Selezionare **+ Nuova colonna**.

1.  Immettere `Code` per **Nome visualizzato**.

1.  Selezionare **Numerazione automatica** per **Tipo di dati**.

1.  Selezionare **Numero prefisso data** per **Tipo di numerazione automatica**.

1.  Selezionare **Salva**. 

# Creare la colonna di ricerca Visitor

1.  Selezionare **+ Nuova colonna**.

1.  Immettere `Visitor` per **Nome visualizzato**.

1.  Selezionare **Ricerca** in **Tipo di dati**. 

1.  Selezionare **Contatto** in **Tabella correlata**. 

1.  Espandere **Opzioni avanzate**. 

1.  Immettere `visitor_id` per **Nome relazione**. 

1.  Selezionare **Salva**.


Esercizio 2: Importare dati

**Obiettivo:** in questo esercizio si importeranno dati di esempio nel database Dataverse.

### Attività \#1: Caricare il file di Excel in OneDrive

1.  Nella macchina virtuale dovrebbe essere memorizzato il file **Visits.xlsx** in **C:/LabFiles**. In caso contrario, scaricare [Visits.xls](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/Visits.xlsx).

2.  Se non è già stato eseguito l'accesso, accedere a [https://make.powerapps.com](https://make.powerapps.com/). 

3.  Selezionare l'ambiente **[iniziali] Practice** in alto a destra, se non è già selezionato.

4.  Selezionare il pulsante Waffle nell'angolo superiore sinistro per modificare le applicazioni e selezionare **OneDrive**. La configurazione di OneDrive potrebbe richiedere qualche minuto. Selezionare **OneDrive pronto** quando viene visualizzato sullo schermo.

5.  Selezionare **Carica** dal menu in alto e selezionare **File**.

6.  Individuare e selezionare il file **Visits.xlsx** e selezionare **Apri**.

    > **Nota:** questo file si trova nella cartella **Tutti i file** nel computer.


### Attività \#2: Creare un flusso di dati

1.  Se non si è già connessi, accedere <https://make.powerapps.com> 

2.  Dal menu **Ambiente** in alto a destra verificare che l'ambiente **Practice** sia selezionato. 

3.  Usando lo spostamento a sinistra, selezionare **Tabelle**. 

4.  Aprire la tabella **Visit** creata nell'esercizio precedente. 

5.  Usando il menu in alto selezionare **Importa** > **dati**.

6.  Nella finestra di dialogo **Scegli origine dati** selezionare **Cartella di lavoro di Excel**.

7.  Selezionare l'opzione **Collegamento al file**. Selezionare **Sfoglia OneDrive**. Se richiesto, eseguire l'accesso con le proprie credenziali di Microsoft 365. Configurare il browser per consentire sempre popup. 

8.  Selezionare il file **Visits.xlsx** caricato in OneDrive nell'attività precedente. 

9.  Selezionare **Avanti**. 

10. Nella schermata Power **query** > **Scegliere dati** selezionare la cartella di lavoro **Visite** di Excel. 

11. Selezionare **Avanti**. Non uscire da questa pagina.

12. Selezionare **Avanti**. 

13. Nella sezione **Tabelle mappa** in **Impostazioni di caricamento** selezionare **Carica nella tabella esistente**. 

14. Nel menu a discesa **Tabella destinazione** selezionare la tabella **crXXX_Visit** (Dove XXX è un set casuale di lettere e numeri)

15. Nella sezione **Mapping colonne** eseguire il mapping delle colonne alle colonne di destinazione corrispondenti:

    | Colonne di destinazione  | Valori di origine   |
    |:---------------------|:----------------|
    | crxxx_ActualEnd      | fine effettiva      |
    | crxxx_ActualStart    | inizio effettivo    |
    | crxxx_Code           | codice            |
    | crxxx_Name           | name            |
    | crxxx_ScheduledEnd   | fine pianificata   |
    | crxxx_ScheduledStart | inizio pianificato |

16. Selezionare **Avanti**. 

17. Selezionare **Aggiorna manualmente**. 

18. Selezionare **Pubblica**. 

    > **Nota:** per l'importazione dei dati nella tabella potrebbero essere necessari alcuni minuti. Non preoccuparsi se vengono segnalati errori. È normale e non influiranno sul resto del corso.


Attività 3: Verificare l'importazione dei dati

1.  Dopo l'importazione dei dati, usare lo spostamento a sinistra della schermata per selezionare **Tabelle** e aprire la tabella **Visita** .

2.  Verificare che i dati importati siano visualizzati nella sezione **Visita colonne e dati**.

Congratulazioni, è stata creata correttamente una nuova tabella ed è stata eseguita l'importazione di dati.

