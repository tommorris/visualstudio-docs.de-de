---
title: Content-Definition (Dialogfeld) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 2018-06-30
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- MessageContent.UI
ms.assetid: 7e4237c3-90a1-4149-bd8a-3643d1dde0df
caps.latest.revision: 3
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: c1ef7dfa925f0f658edb981725d2a5dd8847412b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47511459"
---
# <a name="content-definition-dialog-box"></a>Inhaltsdefinition (Dialogfeld)
Die **Inhaltsdefinition** Dialogfeld wird verwendet, [!INCLUDE[wfd1](../includes/wfd1-md.md)] so konfigurieren Sie die **Content** Eigenschaften der <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.SendReply>, und <xref:System.ServiceModel.Activities.ReceiveReply> Aktivitäten. [!INCLUDE[crabout](../includes/crabout-md.md)] die Aktivitäts-Designer, die dieses Dialogfeld verwenden, finden Sie unter den [senden](../workflow-designer/send-activity-designer.md), [Receive](../workflow-designer/receive-activity-designer.md), [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md), und [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md) Themen.  
  
 Die folgende Tabelle beschreibt die Elemente der Benutzeroberfläche (UI) von der **Korrelation initialisieren** Dialogfeld.  
  
|Benutzeroberflächenelement|Beschreibung|  
|----------------|-----------------|  
|**Meldung**|Gibt an, den Nachrichteninhalt mit dem **Message Data** Ausdruckstextfeld und den Typ mit der **Nachrichtentyp** im Dropdown Listenfeld. Standardmäßig die **Inhaltsdefinition** verwendet die <xref:System.ServiceModel.Activities.ReceiveMessageContent>, der erwartet, dass eine <xref:System.ServiceModel.Channels.Message> oder einen Nachrichtenvertragstyp innerhalb der workflowdienstdefinition.|  
|**Parameter**|Klicken Sie auf die **Parameter** Optionsfeld mit <xref:System.ServiceModel.Activities.ReceiveParametersContent>, der einen Datenvertrag erwartet. Legen Sie mithilfe des Datenrasters eine generische Auflistung von <xref:System.Activities.OutArgument>-Schlüssel-Wert-Paaren fest, deren Werte variablen Parametern im aktuellen Workflow zugewiesen werden.|  
  
 Die **Inhaltsdefinition** Dialogfeld wird verwendet, durch die **senden**, **Receive**, **ReceiveAndSendReply**, und  **SendAndReceiveReply** Designer. Auf diese Designer wird auf ähnliche Weise zugegriffen. Zur Veranschaulichung des Verfahrens wird hier der Receive-Fall verwendet.  
  
 Die **Receive** Aktivitäts-Designer gezogen werden kann, aus der **Toolbox** und auf die [!INCLUDE[wfd2](../includes/wfd2-md.md)] -Oberfläche ganz egal, wo Aktivitäten normalerweise platziert werden. Dadurch wird eine <xref:System.ServiceModel.Activities.Receive>-Aktivität mit dem standardmäßigen <xref:System.Activities.Activity.DisplayName%2A> Receive erstellt. Wählen Sie die **Receive** Aktivitäts-Designer, und klicken Sie auf die Schaltfläche mit den Auslassungspunkten neben dem (Inhalt) Text für die **Inhalt** Eigenschaft im Eigenschaftenraster für das **Inhaltsdefinition**Dialogfeld angezeigt.  
  
 Der Inhalt kann angegeben werden, in der **Nachricht** im Abschnitt für eine <xref:System.ServiceModel.Activities.ReceiveMessageContent> Aktivität oder innerhalb der **Parameter** im Abschnitt für eine <xref:System.ServiceModel.Activities.ReceiveParametersContent> Aktivität.  
  
## <a name="see-also"></a>Siehe auch  
 [Workflow-Designer-Benutzeroberflächenhilfe](../workflow-designer/workflow-designer-ui-help.md)