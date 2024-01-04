---
lab:
  title: 'Lab 1: Modellazione dei dati'
  module: 'Module 2: Introduction to Microsoft Dataverse'
---

# Lab 1: Modellazione dei dati

**Tenant WWL: condizioni per l'utilizzo** Se, come parte della distribuzione di formazione con istruttore, viene fornito un tenant, tenere presente che il tenant viene reso disponibile allo scopo di supportare le esercitazioni pratiche nel training con docente. I tenant non devono essere condivisi o utilizzati per scopi esterni alle esercitazioni pratiche. Il tenant utilizzato in questo corso è un tenant di valutazione e non può essere utilizzato o reso accessibile dopo il termine della lezione e non è idoneo per l'estensione. I tenant non devono essere convertiti in un abbonamento a pagamento. I tenant ottenuti come parte di questo corso rimangono di proprietà di Microsoft Corporation e Microsoft si riserva il diritto di ottenere l'accesso e di riprenderne il possesso in qualsiasi momento. 

## Scenario

Bellows College è un'organizzazione educativa con più edifici nel campus. Attualmente, le visite al campus sono registrate in formato cartaceo. Le informazioni non vengono acquisite in modo coerente e non ci sono mezzi per raccogliere e analizzare i dati sulle visite nell'intero campus.

L'amministrazione del campus vorrebbe modernizzare il proprio sistema di registrazione dei visitatori, facendo controllare l'accesso agli edifici dal personale addetto alla sicurezza e richiedendo una preregistrazione di tutte le visite da parte degli ospiti.

In questo corso verranno create applicazioni ed eseguita l'automazione per consentire al personale amministrativo e di sicurezza di Bellows College di gestire e controllare l'accesso agli edifici del campus.

In questo lab verrà creato un modello di dati per supportare i requisiti seguenti:

- R1: tenere traccia delle informazioni per le visite al campus pianificate

- R2: registrare le informazioni di base per identificare e tenere traccia dei visitatori.

- R3: pianificare, registrare e gestire le visite.

Infine, i dati di esempio verranno importati in Microsoft Dataverse.

Procedura generale per il lab

Per preparare gli ambienti di apprendimento, è possibile:

- Fare riferimento al [documento del modello dati](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Allfiles/Campus%20Management.png) per la descrizione dei metadati (tabelle e relazioni). Per aprire il documento del modello di dati in una nuova finestra, è possibile tenere premuto CTRL e fare clic con il pulsante destro del mouse oppure fare clic con il pulsante destro del mouse sul collegamento.
- Creare la tabella Visit
- Importare i dati per la tabella Visit utilizzando un foglio di calcolo di Excel


## Prerequisiti

- Completamento del **lab 0 del modulo 0 - Convalidare l'ambiente lab**

Aspetti da considerare prima di iniziare

- Convenzioni di denominazione - digitare i nomi con attenzione.

# Esercizio 1: Creare una nuova tabella

**Obiettivo:** in questo esercizio verrà creata la nuova tabella personalizzata per Visits.

## Attività 1: Creare la tabella Visit e le colonne

La tabella **Visit** conterrà informazioni sulle visite al campus, inclusi visitatore, ora pianificata e ora effettiva di ogni visita.

Desideriamo assegnare a ogni visita un numero univoco che può essere facilmente immesso e interpretato da un visitatore quando richiesto durante il processo di registrazione della visita.

1.  Se non è già stato effettuato l'accesso, accedere a <https://make.powerapps.com> 

1.  Dal menu **Ambiente** in alto a destra, verificare che sia selezionato l'ambiente **Pratica**. 

1.  Dalla barra di spostamento a sinistra selezionare **Tabelle**.

1.  Selezionare **+ Nuova tabella** e scegliere **Imposta proprietà avanzate**. 

1.  Per **Nome visualizzato** immettere `Visit`.

1.  Seleziona **Salva**. 

1.  Nella sezione **Schema** selezionare **Colonne**. 


## Creare la colonna Scheduled Start

1.  Selezionare **+ Nuova colonna**. 

1.  Immettere `Scheduled Start` per il **Nome visualizzato** 

1.  Selezionare **Data e ora** per **Tipo di dati**. 

1.  Modificare **Obbligatorio** in **Obbligatorio per l'azienda**. 

1.  Espandi **Opzioni avanzate**. 

1.  In **Regolazione fuso orario** selezionare **Fuso orario indipendente**. 

    > **Nota:** usiamo il comportamento **Indipendente dal fuso orario** per registrare le informazioni di data e ora, perché l'ora di una visita è sempre locale rispetto alla posizione dell'edificio e non deve cambiare se visualizzata da un fuso orario diverso. 

1.  Seleziona **Salva**. 


## Creare una colonna Fine pianificata

1.  Selezionare **+ Nuova colonna**. 

1.  Immettere `Scheduled End` per **Nome visualizzato.**.

1.  Selezionare **Data e ora** per **Tipo di dati**.

1.  In **Obbligatorio** selezionare **Obbligatorio per l'azienda**.

1.  Espandi **Opzioni avanzate**.

1.  In **Regolazione fuso orario** selezionare **Fuso orario indipendente**.

1.  Seleziona **Salva**. 


## Creare la colonna Actual Start

1.  Selezionare **+ Nuova colonna**. 

1.  Immettere `Actual Start` per **Nome visualizzato.**.

1.  Selezionare **Data e ora** per **Tipo di dati**.

1.  In **Obbligatorio** mantenere **Facoltativo**.

1.  Espandi **Opzioni avanzate**.

1.  In **Regolazione fuso orario** selezionare **Fuso orario indipendente**. 

1.  Seleziona **Salva**. 


## Creare la colonna Actual End

1.  Selezionare **+ Nuova colonna**.

1.  Immettere `Actual End` per **Nome visualizzato**.

1.  Selezionare **Data e ora** per **Tipo di dati**.

1.  In **Obbligatorio** mantenere **Facoltativo**.

1.  Espandi **Opzioni avanzate**.

1.  In **Regolazione fuso orario** selezionare **Fuso orario indipendente**.

1.  Seleziona **Salva**.


## Creare la colonna Codice

1.  Selezionare **+ Nuova colonna**.

1.  Immettere `Code` per **Nome visualizzato**.

1.  Selezionare **Numerazione automatica** per **Tipo di dati**.

1.  Selezionare **Numero con prefisso data** in **Tipo di numerazione automatica**.

1.  Seleziona **Salva**. 


## Creare la colonna di ricerca Visitor

1.  Selezionare **+ Nuova colonna**.

1.  Immettere `Visitor` per **Nome visualizzato**.

1.  Selezionare **Ricerca** > **Ricerca** in **Tipo di dati**. 

1.  Selezionare **Contatto** in **Tabella correlata**. 

1.  Espandi **Opzioni avanzate**. 

1.  Immettere `visitor_id` per **Nome relazione**. 

1.  Seleziona **Salva**.


# Esercizio 2: Importare dati

**Obiettivo:** in questo esercizio verranno importati dati di esempio nel database Dataverse.

## Attività \#1: Caricare il file di Excel in OneDrive

1.  Nella macchina virtuale dovrebbe essere memorizzato il file **Visits.xlsx** in **C:/LabFiles**. In caso contrario, scaricare [Visits.xls](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/Visits.xlsx).

2.  Se non è già stato eseguito l'accesso, accedere a [https://make.powerapps.com](https://make.powerapps.com/). 

3.  Selezionare l'ambiente **[iniziali] Practice** in alto a destra, se non è già selezionato.

4.  Selezionare il pulsante Waffle nell'angolo superiore a sinistra per cambiare le applicazioni e selezionare **OneDrive**. La configurazione di OneDrive potrebbe richiedere qualche minuto. Selezionare **OneDrive è pronto** quando viene visualizzato sullo schermo.)

5.  Selezionare **+Aggiungi nuovo** dal menu, quindi selezionare **Carica file**.

6.  Individuare e selezionare il file **Visits.xlsx** e selezionare **Apri**.

    > **Nota:** il file deve trovarsi nella cartella **Desktop** > **Tutti i file** nella macchina virtuale.


## Attività \#2: creare un flusso di dati

1.  Se non è già stato effettuato l'accesso, accedere a <https://make.powerapps.com> 

2.  Dal menu **Ambiente** in alto a destra, verificare che sia selezionato l'ambiente **Pratica**. 

3.  Dalla barra di spostamento a sinistra selezionare **Tabelle**. 

4.  Aprire la tabella **Visit** creata nell'esercizio precedente. 

5.  Usando il menu in alto, selezionare **Importa** > **Importa dati**.

6.  Nella finestra di dialogo **Scegli origine dati** selezionare **Cartella di lavoro di Excel**.

7.  Selezionare l'opzione **Collegamento al file**. Seleziona **Sfoglia OneDrive**. Se richiesto, eseguire l'accesso con le proprie credenziali di Microsoft 365. Configurare il browser per consentire sempre i popup. 

8.  Selezionare il file **Visits.xlsx** caricato in OneDrive nell'attività precedente. 

9.  Selezionare **Avanti**. 

10. Nella schermata **Power Query** > **Scegli dati**, controllare la cartella di lavoro Excel **Visits**. 

11. Selezionare **Avanti**. Non uscire da questa pagina.

12. Selezionare **Avanti**. 

13. Nella sezione **Mapping tabelle**, sotto **Carica impostazioni**, selezionare **Carica in tabella esistente**. 

14. Nel menu a discesa **Tabella di destinazione**, selezionare la tabella **crXXX_visit** (dove XXX è un set casuale di lettere e numeri)

15. Nella sezione **Mapping delle colonne**, eseguire il mapping delle colonne alle colonne di destinazione corrispondenti:

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

    > **Notare:** per l'importazione dei dati nella tabella potrebbero essere necessari alcuni minuti. Non preoccuparsi se vengono segnalati errori. È normale e non influiranno sul resto del corso.


## Attività \#3: Verificare l'importazione dei dati

1.  Dopo aver importato i dati, utilizzare la navigazione a sinistra della schermata per selezionare **Tabelle** e aprire la tabella **Visite**.

2.  Verificare che i dati importati siano visualizzati nella sezione **Visita colonne e dati**.

Congratulazioni, è stata creata correttamente una nuova tabella ed è stata eseguita l'importazione di dati.

