---
lab:
  title: 'Bonus Lab: Creare un''app canvas con Copilot'
  module: 'Module 3: Get started with Power Apps'
---

# Bonus Lab: Creare un'app canvas con Copilot

**Tenant WWL: condizioni per l'utilizzo** Se, come parte della distribuzione di formazione con istruttore, viene fornito un tenant, tenere presente che il tenant viene reso disponibile allo scopo di supportare le esercitazioni pratiche nel training con docente. I tenant non devono essere condivisi o utilizzati per scopi esterni alle esercitazioni pratiche. Il tenant utilizzato in questo corso è un tenant di valutazione e non può essere utilizzato o reso accessibile dopo il termine della lezione e non è idoneo per l'estensione. I tenant non devono essere convertiti in un abbonamento a pagamento. I tenant ottenuti come parte di questo corso rimangono di proprietà di Microsoft Corporation e Microsoft si riserva il diritto di ottenere l'accesso e di riprenderne il possesso in qualsiasi momento. 

## Scenario

Bellows College è un'organizzazione educativa con più edifici nel campus. I visitatori del campus sono attualmente registrati in giornali di registrazione cartacei. Le informazioni non vengono acquisite in modo coerente e non ci sono mezzi per raccogliere e analizzare i dati sulle visite nell'intero campus.

L'amministrazione del campus vorrebbe modernizzare il proprio sistema di registrazione dei visitatori, facendo controllare l'accesso agli edifici dal personale addetto alla sicurezza e richiedendo una preregistrazione di tutte le visite da parte degli ospiti.

In questo lab si userà Copilot per creare una nuova applicazione canvas per la registrazione delle visite. 

## Procedura generale per il lab

Seguire la sequenza seguente per progettare l'app canvas:

- Descrivere l'app da compilare

- Usare Copilot per modificare la struttura della tabella di supporto

 ## Prerequisiti

- Completamento del modulo 1 Lab 0 - Convalidare l'ambiente **lab**

## Esercizio 1: Usare Copilot per creare un'applicazione di visite universitarie.

**Obiettivo:** in questo esercizio si creerà un'app canvas connettendosi a una tabella Expense Reports.

### Attività \#1: Creare l'applicazione iniziale

1. Passare a https://make.powerapps.com

2. Potrebbe essere necessario ripetere l'autenticazione: selezionare **Accedi** e seguire le istruzioni, se necessario.

3. Selezionare l'ambiente **Dev One** in alto a destra, se non è già selezionato.

4. **Nella casella Descrivere l'applicazione da creare** immettere il testo seguente. Creare un'applicazione che registri visite a un campus universitario. 

5. Selezionare il pulsante **Vai**.

Copilot inizierà a creare una struttura di tabella per supportare l'applicazione. 

> **IMPORTANTE:** quando si usa l'intelligenza artificiale generativa, non si otterranno sempre gli stessi risultati. È possibile che la tabella non corrisponda esattamente alla tabella creata per un altro studente. 

6. **Nella casella Descrivere cosa modificare** immettere il testo: Aggiungi due colonne, Time in e Timeout. Entrambi devono essere campi di data e ora.  

7. Selezionare il **pulsante Vai** o premere **INVIO**. 

8. Scorrere fino al lato della tabella e verificare che le **colonne Tempo in** e **Timeout** siano state create. 

Dal momento che stiamo registrando i visitatori in e fuori tempo, non abbiamo più bisogno di altri campi della data di visita. 

9. Individuare il **campo Data** visita (o campo equivalente) e nella **casella** Descrive cosa modificare immettere il testo Rimuovi il campo Data visita. 

10. Selezionare il pulsante **Vai**. 

11. Rimuovere eventuali campi di data aggiuntivi che potrebbero essere presenti diversi da **Time in** e **Timeout**. 

Inizialmente è stato aggiunto un campo come un **campo Scopo** con un tipo di dati di testo. Avremo copilot cambiarlo in un menu a discesa (scelta). 

12. **Nella casella** Descrivere cosa modificare immettere il testo seguente: Modificare il campo Scopo in un menu di scelta con le opzioni seguenti: Campus Tour, Fiera della carriera, Incontro con professore, Consulente degli studenti, Altro. 

13. Selezionare il pulsante **Vai**. 

14. Poiché si vuole acquisire anche il numero di edificio, nella **casella** Descrivere cosa modificare immettere: Aggiungere una colonna di compilazione. 

15. Selezionare il pulsante **Vai**. 

16. Dopo aver soddisfatto la tabella, selezionare il **pulsante Crea app** . 

17. Se necessario, nella **schermata Benvenuto in Power Apps Studio** selezionare **Non visualizzare di nuovo** questa opzione e selezionare il **pulsante Ignora** . 

![](media/bonus-lab-copilot-01.png)

Congratulazioni, è stato usato Copilot per creare una nuova app. 
