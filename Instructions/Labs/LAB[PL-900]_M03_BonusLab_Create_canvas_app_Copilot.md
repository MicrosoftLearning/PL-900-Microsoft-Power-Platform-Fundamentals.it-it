---
lab:
  title: 'Bonus Lab: creare un''app canvas con Copilot'
  module: 'Module 3: Describe how to build applications with Microsoft Power Apps'
---

# Bonus Lab: creare un'app canvas con Copilot

**Tenant WWL: condizioni per l'utilizzo** Se, come parte della distribuzione di formazione con istruttore, viene fornito un tenant, tenere presente che il tenant viene reso disponibile allo scopo di supportare le esercitazioni pratiche nel training con docente. I tenant non devono essere condivisi o utilizzati per scopi esterni alle esercitazioni pratiche. Il tenant usato in questo corso è un tenant di prova: non è possibile usarlo o accedervi dopo la fine del corso e non è idoneo per l'estensione. I tenant non devono essere convertiti in un abbonamento a pagamento. I tenant ottenuti come parte di questo corso rimangono di proprietà di Microsoft Corporation e Microsoft si riserva il diritto di ottenere l'accesso e di riprenderne il possesso in qualsiasi momento. 

## Scenario

Bellows College è un'organizzazione educativa con più edifici nel campus. I visitatori del campus sono attualmente registrati in giornali di registrazione cartacei. Le informazioni non vengono acquisite in modo coerente e non ci sono mezzi per raccogliere e analizzare i dati sulle visite nell'intero campus.

L'amministrazione del campus vorrebbe modernizzare il proprio sistema di registrazione dei visitatori, facendo controllare l'accesso agli edifici dal personale addetto alla sicurezza e richiedendo una preregistrazione di tutte le visite da parte degli ospiti.

In questo lab, si userà Copilot per creare una nuova applicazione canvas per la registrazione delle visite. 

## Procedura generale per il lab

Seguire la sequenza seguente per progettare l'app canvas:

- Descrivere l'app che si intende sviluppare

- Usare Copilot per modificare la struttura della tabella di supporto

 ## Prerequisiti

- Completamento del **Modulo 1 Lab 0 - Convalidare l'ambiente lab**

## Esercizio 1: Usare Copilot per creare un’app per le visite all’università.

**Obiettivo:** In questo esercizio si creerà un'app canvas connettendosi a una tabella visite del campus.

### Attività \#1: Creare l'applicazione iniziale

1. Passare a https://make.powerapps.com

2. Potrebbe essere necessario ripetere l'autenticazione. Selezionare **Accedi** e seguire le istruzioni, se richiesto.

3. Selezionare l'ambiente **Dev One** in alto a destra, se non è già selezionato.

4. Nella casella **Descrivere l'applicazione che si intende creare**, immettere il testo seguente. Creare un'applicazione che registri le visite di un campus universitario. 

5. Selezionare il pulsante **Vai**.

Copilot inizierà a creare una struttura sotto forma di tabella per supportare l'applicazione. 

> **IMPORTANTE:** Usando l’IA generativa, non si otterranno sempre gli stessi risultati esatti. È possibile che la tabella non corrisponda esattamente alla tabella creata per un altro studente. 

6. Nella casella **Descrivere cosa modificare**, immettere il testo: Aggiungere due colonne, Entrata e Uscita. Questi campi devono entrambi riportare la data e l’ora.  

7. Selezionare il pulsante **Vai** o premere **Invio**. 

8. Far scorrere il lato della tabella e verificare che le colonne **Entrata** e **Uscita** siano state create. 

Dal momento che registriamo l’entrata e l’uscita dei visitatori, non abbiamo bisogno di altri campi che riportino la data della visita. 

9. Individuare il campo **Data visita** (o campo equivalente) e nella casella **Descrivi cosa modificare**, immettere il testo Rimuovi il campo Data visita. 

10. Selezionare il pulsante **Vai**. 

11. Rimuovere altri eventuali campi con la data diversi da **Entrata** e **Uscita**. 

Inizialmente è stato aggiunto il campo **Scopo** formattato con un tipo di dati di testo. Copilot lo trasformerà in un menu a discesa (a scelta). 

12. Nella casella **Descrivi cosa modificare**, immettere il testo seguente: Modificare il campo Scopo in un menu a scelta con le opzioni seguenti: Visita del campus, Fiera della carriera, Incontro con il professore, Orientamento degli studenti, Altro. 

13. Selezionare il pulsante **Vai**. 

14. Dato che si intende riportare anche il numero dell’edificio, nella casella **Descrivi cosa modificare**, inserire: Aggiungere una colonna di compilazione. 

15. Selezionare il pulsante **Vai**. 

16. Se si è soddisfatti della tabella, selezionare il pulsante **Crea app**. 

17. Se necessario, nella schermata **Benvenuto in Power Apps Studio**, selezionare **Non mostrare più**, poi selezionare il pulsante **Ignora**. 

![Screenshot dell'app appena creata](media/bonus-lab-copilot-01.png)

Congratulazioni, è stato usato Copilot per creare una nuova app. 
