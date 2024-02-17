---
lab:
  title: 'Lab 3: Come creare un''app basata su modello'
  module: 'Module 3: Get started with Power Apps'
---

# Lab 3: Come creare un'app basata su modello

**Tenant WWL: condizioni per l'utilizzo** Se, come parte della distribuzione di formazione con istruttore, viene fornito un tenant, tenere presente che il tenant viene reso disponibile allo scopo di supportare le esercitazioni pratiche nel training con docente. I tenant non devono essere condivisi o utilizzati per scopi esterni alle esercitazioni pratiche. Il tenant utilizzato in questo corso è un tenant di valutazione e non può essere utilizzato o reso accessibile dopo il termine della lezione e non è idoneo per l'estensione. I tenant non devono essere convertiti in un abbonamento a pagamento. I tenant ottenuti come parte di questo corso rimangono di proprietà di Microsoft Corporation e Microsoft si riserva il diritto di ottenere l'accesso e di riprenderne il possesso in qualsiasi momento. 

## Scenario

Bellows College è un'organizzazione educativa con più edifici nel campus. I visitatori del campus sono attualmente registrati in giornali di registrazione cartacei. Le informazioni non vengono acquisite in modo coerente e non ci sono mezzi per raccogliere e analizzare i dati sulle visite nell'intero campus.

L'amministrazione del campus vorrebbe modernizzare il proprio sistema di registrazione dei visitatori, facendo controllare l'accesso agli edifici dal personale addetto alla sicurezza e richiedendo una preregistrazione di tutte le visite da parte degli ospiti.

In questo corso verranno create applicazioni ed eseguita l'automazione per consentire al personale amministrativo e di sicurezza di Bellows College di gestire e controllare l'accesso agli edifici del campus.

In questo lab, verrà creata un'app basata su modello di Power Apps per consentire al personale del back-office del campus di gestire i record delle visite per l'intero campus.

## Procedura generale per il lab

Nell'ambito della creazione dell'app basata su modello, verranno completate le seguenti operazioni:

- Creare una nuova app basata su modello denominata Bellows Campus Management

- Modificare la navigazione dell'app per fare riferimento alle tabelle richieste

- Personalizzare i moduli e le viste delle tabelle necessari per l'app

Verranno utilizzati i seguenti componenti:

- **Viste**: le viste consentono all'utente di visualizzare i dati esistenti nella tabella del modulo.

- **Moduli**: qui l'utente può creare/aggiornare nuove righe nelle tabelle.

Entrambi verranno integrati nell'app basata su modello per una migliore esperienza utente.

## Prerequisiti

- Completamento del **lab 0 del modulo 0 - Convalidare l'ambiente lab**

- Completamento del **lab 1 del modulo 2 - Modellazione dei dati**

Aspetti da considerare prima di iniziare

- Quali modifiche sono necessarie per migliorare l'esperienza utente?

- Cosa è necessario includere in un'app basata su modello sulla base al modello di dati creato?

- Quali personalizzazioni possono essere effettuate sulla mappa del sito di un'app basata su modello?

## Esercizio 1: Personalizzare visualizzazioni e moduli

**Obiettivo:** in questo esercizio, verranno personalizzate le viste e i moduli delle tabelle create in modo personalizzato che verranno utilizzate nell'app basata su modello.

### Attività n. 1: Modificare il modulo delle visite

1.  Se non si è già, accedere a `https://make.powerapps.com` 

2.  Selezionare l'ambiente **Dev One** in alto a destra, se non è già selezionato.

3.  Usando il riquadro di spostamento a sinistra, selezionare **Tabelle** e aprire la tabella **Visite**.

    Se la tabella Visit non viene visualizzata, assicurarsi di essere nell'ambiente corretto (passaggio 2).

4.  Nella sezione **Esperienze con i dati**, selezionare **Moduli** e aprire il modulo **Informazioni** con il tipo di modulo **Principale**. (**Importante:**  assicurarsi di selezionare il modulo con il tipo di modulo **Principale**). 

    > **IMPORTANTE:**  poiché tutti i moduli hanno il nome Informazioni per impostazione predefinita, verificare che il modulo selezionato abbia il tipo di modulo **Principale** e non un altro. Per impostazione predefinita, il modulo include due campi: Nome e Proprietario.

5.  Sul lato destro della schermata, nel pannello **Proprietà**, selezionare il campo **Nome visualizzato** e modificarlo in `Main Information`

6.  Selezionare **Colonne tabella** nel riquadro di spostamento a sinistra e aggiungere i campi seguenti sotto il campo **Proprietario** trascinando le colonne nel modulo o semplicemente facendo clic sui nomi delle colonne:

    1. **Visitatore**

    2. **Scheduled Start**

    3. **Scheduled End**

    4. **Actual Start**

    5. **Actual End**

7.  Trascinare la colonna **Codice** e rilasciarla nell'intestazione del modulo.

    L'intestazione si trova nell'area in alto a destra del modulo. Potrebbe essere necessario comprimere il pannello Proprietà sul lato destro della schermata per visualizzare il campo nel modulo.

8.  Con il campo **Code** ancora selezionato, selezionare la casella di controllo **Sola lettura** nel pannello Proprietà sul lato destro della schermata.

9.  Selezionare il campo **Proprietario**. Nel pannello Proprietà, impostare la proprietà **Etichetta** su `Host`

10. Selezionare il pulsante **Salva e pubblica** in alto a destra e attendere il completamento del salvataggio e della pubblicazione.

11. Se la visualizzazione di modifica è aperta in una nuova scheda o finestra del browser, chiuderla. In caso contrario, selezionare **🡠 Indietro** in alto a sinistra della schermata. Adesso si dovrebbe passare di nuovo ai moduli delle tabelle **Visit**.

12. Usando la navigazione della parte superiore sinistra (**Tabelle** > **Visit** > **Moduli**). Selezionare **Visita** per tornare alla schermata delle proprietà della tabella **Visit**. 


### Attività n.2: Modificare la vista Visite attive

In questa attività verrà modificata la visualizzazione predefinita Visit attivi/e e si creerà una nuova visualizzazione per le visite del giorno.

1.  Nella sezione **Esperienze dati**, selezionare **Visite** e aprire la vista **Visite attive**.

2.  Aggiungere i seguenti campi alla vista facendo clic su di essi o trascinandoli:

    1. **Codice**

    2. **Visitatore**

    3. **Scheduled Start**

    4. **Scheduled End**

3.  Selezionare il menu a discesa nella colonna **Creato il** e selezionare **Rimuovi**. Il campo **Creato il** verrà ora rimosso dalla vista.

4.  Ridimensionare le larghezze delle singole colonne per adattarle ai dati.

5.  In **Ordina per …** Selezionare la X per rimuovere **Nome** e selezionare **Inizio pianificato**.

6.  Selezionare **Inizio pianificato** per modificare l'ordinamento in **Dal più recente al meno recente**.

7.  Selezionare il pulsante **Salva e pubblica** in alto a destra e attendere il completamento della pubblicazione.


### Attività n.3: Creare una nuova vista per le visite del giorno

Vedremo ora come clonare la visualizzazione per creare una nuova visualizzazione per le visite del giorno.

> **IMPORTANTE:**  assicurarsi di non chiudere la vista Visite attive, che verrà utilizzata per creare la nuova vista Visite odierne.

1.  Seleziona **Salva con nome**.

2.  Modificare **Nome** in `Today’s Visits` e selezionare **Salva**.

3.  Nel pannello Proprietà, selezionare **Modifica filtri**.

4.  Selezionare **+ Aggiungi** e **Aggiungi riga**.

5.  Selezionare **Inizio pianificato** come campo, quindi modificare **Uguale a** in **Oggi** come condizione nel menu a discesa.

6.  Selezionare  **…** **Altri comandi** sulla riga **Stato** e selezionare **Elimina** per eliminare la condizione di filtro.

7.  Selezionare **OK** per salvare la condizione. La vista è ora filtrata per mostrare solo i record in cui la data di **Inizio pianificato** è oggi.

8.  Aggiungere i campi **Inizio effettivo** e **Fine effettiva** alla vista.

> **NOTA:**  poiché i dati non vengono più filtrati in base allo stato della vista, verranno visualizzate tutte le visite di oggi, comprese quelle completate. Questi campi aiutano a distinguere le visite completate da quelle in corso.

9.  Selezionare il pulsante **Salva e pubblica** in alto a destra e attendere il completamento della pubblicazione.


## Esercizio 2: Creare un'app basata su modello

**Obiettivo:** in questo esercizio si creerà un'app basata su modello, si personalizzerà la mappa del sito e quindi si testerà l'app.

Per semplicità e per ragioni di tempo, non verranno usate alcune delle colonne Visit in questo lab.

### Attività n.1: Creare l'app

1.  Se non si è già, accedere a `https://make.powerapps.com` 

2.  Selezionare l'ambiente **Dev One** in alto a destra, se non è già selezionato.

3.  Selezionare **+ Crea** nel riquadro di spostamento a sinistra.

4.  Creare l'applicazione basata su modello:

    1. Selezionare **App vuota** nella sezione **Inizia da** della schermata **Crea la tua app**.

    2. In **App vuota basata su Dataverse** selezionare **Crea**.

    3. Immettere `Bellows Campus Management` nel campo **Nome** e selezionare **Crea**.

5.  Dopo il caricamento della nuova applicazione basata su modello, selezionare il pulsante **+ Aggiungi pagina**.

6.  Nella schermata **Aggiungi pagina**, scegliere **Tabella di Dataverse**, quindi selezionare il pulsante **Avanti**.

7.  Selezionare le tabelle seguenti:

    1. Visitare

    2. Contact

8.  Una volta disponibili entrambe le tabelle, selezionare **Aggiungi**.

9.  Usando le icone di spostamento su lato sinistro della schermata, selezionare **Spostamento**.

10. Nel riquadro di spostamento, selezionare **Nuovo gruppo** sotto la dicitura Navigazione. Potrebbe essere necessario espandere il menu a sinistra.

11. Sul lato destro della schermata, nella sezione **Opzioni di visualizzazione**, impostare la proprietà **Titolo** su `Security`

12. Selezionare**Salva** e attendere che le modifiche vengano salvate.

13. Al termine del** salvataggio** selezionare il pulsante **Pubblica** per pubblicare le modifiche. Attendere il completamento della pubblicazione.


### Attività n. 2: Testare l'app

Avviare l'applicazione

1. Selezionare il pulsante **Riproduci**, l'app basata su modello verrà caricata in una nuova scheda.

Creare un nuovo contatto

2.  L'app verrà aperta nella visualizzazione **Contatti attivi**. In caso contrario, selezionare **Contatti** nel riquadro di spostamento sinistro.

3.  Selezionare **+ Nuovo** dalla barra dei comandi.

4.  Immettere **Nome** come `John` e **Cognome** come `Doe`.

5.  Indicare l'e-mail personale come **E-mail**. Verrà usata in un lab futuro in cui si riceverà un messaggio e-mail.

6.  Seleziona **Salva e chiudi**.

7.  Il nuovo contatto creato dovrebbe essere ora visibile nella visualizzazione **Contatti attivi personali**.

Creare una nuova visita

8.  Selezionare **Visite** nel riquadro di spostamento a sinistra (noto anche come mappa del sito).

9.  Selezionare **+ Nuovo**.

10. Compilare i campi come segue:

    1. **Nome**: `New test visit`

    2. **Visitatore**: selezionare **John Doe**

    3. **Inizio pianificato**: selezionare la data di domani e 14:00 come ora di inizio

    4. **Fine pianificata**: selezionare la data di domani e 15:30 come ora di fine

11. Seleziona **Salva e chiudi**. Verrà così creata la visita che dovrebbe essere visibile nella visualizzazione **Visite attive**.

12. Passare alla visualizzazione **Visite odierne** utilizzando l'elenco a discesa accanto a **Visite attive**. La nuova visita non dovrebbe più apparire nella vista, poiché è pianificata per domani.

13. È possibile aggiungere altri record di test.

L'app basata su modello in esecuzione dovrebbe avere un aspetto simile al seguente:

![](media/3-model-driven-app.png)

Complimenti. È stata creata e configurata la prima app basata su modello.

## Sfide

- Selezionare visualizzazioni e moduli specifici per Contatti.

