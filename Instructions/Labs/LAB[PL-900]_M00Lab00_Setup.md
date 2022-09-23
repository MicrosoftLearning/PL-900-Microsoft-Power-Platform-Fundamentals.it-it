---
lab:
  title: Lab 0. Convalidare l'ambiente lab
  module: 'Module 0: Course introduction'
ms.openlocfilehash: d25543d93be7e40749c8fee3a01c35b3a8f2947b
ms.sourcegitcommit: 8a89b7eacd1a65eaa7c5d6bff0dc7254991c4dde
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2022
ms.locfileid: "147154396"
---
# <a name="lab-0-validate-lab-environment"></a>Lab 0. Convalidare l'ambiente lab

## <a name="scenario"></a>Scenario

Il Bellows College è un'organizzazione didattica con più edifici nel proprio campus. I visitatori del campus sono attualmente registrati su documenti cartacei. Le informazioni non vengono acquisite in modo coerente e non esiste un sistema per raccogliere e analizzare i dati sulle visite in tutto il campus.

L'amministrazione del campus vorrebbe modernizzare il proprio sistema di registrazione dei visitatori, facendo controllare l'accesso agli edifici dal personale addetto alla sicurezza e richiedendo una preregistrazione di tutte le visite da parte degli ospiti.

Durante questo corso verranno sviluppate applicazioni e si useranno le funzionalità di automazione per consentire al personale amministrativo e addetto alla sicurezza del Bellows College di gestire e controllare l'accesso agli edifici del campus.

In questo lab del modulo 0 si acquisirà un tenant di prova di Power Platform e si accederà all'interfaccia di amministrazione di Power Platform. Nell'interfaccia di amministrazione si creerà l'ambiente **Practice** in cui verrà eseguita la maggior parte delle operazioni dei lab.

## <a name="exercise-1--setup"></a>Esercizio 1. Configurazione

### <a name="task-1---acquire-your-microsoft-power-platform-trial-tenant"></a>Attività \#1 - Acquisire il tenant di prova di Microsoft Power Platform

1. Copiare le **credenziali di Microsoft 365** dal provider di servizi di hosting per i lab autorizzato.

1. Passare a <https://powerapps.microsoft.com> e fare clic su **Inizia con la versione di valutazione gratuita**.

1. In **Iniziamo** immettere l'indirizzo e-mail delle credenziali di Microsoft 365 nella casella di testo **Immettere l'indirizzo di posta elettronica aziendale** e fare clic su **Avanti**.

1. Verrà visualizzato un messaggio per confermare che si dispone di un account Microsoft esistente. Fare clic su **Accedi**.

1. Immettere la password fornita dal provider di servizi di hosting per i lab autorizzato ed eseguire l'accesso.

1. Selezionare **Sì** per mantenere l'accesso.

1. Non cambiare il paese.

1. Per **Numero di telefono** immettere 01234567890.

1. Immettere le informazioni sull'account e selezionare **Get started** (Inizia) per iscriversi alla versione di valutazione di Microsoft Power Platform.

1. Nella schermata di conferma fare clic su **Inizia**.

1. Se viene visualizzata la richiesta di immettere i dettagli del contatto, fare clic su **X** per chiudere la finestra popup.

### <a name="task-2--create-environment"></a>Attività 2 - Creare l'ambiente

1. Passare a <https://admin.powerplatform.microsoft.com> ed eseguire l'accesso con le proprie credenziali di Microsoft 365, se richiesto.

1. Se viene visualizzato un popup di benvenuto, fare clic su **Inizia**.

1. Selezionare **Ambienti** e fare clic su **+Nuovo**.

    1. In **Nome** immettere **[Iniziali] Practice**, ad esempio: AJ Practice.

    1. In **Tipo** selezionare **Versione di valutazione**. Non selezionare l'opzione Versione di valutazione (basata su abbonamento).

    1. Impostare l'interruttore per **Creare un database per questo ambiente?** su **Sì**.

    1. Lasciare le impostazioni predefinite per tutte le altre opzioni e fare clic su **Avanti**.

    1. Nella scheda successiva lasciare le impostazioni predefinite per tutte le opzioni e fare clic su **Salva**.

1. L'ambiente **Practice** dovrebbe ora comparire nell'elenco Ambienti.

> Per il provisioning dell'ambiente potrebbero essere necessari alcuni minuti. Se necessario, aggiornare la pagina.
