---
lab:
  title: "Laboratorio: Convalidare l'ambiente lab"
  module: 'Module 0: Course introduction'
ms.openlocfilehash: e69074549dddd4494db53a9ccb9ebfb3ae198d48
ms.sourcegitcommit: fc79a9b68a8235b37fd90ef84ba8ae1aa2e581f5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2022
ms.locfileid: "144424703"
---
# <a name="module-0-course-introduction"></a>Modulo 0: Introduzione al corso

## <a name="scenario"></a>Scenario

Il Bellows College è un'organizzazione didattica con più edifici nel proprio campus. I visitatori del campus sono attualmente registrati su documenti cartacei. Le informazioni non vengono acquisite in modo coerente e non esiste un sistema per raccogliere e analizzare i dati sulle visite in tutto il campus.

L'amministrazione del campus vorrebbe modernizzare il proprio sistema di registrazione dei visitatori, facendo controllare l'accesso agli edifici dal personale addetto alla sicurezza e richiedendo una preregistrazione di tutte le visite da parte degli ospiti.

Durante questo corso verranno sviluppate applicazioni e si useranno le funzionalità di automazione per consentire al personale amministrativo e addetto alla sicurezza del Bellows College di gestire e controllare l'accesso agli edifici del campus.

In questo lab del modulo 0 si acquisirà un tenant di prova di Power Platform e si accederà all'interfaccia di amministrazione di Power Platform. Nell'interfaccia di amministrazione verrà creato l'ambiente **Practice** in cui verrà eseguita la maggior parte delle operazioni dei lab.

## <a name="exercise-1--setup"></a>Esercizio 1. Configurazione

### <a name="task-1---acquire-your-microsoft-power-platform-trial-tenant"></a>Attività 1 - Acquisire il tenant di prova di Microsoft Power Platform

1.  Copiare le **credenziali di Microsoft 365** dal provider di servizi di hosting per i lab autorizzato.

2.  Passare a <https://powerapps.microsoft.com> e fare clic su **Inizia con la versione di valutazione gratuita**.

3.  In **Iniziamo** immettere l'indirizzo e-mail delle credenziali di Microsoft 365 nella casella di testo **Per iniziare, immetti l'account aziendale o dell'istituto di istruzione**.

4.  Viene visualizzato un messaggio per confermare che si dispone di un account Microsoft esistente. Selezionare **Accedi**.

5.  Immettere la password fornita dal provider di servizi di hosting per i lab autorizzato ed eseguire l'accesso.

6.  Selezionare **Sì** per mantenere l'accesso.

7.  Immettere le informazioni sull'account e selezionare **Get started** (Inizia) per iscriversi alla versione di valutazione di Microsoft Power Platform.

### <a name="task-2--create-environment"></a>Attività 2 - Creare l'ambiente

1.  Passare a <https://admin.powerplatform.microsoft.com> ed eseguire l'accesso con le proprie credenziali di Microsoft 365, se richiesto.

2.  Selezionare **Ambienti** e fare clic su **+Nuovo**.

    1.  In **Nome** immettere **Practice [iniziali]** . Ad esempio: Practice BL.

    2.  In **Tipo** selezionare **Versione di valutazione**. Non selezionare l'opzione Versione di valutazione (basata su abbonamento).

    3.  Impostare l'interruttore per **Creare un database per questo ambiente?** su **Sì**.

    4.  Lasciare le impostazioni predefinite per tutte le altre opzioni e fare clic su **Avanti**.

    5.  Nella scheda successiva lasciare le impostazioni predefinite per tutte le opzioni e fare clic su **Salva**.

3.  L'ambiente **Practice** dovrebbe ora comparire nell'elenco Ambienti.

>   Per il provisioning dell'ambiente potrebbero essere necessari alcuni minuti. Se necessario, aggiornare la pagina.
