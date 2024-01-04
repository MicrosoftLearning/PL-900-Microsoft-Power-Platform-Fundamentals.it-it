---
lab:
  title: 'Lab 0: convalidare l''ambiente lab'
  module: 'Module 0: Course introduction'
---

# Lab 0: convalidare l'ambiente lab

**Tenant WWL: condizioni per l'utilizzo** Se, come parte della distribuzione di formazione con istruttore, viene fornito un tenant, tenere presente che il tenant viene reso disponibile allo scopo di supportare le esercitazioni pratiche nel training con docente. I tenant non devono essere condivisi o utilizzati per scopi esterni alle esercitazioni pratiche. Il tenant utilizzato in questo corso è un tenant di valutazione e non può essere utilizzato o reso accessibile dopo il termine della lezione e non è idoneo per l'estensione. I tenant non devono essere convertiti in un abbonamento a pagamento. I tenant ottenuti come parte di questo corso rimangono di proprietà di Microsoft Corporation e Microsoft si riserva il diritto di ottenere l'accesso e di riprenderne il possesso in qualsiasi momento. 

## Scenario

Bellows College è un'organizzazione educativa con più edifici nel campus. I visitatori del campus sono attualmente registrati in giornali di registrazione cartacei. Le informazioni non vengono acquisite in modo coerente e non ci sono mezzi per raccogliere e analizzare i dati sulle visite nell'intero campus.

L'amministrazione del campus vorrebbe modernizzare il proprio sistema di registrazione dei visitatori, facendo controllare l'accesso agli edifici dal personale addetto alla sicurezza e richiedendo una preregistrazione di tutte le visite da parte degli ospiti. 

In questo corso verranno create applicazioni ed eseguita l'automazione per consentire al personale amministrativo e di sicurezza di Bellows College di gestire e controllare l'accesso agli edifici del campus.

In questo lab del modulo 0 si acquisirà un tenant di prova di Power Platform e si accederà all'interfaccia di amministrazione di Power Platform. Nell'interfaccia di amministrazione si creerà l'ambiente **Practice** in cui verrà eseguita la maggior parte delle operazioni dei lab.


## Esercizio 1: configurazione

Attività 1: Acquisire il tenant di prova di Microsoft Power Platform

1.  Copiare le **credenziali di Microsoft 365** da Authorized Lab Hoster. 

1.  Accedere a <https://powerapps.microsoft.com> e selezionare **Inizia gratuitamente**.

1.  In **Inizia**, inserire l'indirizzo e-mail fornito dal  provider di servizi di hosting per i lab autorizzato e selezionare **Inizia la versione di prova gratuita**. 

1.  Se viene visualizzata una pagina aggiuntiva con i pulsanti **Inizia a creare app** e **Inizia a usare app**, fare clic su **Inizia a usare app**, non su Inizia a creare app.

1.  Verrà visualizzato un messaggio per confermare che si dispone di un account Microsoft esistente. Selezionare **Accedi**. 

1.  Immettere la password fornita dal provider di servizi di hosting per i lab autorizzato e selezionare **Accedi**. 

1.  Selezionare **Sì** per mantenere l'accesso. 


Attività n. 2: Creare l'ambiente

1.  Passare a <https://admin.powerplatform.microsoft.com> ed eseguire l'accesso con le proprie credenziali di Microsoft 365, se richiesto. 

1.  Se viene visualizzato un popup di benvenuto, selezionare **Attività iniziali**. 

1.  Selezionare **Ambienti** e selezionare **+ Nuovo**.

    1. In **Nome** immettere **[Iniziali] Practice**, ad esempio: AJ Practice.

    1. Per **Tipo**, scegliere **Prova** (non selezionare l'opzione *Prova (basata su abbonamento)*).

    1. Modificare l'interruttore per **Aggiungere un archivio dati Dataverse?** su **Sì**. 

    1. Lasciare tutte le altre selezioni come impostazione predefinita e selezionare **Avanti**. 

    1. In **Gruppo di sicurezza**, utilizzare il pulsante **+ Seleziona**.

    1. Selezionare la casella di controllo per l'elemento **Nessuno**, sotto la voce **Accesso libero** e quindi selezionare **Fine**.

    1. Lasciare le opzioni rimanenti ai valori predefiniti e selezionare **Salva**. 

1.  L'ambiente **Practice** dovrebbe ora apparire nell'elenco degli ambienti. 

    > L'ambiente potrebbe richiedere alcuni minuti per effettuare il provisioning. Se necessario, aggiornare la pagina.

