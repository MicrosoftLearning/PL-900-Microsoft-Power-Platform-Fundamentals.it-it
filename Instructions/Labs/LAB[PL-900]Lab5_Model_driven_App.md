---
lab:
  title: 'Lab 5: Creare un''app basata su modello'
  learning path: 'Learning Path: Demonstrate the capabilities of Microsoft Power Apps'
  module: 'Module 3: Build a model-driven app'
---
## Obiettivo di apprendimento

In questo esercizio gli studenti creeranno un'app basata su modello in Power Apps usando Copilot. Si definirà il modello di dati, si modificheranno moduli e visualizzazioni e si creerà l'applicazione.

**Al termine di questo lab, si eseguiranno le operazioni seguenti:**

-   Creare un'applicazione basata su modello.
-   Modificare moduli e visualizzazioni nell'applicazione in base alle proprie esigenze.
-   Esplorare un'applicazione basata su modello.

### Scenario

Contoso Consulting è un'organizzazione di servizi professionali specializzata in servizi di consulenza IT e di intelligenza artificiale. Durante tutto l'anno, offrono molti eventi diversi ai loro clienti. Alcuni di questi sono eventi di stile di fiera in cui hanno molti partner sono disponibili e forniscono dettagli su nuovi prodotti, tendenze di mercato e servizi. Altri si verificano durante tutto l'anno e sono webinar rapidi che vengono usati per fornire dettagli sui singoli prodotti.

Contoso vuole usare Power Platform per creare una soluzione di gestione eventi che può usare per gestire i diversi eventi che ospitano durante l'anno.

In questo esercizio si creerà un'applicazione basata su modello per gestire gli eventi di Contoso. L'applicazione basata su modello si baserà su un modello di dati esistente e includerà eventi, sessioni di eventi e registrazioni di sessione.

### Dettagli lab:

Prima di iniziare questo esercizio, è consigliabile aver completato:

-   **Lab 1: Creare una soluzione**
-   **Lab 2: Creare un modello di dati**

Il tempo stimato per completare questo esercizio è **compreso tra 20 e 30** minuti.

## Attività 1: Creare un modello di dati per supportare la nuova applicazione basata su modello

Contoso archivia attualmente le informazioni di contatto nell'istanza di Dataverse, quindi vuole usare Dataverse per tenere traccia dei corsi e delle registrazioni dei corsi. È necessario creare le tabelle necessarie per supportare l'applicazione e creare un'applicazione basata su modello basata su tale modello di dati.

1.  Se necessario, aprire un Web browser e passare al [portale di Power Apps](https://make.powerapps.com/) Maker e accedere usando le credenziali dell'account Microsoft.
1.  Usando lo spostamento a sinistra, selezionare **Soluzioni.**
1.  Aprire la **soluzione Gestione** eventi creata in precedenza.
1.  Sulla barra dei comandi selezionare **Nuova** **\> \> **** app basata su modello di app.******
1.  Selezionare la **sezione Crea** .
    -   **Nome**: `Contoso Event Management`
    -   **Descrizione:**` Used to manage Events and Event Sessions`.
1.  Selezionare il pulsante **Crea**.
1.  Selezionare il **pulsante +Aggiungi pagina** , selezionare **Tabella dataverse.**
1.  Selezionare le tabelle seguenti:
    -   Contatto
    -   Event
    -   Sessione evento
    -   Registrazione della sessione
1.  Assicurarsi che **l'opzione Mostra nel riquadro di spostamento** sia selezionata.

    ![Screenshot che mostra la finestra di dialogo seleziona una tabella.](media/bb46dc856d2939af9c55bdc0303b8a27.png)

1. Seleziona il pulsante **Aggiungi**.

> **Nota:** a volte viene richiesto di accedere durante l'uso della finestra di progettazione. Selezionare la X per annullare la schermata di accesso.

## Attività 2: Modificare l'applicazione basata su modello in base alle proprie esigenze

Ora che l'app viene creata, verranno apportate alcune modifiche alla modalità di presentazione dell'applicazione. Vogliamo avere due gruppi distinti; Persone ed eventi. Si vuole avere la tabella Contatti nel gruppo People e tutte le tabelle Event nel gruppo Eventi.

1.  In **Navigazione** sul lato sinistro della schermata selezionare **Nuovo gruppo**.
1.  Sul lato destro dell'applicazione espandere il **pannello Proprietà** .
1.  Modificare il **titolo** da **Nuovo gruppo** a `People`.

    ![Screenshot che mostra la modifica del nome di un gruppo. ](media/82b6d0cdc4fdbaf4a9eaf2d1f82e972f.png)

1.  Selezionare i **puntini di sospensione** nel **gruppo Persone** .
1.  Scegliere **Nuovo gruppo**.
1.  **Nel riquadro Proprietà** modificare il nome del gruppo da **Nuovo gruppo** a `Events`.
1.  Passare il puntatore del mouse sulla **visualizzazione** Registrazioni sessione a sinistra, selezionare i **puntini di sospensione** e scegliere **Sposta giù** per spostare **le registrazioni** delle sessioni nel **gruppo Eventi** .
1.  Passare il puntatore del mouse sulla **visualizzazione Sessioni** eventi a sinistra, selezionare i **puntini di sospensione** e scegliere **Sposta giù** per spostare **le sessioni** eventi nel **gruppo Eventi** .
1.  Passare il puntatore del mouse sulla **visualizzazione** Eventi a sinistra, selezionare i **puntini di sospensione** e scegliere **Sposta verso il basso** per spostare **gli eventi nel **gruppo** Eventi**.

    L'app dovrebbe essere simile all'immagine:

    ![screenshot che mostra la mappa del sito aggiornata](media/ff039cad105533933959854cec4ec95e.png)

## Attività 3: Modificare i diversi moduli e visualizzazioni nell'applicazione basata su modello

L'applicazione model drive usa moduli e visualizzazioni per presentare i dati agli utenti nell'interfaccia utente. Verranno apportate alcune modifiche a tali elementi.

1.  Se necessario, assicurarsi che **l'app Contoso Event Management** sia aperta nella finestra di progettazione.
1.  Sul lato sinistro della schermata, sotto il gruppo Persone** passare il **puntatore del mouse sul **modulo** Contatti e selezionare **Modifica.**

    Se viene richiesto di salvare le modifiche, selezionare **Salva e continua.**

1.  In **Colonne** tabella a sinistra selezionare **Nuova colonna** tabella.
1.  Configurare la colonna della tabella come indicato di seguito:
    -   **Nome visualizzato**: `Contact Type`
    -   **Tipo di dati:** Scelta
    -   **Eseguire la sincronizzazione con la scelta globale:** No
1.  Impostare Etichetta **** della prima scelta su **Altoparlante.**
1.  Selezionare **+ Nuova scelta** e impostare l'etichetta su **Partecipante.**
1.  Selezionare **+ Nuova scelta** e impostare l'etichetta su **Staff di** supporto.

    ![Screenshot della colonna Tipo contatto.](media/b1982b779d91cf134b41b6f445b8f07c.png)

1.  Fare clic sul pulsante **Salva**.
1.  Usando il mouse, selezionare il **testo Nuovo contatto** per selezionare l'intestazione del modulo. *(Dovrebbe essere visualizzato un rettangolo viola intorno all'intestazione)*
1. In **Colonne** tabella immettere Contatto** nel **campo **Cerca**.
1. Selezionare la **colonna della tabella Contact Type** appena creata.
1. Il **tipo di** contatto dovrebbe ora essere visualizzato nell'intestazione****.

    ![Screenshot che mostra il campo tipo di contatto in un modulo.](media/4debe7a09e460f79c1cb05a6824dad66.png)

1. Sulla barra** dei comandi dei moduli **selezionare il **pulsante Salva e pubblica**.
1. Selezionare il **pulsante Freccia Indietro** per tornare alla finestra di progettazione di applicazioni basate su modello
1. In **Navigazione** a sinistra passare il puntatore del mouse sulla **visualizzazione** Contatti e selezionare l'icona **Modifica** . (Se viene richiesto di salvare, selezionare **Salvare e continuare.**
1. Selezionare **+ Visualizza colonna**.
1. Cercare e aggiungere la **colonna Tipo contatto** alla vista.
1. Selezionare il pulsante **Salva e pubblica**.
1. Selezionare il **pulsante Indietro freccia** per tornare alla finestra di progettazione dell'applicazione basata su modello.

    Successivamente, verranno apportate le modifiche necessarie ai moduli rimanenti.

1.  In **Navigazione** selezionare **Visualizzazione eventi**
    
    Si noti che potrebbe essere presente una **colonna EventDetails1** . In tal caso, verrà rimosso dalla visualizzazione. *(Se non è disponibile, è possibile passare a **Attività 4: Salvare e pubblicare**)*

1.  Passare il puntatore del mouse sulla **visualizzazione** Eventi e selezionare il **pulsante Modifica** .

    Se viene richiesto di **salvare** le modifiche, selezionare **Salva e continua**.

1.  **Nella visualizzazione** selezionare la freccia accanto a **EventDetails1** e scegliere Rimuovi** dal menu visualizzato**.

    ![Screenshot che mostra come rimuovere una colonna aggiuntiva da una visualizzazione.](media/f0f1484a4f3a679abc18cdb1cd5c04da.png)

1.  Selezionare il pulsante **Salva e pubblica**.
1.  Selezionare il **pulsante Freccia Indietro** per tornare alla finestra di progettazione dell'app.
1.  In **Navigazione** passare il puntatore del mouse sul **modulo** Eventi** **e selezionare **Modifica**.

    Se viene richiesto di salvare le modifiche, selezionare **Salva e continua**.

1.  Selezionare **il campo Dettagli evento1** e premere il **tasto Canc** sulla tastiera.

    Il modulo dovrebbe essere simile all'immagine:

    ![Screenshot che mostra il modulo Evento aggiornato, dopo la rimozione di colonne aggiuntive. ](media/d9e8903c79b01e85e32c6ef5279a2ad5.png)

    Se non corrisponde esattamente, va bene fino a quando ci sono tutti i campi dell'immagine.  

1.  Selezionare il **pulsante Salva e pubblica** .
1.  Selezionare il **pulsante Freccia Indietro** per tornare alla finestra di progettazione dell'app.

## Attività 4: Salvare e pubblicare (se il campo EventDetail1 non è presente nel modulo, continuare qui).

1.  **Sulla barra dei comandi** dell'app selezionare il **pulsante Salva e pubblica**.

1.  Selezionare il **pulsante Indietro** per tornare alla **soluzione Gestione eventi** .
1.  Selezionare **Torna alle soluzioni** freccia per tornare al portale principale **di Power Apps Maker** .
1.  Selezionare la **freccia Indietro** per tornare alla schermata principale **di Power Apps** .

## Attività 5: Testare la nuova applicazione

Ora che l'applicazione basata su modello è stata creata, verrà testata la relativa funzionalità.

Prima di tutto aggiungeremo un paio di contatti.

1.  Usando lo spostamento a sinistra, selezionare **App**.
1.  Modificare le app visualizzate da **App personali** a **Tutte**.
1.  Passare il puntatore del mouse sull'applicazione **Gestione** eventi Contoso appena creata e selezionare l'icona **Riproduci** .
1.  Usando lo spostamento a sinistra, selezionare **Contatti**.
1.  Sulla barra dei **comandi** selezionare il **pulsante + Nuovo** .
1.  Nella **schermata Nuovo contatto** configurare come segue:
    -   **Nome di battesimo:** `Suzanne`
    -   **Cognome:** `Diaz`
    -   **Titolo del lavoro:** `Engineer`
1.  Nell'intestazione del modulo selezionare la freccia giù accanto a **Tipo contatto**.
1.  **Impostare Tipo di** contatto su **Altoparlante**.

    ![Screenshot che mostra come impostare il campo Tipo contatto in un modulo.](media/0860116a9b7df096c14728212b9977b1.png)

1.  Selezionare il **pulsante Salva** per salvare il contatto e lasciarlo aperto.
1. Selezionare il pulsante **+New**.
1. Nella **schermata Nuovo contatto** configurare come segue:
    -   **Nome:** Edgar
    -   **Cognome:** Swenson
    -   **Job Title:** Architect
    -   **Email:** immettere l'indirizzo di posta elettronica (assicurarsi di aggiungere **l'indirizzo** di posta elettronica).
1. Nell'intestazione del modulo selezionare la freccia giù accanto a **Tipo contatto**.
1. Impostare Tipo **di** contatto su **Partecipante**.
1. Selezionare il pulsante **Salva e chiudi**.

    Successivamente, verrà aggiunto un nuovo evento.

1.  Usando lo spostamento a sinistra, selezionare **Eventi**.
1.  Sulla barra dei comandi selezionare il **pulsante + Nuovo** .
1.  Nella **schermata Nuovo evento** configurare come segue:
    - **Nome evento:** `Spring conference`.
    - **Data evento:** data di domani.
    - **Numero massimo partecipanti:** `500`
    - **Dettagli evento:** `Spring conference to showcase newest products and services from our supported vendors`.
    - **Tipo di evento:** Conferenza
    - **Posizione**: `Seattle`
    - **Registrazione obbligatoria:** Sì/True

    ![Screenshot del modulo evento completato. ](media/802f68c4c34c635eeff620a23d42acd8.png)

1.  Selezionare il pulsante **Salva e chiudi**.

    Verrà quindi aggiunta una nuova sessione per l'evento.

1.  Usando lo spostamento a sinistra, selezionare **Sessioni** eventi.
1.  Selezionare il pulsante **+New**.
1.  Configurare la **sessione** eventi come indicato di seguito:
    - **Nome sessione:** `Responsible AI`
    - **Data sessione:** data di domani
    - **Durata:** 1,5 ore
    - **Descrizione sessione:** `With all the new AI solutions, being responsible is important. We will discuss the challenges`.
    - **Altoparlante:** `Suzanne Diaz`
    - **Evento:** `Spring Conference`

    ![Screenshot del modulo di sessione evento completato. ](media/6e509e4a29e6f253b5db3b4c9f82e42e.png)

1.  Selezionare il pulsante **Salva e chiudi**.

    Infine, creeremo una **registrazione** di sessione.

1.  Usando il riquadro di spostamento a sinistra, selezionare **Registrazioni di sessione.**
1.  Sulla barra dei **comandi selezionare **+ Nuovo**.**
1.  Completare la registrazione della sessione come indicato di seguito:
    - **Nome registrazione:** `E, Swenson Registration`.
    - **Proprietario:** lasciare invariato
    - **Data registrazione:** data odierna
    - **Istruzioni speciali:** `No Gluten`
    - **Partecipante:** `Edgar Swenson`
    - **Sessione eventi:** `Responsible AI`

    ![Screenshot del modulo di registrazione sessione completato.  ](media/Session-registration-form.png)

1.  Seleziona il pulsante **Salva e chiudi**.



