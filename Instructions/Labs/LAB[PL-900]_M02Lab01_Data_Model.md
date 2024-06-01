---
lab:
  title: 'Lab 1: Modellazione dei dati'
  module: 'Module 2: Identify foundational components of Microsoft Power Platform'
---

# Lab 1: Modellazione dei dati

**Tenant WWL: condizioni per l'utilizzo** Se, come parte della distribuzione di formazione con istruttore, viene fornito un tenant, tenere presente che il tenant viene reso disponibile allo scopo di supportare le esercitazioni pratiche nel training con docente. I tenant non devono essere condivisi o utilizzati per scopi esterni alle esercitazioni pratiche. Il tenant usato in questo corso è un tenant di valutazione e non può essere usato o accessibile dopo che la classe è finita e non è idonea per l'estensione. I tenant non devono essere convertiti in un abbonamento a pagamento. I tenant ottenuti come parte di questo corso rimangono di proprietà di Microsoft Corporation e Microsoft si riserva il diritto di ottenere l'accesso e di riprenderne il possesso in qualsiasi momento. 

## Scenario

Bellows College è un'organizzazione educativa con più campus e programmi. Molti insegnanti e amministratori di Bellow College devono partecipare agli eventi e acquistare articoli. Storicamente, tenere traccia di queste spese è stata una sfida. 

L'amministrazione campus vuole modernizzare il sistema di gestione delle spese fornendo ai dipendenti un modo digitale per segnalare le spese. 

In questo corso si creeranno applicazioni ed eseguiranno l'automazione per consentire ai dipendenti di Bellows College di gestire le spese.

Infine, i dati di esempio verranno importati in Microsoft Dataverse.

## Procedura generale per il lab

Per preparare gli ambienti di apprendimento, è possibile:

- Fare riferimento al [documento del modello dati](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Allfiles/Campus Management.png) per la descrizione dei metadati (tabelle e relazioni). Per aprire il documento del modello di dati in una nuova finestra, è possibile tenere premuto CTRL e fare clic con il pulsante destro del mouse oppure fare clic con il pulsante destro del mouse sul collegamento.

- Creare una tabella Expense

- Aggiungere alcuni dati di esempio. 

### Prerequisiti

- Completamento del modulo 1 Lab 0 - Convalidare l'ambiente **lab**

Aspetti da considerare prima di iniziare

- Convenzioni di denominazione: immettere i nomi con attenzione.

## Esercizio 1: Creare una nuova tabella

**Obiettivo:** in questo esercizio si creerà una nuova tabella personalizzata per Expenses.

### Attività n. 1: Creare una tabella e colonne expenses

La **tabella Spese** conterrà informazioni sulle singole spese che un dipendente può inviare, tra cui motivo, tipo, data e importo.

1. Se non è già stato effettuato l'accesso, accedere a https://make.powerapps.com

1. **Nel menu Ambiente** in alto a destra verificare che sia selezionato l'ambiente **Dev One**.

1. Dalla barra di spostamento a sinistra selezionare **Tabelle**.

1. Selezionare **+ Nuova tabella** e scegliere **Imposta proprietà avanzate**.

1. Per **Nome** visualizzato immettere Expense

1. Seleziona **Salva**.

1. Nella sezione **Schema** selezionare **Colonne**.

### Crea colonna Data spese

1. Selezionare **+ Nuova colonna**.

1. Immettere Expense Date (Data spese) per **Nome** visualizzato.

1. Selezionare **Solo data** per **Tipo di** dati.

1. Modificare **Obbligatorio** in **Obbligatorio per l'azienda**.

1. Espandi **Opzioni avanzate**.

1. In **Regolazione** fuso orario selezionare **Solo** data.

    >**Nota:** per registrare le informazioni sulla data viene usato **solo** il comportamento date, perché la data delle spese non deve cambiare se visualizzata da un fuso orario diverso.

1. Seleziona **Salva**.

### Crea colonna Tipo di spesa

1. Selezionare **+ Nuova colonna**.

1. Immettere Expense Type (Tipo di spesa) per **Nome** visualizzato.

1. Selezionare **Scelta** per **Tipo di** dati.

1. In **Obbligatorio** selezionare **Facoltativo**.

1. Impostare **Sincronizza con la scelta** globale su **Sì (scelta consigliata)**

1. In **Sincronizza questa scelta con** campo selezionare **Tipo** di spesa.

1. Impostare il **campo Scelta predefinita** su **Nessuno**.

1. Seleziona **Salva**.

### Crea colonna Scopo spese

1. Selezionare **+ Nuova colonna**.

1. Immettere Expense Purpose (Scopo spese) per **Nome** visualizzato.

1. Selezionare **Scelta** per **Tipo di** dati.

1. In **Obbligatorio** selezionare **Facoltativo**.

1. Impostare **Sincronizza con la scelta** globale su **Sì (scelta consigliata)**

1. In **Sincronizza questa scelta con** campo selezionare **Expense Purpose (Scopo** spese).

1. Impostare il **campo Predefinito** su **Nessuno**.

1. Seleziona **Salva**.

### Crea colonna Descrizione elemento

1. Selezionare **+ Nuova colonna**.

1. Immettere Descrizione elemento per **Nome** visualizzato.

1. Selezionare **Più righe di testo &gt; normale** per **Tipo di** dati.

1. Seleziona **Salva**.

### Crea colonna Importo spese

1. Selezionare **+ Nuova colonna**.

1. Immettere Importo spese per **Nome** visualizzato.

1. Selezionare **Valuta** per **Tipo di** dati.

1. Seleziona **Salva**.

 
## Esercizio 2: Immettere i dati

**Obiettivo:** in questo esercizio immettere manualmente alcuni dati di esempio nella nuova tabella. 

### Attività 1: Modificare le colonne visualizzate

1. Se non è già stato eseguito l'accesso, accedere a https://make.powerapps.com

1. Selezionare l'ambiente **Dev One** in alto a destra se non è già selezionato.

1. Dalla barra di spostamento a sinistra selezionare **Tabelle**.

1. Aprire la **tabella Expense** creata nell'esercizio precedente.

1. Accanto alla **colonna Nome** selezionare **+26 altri**.

1. Dal menu visualizzato selezionare le colonne seguenti.

    1. Data spese

    2. Scopo spesa 

    3. Tipo di spesa

    4. Importo spese

    5. Descrizione elemento

1. Selezionare il pulsante **Salva**.

## Attività 2: Aggiungere un record di esempio.

1. Selezionare la **freccia** accanto a **Modifica**. Dal menu visualizzato selezionare **Modifica nella nuova scheda**.

1. **Nella colonna Nome** immettere **John Doe**.

1. **Nella colonna Expense Date (Data** spese) immettere **xxx**.

1. **In Expense Purpose (Scopo** spese) selezionare **Conference (Conferenza**).

1. **Nella colonna Expense Type (Tipo di spesa)** selezionare **Travel (Viaggi**).

1. **Nella colonna Importo** spese immettere **750,00**.

1. Nella descrizione** dell'elemento **immettere una breve descrizione.

1. Premere il pulsante Tab per passare alla riga successiva e **salvare** il record.

Congratulazioni, è stata creata correttamente una nuova tabella e sono stati aggiunti dati.


