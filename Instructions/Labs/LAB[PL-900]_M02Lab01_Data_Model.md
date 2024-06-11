---
lab:
  title: 'Lab 1: Modellazione dei dati'
  module: 'Module 2: Identify foundational components of Microsoft Power Platform'
---

# Lab 1: Modellazione dei dati

**Tenant WWL: condizioni per l'utilizzo** Se, come parte della distribuzione di formazione con istruttore, viene fornito un tenant, tenere presente che il tenant viene reso disponibile allo scopo di supportare le esercitazioni pratiche nel training con docente. I tenant non devono essere condivisi o utilizzati per scopi esterni alle esercitazioni pratiche. Il tenant usato in questo corso è un tenant di valutazione e non può essere usato o risultare accessibile dopo che la classe è finita e non è idonea per l'estensione. I tenant non devono essere convertiti in un abbonamento a pagamento. I tenant ottenuti come parte di questo corso rimangono di proprietà di Microsoft Corporation e Microsoft si riserva il diritto di ottenere l'accesso e di riprenderne il possesso in qualsiasi momento. 

## Scenario

Il Bellows College è un'organizzazione educativa con più campus e programmi. Molti insegnanti e amministratori del Bellow College devono partecipare agli eventi e acquistare articoli. Storicamente, tenere traccia di queste spese è stata una sfida. 

L'amministrazione del campus vuole modernizzare il sistema di gestione delle spese fornendo ai dipendenti un modo digitale per segnalare le spese. 

In questo corso si creeranno delle applicazioni e si eseguirà l'automazione per consentire ai dipendenti del Bellows College di gestire le spese.

Infine, i dati di esempio verranno importati in Microsoft Dataverse.

## Procedura generale per il lab

Per preparare gli ambienti di apprendimento, è possibile:

- Fare riferimento al [documento del modello dati](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Allfiles/Campus Management.png) per la descrizione dei metadati (tabelle e relazioni). Per aprire il documento del modello di dati in una nuova finestra, è possibile tenere premuto CTRL e fare clic con il pulsante destro del mouse oppure fare clic con il pulsante destro del mouse sul collegamento.

- Creare una tabella Spesa

- Aggiungere alcuni dati di esempio. 

### Prerequisiti

- Completamento del **Modulo 1 Lab 0 - Convalidare l'ambiente lab**

Aspetti da considerare prima di iniziare

- Convenzioni di denominazione: immettere i nomi con attenzione.

## Esercizio 1: Creare una nuova tabella

**Obiettivo:** In questo esercizio sarà creata la nuova tabella personalizzata per Spese.

### Attività 1: Creare una tabella e colonne Spese

La tabella **Spese** conterrà informazioni sulle singole spese che un dipendente può presentare, quali motivo, tipo, data e importo.

1. Se non è già stato effettuato l'accesso, accedere a https://make.powerapps.com

1. Nel menu **Ambiente** in alto a destra, verificare che sia selezionato l'ambiente **Dev One**.

1. Dalla barra di spostamento a sinistra selezionare **Tabelle**.

1. Selezionare **+ Nuova tabella** e scegliere **Imposta proprietà avanzate**.

1. Per **Nome visualizzato** immettere Spesa

1. Seleziona **Salva**.

1. Nella sezione **Schema** selezionare **Colonne**.

### Creare la colonna Data spese

1. Selezionare **+ Nuova colonna**.

1. Immettere Data spese per **Nome visualizzato**.

1. Selezionare **Solo data** per **Tipo di dati**.

1. Modificare **Obbligatorio** in **Obbligatorio per l'azienda**.

1. Espandi **Opzioni avanzate**.

1. In **Rettifica del fuso orario**selezionare **Solo data**.

    >**Nota:** Il comportamento **Solo data** viene usato per registrare le informazioni sulla data: la data delle spese non deve cambiare quando visualizzata da un fuso orario diverso.

1. Seleziona **Salva**.

### Creare la colonna Tipo di spesa

1. Selezionare **+ Nuova colonna**.

1. Immettere Tipo di spesa per **Nome visualizzato**.

1. Selezionare **Scelta** per **Tipo di dati**.

1. In **Obbligatori**o, selezionare **Facoltativo**.

1. Impostare **Sincronizza con la scelta globale** su **Sì (scelta consigliata)**

1. Nel campo **Sincronizza questa scelta con** selezionare **Tipo di spesa**.

1. Impostare il campo **Impostazione predefinita** su **Nessuna**.

1. Seleziona **Salva**.

### Creare la colonna Scopo spesa

1. Selezionare **+ Nuova colonna**.

1. Immettere Scopo spesa per **Nome visualizzato**.

1. Selezionare **Scelta** per **Tipo di dati**.

1. In **Obbligatori**o, selezionare **Facoltativo**.

1. Impostare **Sincronizza con la scelta globale** su **Sì (scelta consigliata)**

1. Nel campo **Sincronizza questa scelta con** selezionare **Scopo spesa**.

1. Impostare il campo **Impostazione predefinita** su **Nessuna**.

1. Seleziona **Salva**.

### Creare la colonna Descrizione elemento

1. Selezionare **+ Nuova colonna**.

1. Immettere Descrizione elemento per **Nome visualizzato**.

1. Selezionare **Più righe di testo &gt; Testo normale** per **Tipo di dati**.

1. Seleziona **Salva**.

### Creare la colonna Importo spesa

1. Selezionare **+ Nuova colonna**.

1. Immettere Importo spesa per **Nome visualizzato**.

1. Selezionare **Valuta** per **Tipo di dati**.

1. Seleziona **Salva**.

 
## Esercizio 2: Immettere i dati

**Obiettivo:** In questo esercizio vengono immessi manualmente alcuni dati di esempio nella nuova tabella. 

### Attività 1: Modificare le colonne visualizzate

1. Se non è già stato eseguito l'accesso, accedere a https://make.powerapps.com

1. Selezionare l'ambiente **Dev One** in alto a destra, se non è già selezionato.

1. Dalla barra di spostamento a sinistra selezionare **Tabelle**.

1. Aprire la tabella **Spesa** creata nell'esercizio precedente.

1. Accanto alla colonna **Nome** selezionare **+26 altri**.

1. Dal menu visualizzato, selezionare le colonne seguenti.

    1. Data spesa

    2. Scopo spesa 

    3. Tipo di spesa

    4. Importo spesa

    5. Descrizione dell'articolo

1. Selezionare il pulsante **Salva**.

## Attività 2. Aggiungere un record di esempio.

1. Selezionare la **Freccia** accanto a **Modifica**. Dal menu visualizzato selezionare **Modifica nella nuova scheda**.

1. Nella colonna **Nome**, immettere **John Doe**.

1. Nella colonna **Data spesa**, immettere **xxx**.

1. In **Scopo spesa**, selezionare **Conferenza**.

1. Nella colonna **Tipo di spesa**, selezionare **Viaggio**.

1. Nella colonna **Importo spesa**, immettere **750,00**.

1. In **Descrizione elemento**, immettere una breve descrizione.

1. Premere il pulsante Scheda per passare alla riga successiva e **salvare** il record.

Congratulazioni, è stata creata correttamente una nuova tabella e sono stati aggiunti dati.


