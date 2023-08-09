---
lab:
  title: Lab 0. Convalidare l'ambiente lab
  module: 'Module 0: Course introduction'
---

# Lab 0. Convalidare l'ambiente lab

**Tenant WWL - Condizioni per l'utilizzo** Se viene fornito un tenant come parte di un recapito di formazione con docente, si noti che il tenant viene reso disponibile allo scopo di supportare i lab pratici nella formazione con docente. I tenant non devono essere condivisi o usati per scopi esterni ai lab pratici. Il tenant usato in questo corso è un tenant di valutazione e non può essere usato o accessibile dopo che la classe è finita e non sono idonei per l'estensione. I tenant non devono essere convertiti in una sottoscrizione a pagamento. I tenant ottenuti come parte di questo corso rimangono la proprietà di Microsoft Corporation e ci si riserva il diritto di ottenere l'accesso e la ripossess in qualsiasi momento. 

## Scenario

Il Bellows College è un'organizzazione didattica con più edifici nel proprio campus. I visitatori del campus sono attualmente registrati su documenti cartacei. Le informazioni non vengono acquisite in modo coerente e non esiste un sistema per raccogliere e analizzare i dati sulle visite in tutto il campus.

L'amministrazione del campus vorrebbe modernizzare il proprio sistema di registrazione dei visitatori, facendo controllare l'accesso agli edifici dal personale addetto alla sicurezza e richiedendo una preregistrazione di tutte le visite da parte degli ospiti. 

Durante questo corso verranno sviluppate applicazioni e si useranno le funzionalità di automazione per consentire al personale amministrativo e addetto alla sicurezza del Bellows College di gestire e controllare l'accesso agli edifici del campus.

In questo lab del modulo 0 si acquisirà un tenant di prova di Power Platform e si accederà all'interfaccia di amministrazione di Power Platform. Nell'interfaccia di amministrazione si creerà l'ambiente **Practice** in cui verrà eseguita la maggior parte delle operazioni dei lab.


## Esercizio 1. Configurazione

Attività n. 1 - Acquisire il tenant di valutazione di Microsoft Power Platform

1.  Copiare le **credenziali di Microsoft 365** dal provider di servizi di hosting per i lab autorizzato. 

1.  Passare a <https://powerapps.microsoft.com> e selezionare **Avvia gratuitamente**.

1.  In **Iniziamo immettere l'indirizzo** di posta elettronica fornito da Authorized Lab Hoster e selezionare **Avvia la versione di valutazione gratuita**. 

1.  Verrà visualizzato un messaggio per confermare che si dispone di un account Microsoft esistente. Fare clic su **Accedi**. 

1.  Immettere la password fornita da Authorized Lab Hoster e selezionare **Accedi**. 

1.  Selezionare **Sì** per mantenere l'accesso. 


Attività n. 2 : creare un ambiente

1.  Passare a <https://admin.powerplatform.microsoft.com> e accedere con le credenziali di Microsoft 365, se richiesto. 

1.  Se viene visualizzata una finestra popup di benvenuto, selezionare **Inizia**. 

1.  Selezionare **Ambienti** e quindi **+ Nuovo**.

    1. In **Nome** immettere **[Iniziali] Practice**, ad esempio: AJ Practice.

    1. Per **Tipo** scegliere **Versione di** valutazione (Non selezionare l'opzione *Versione di valutazione (basata su sottoscrizione).*

    1. Impostare l'interruttore per **Aggiungi un archivio dati dataverse?** su **Sì**. 

    1. Lasciare predefinite tutte le altre selezioni e selezionare **Avanti**. 

    1. Sotto l'intestazione **Gruppo di sicurezza** usare il pulsante **+ Seleziona** .

    1. Selezionare la casella di controllo per l'elemento **Nessuno** , sotto l'intestazione **Apri accesso** e quindi selezionare **Fine**.

    1. Lasciare le opzioni rimanenti predefinite e selezionare **Salva**. 

1.  L'ambiente **Di pratica** dovrebbe ora essere visualizzato nell'elenco degli ambienti. 

    > Per il provisioning dell'ambiente potrebbero essere necessari alcuni minuti. Se necessario, aggiornare la pagina.

