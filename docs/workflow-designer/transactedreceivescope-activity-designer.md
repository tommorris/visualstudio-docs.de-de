---
title: Workflow-Designer - TransactedReceiveScope-Aktivitätsdesigner
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.ServiceModel.Activities.TransactedReceiveScope.UI
ms.assetid: 7ca93aad-4e83-4d81-90f4-998ee114d9b6
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 97a4871f3f9f7726f8e0f62008c22aef5e22234e
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36755143"
---
# <a name="transactedreceivescope-activity-designer"></a>TransactedReceiveScope-Aktivitätsdesigner

Die **TransactedReceiveScope** -Designer dient zum Erstellen und Konfigurieren einer <xref:System.ServiceModel.Activities.TransactedReceiveScope> Aktivität.

## <a name="the-transactedreceivescope-activity"></a>Die TransactedReceiveScope-Aktivität

Die <xref:System.ServiceModel.Activities.TransactedReceiveScope>-Aktivität ermöglicht es Ihnen, eine Transaktion in Servertransaktionen einzubinden, die von einem Workflow oder einem Verteiler erstellt werden.

### <a name="using-the-transactedreceivescope-activity-designer"></a>Verwenden des TransactedReceiveScope-Aktivitätsdesigners

Zugriff die **TransactedReceiveScope** Aktivitäts-Designer in der **Messaging** Kategorie der **Toolbox**. Die **TransactedReceiveScope** Aktivitäts-Designer gezogen werden kann, aus der **Toolbox** und sich der Workflow-Designer-Oberfläche gelöscht werden, wo Aktivitäten normalerweise platziert werden. Dies erstellt eine <xref:System.ServiceModel.Activities.TransactedReceiveScope> -Aktivität mit dem standardmäßigen **"DisplayName"** von TransactedReceiveScope. Die <xref:System.Activities.Activity.DisplayName%2A> kann im Header des bearbeitet werden die **TransactedReceiveScope** Aktivitäts-Designer oder in der **"DisplayName"** Feld des Eigenschaftenrasters.

Die **TransactedReceiveScope** Designer enthält **anfordern** und **Text** Felder. Diese werden verwendet, um die <xref:System.ServiceModel.Activities.TransactedReceiveScope.Request%2A>-Eigenschaft, die eine <xref:System.ServiceModel.Activities.Receive>-Aktivität angibt, und die <xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A>-Eigenschaft zu konfigurieren, die eine andere <xref:System.Activities.Activity>-Instanz angibt. <xref:System.ServiceModel.Activities.TransactedReceiveScope.Request%2A> erstellt eine Transaktion. Die Transaktion wird dann dem Geltungsbereich der <xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A>-Instanz zugeordnet, damit jede Aktivität in diesem Bereich in dieser Transaktion ausgeführt wird.

### <a name="the-transactedreceivescope-properties"></a>Die TransactedReceiveScope-Eigenschaften

In der folgenden Tabelle werden die <xref:System.ServiceModel.Activities.TransactedReceiveScope>-Eigenschaften aufgeführt, und es wird beschrieben, wie sie im Designer verwendet werden. Diese <xref:System.Activities.Activity.DisplayName%2A> Eigenschaft im Eigenschaftenraster oder auf der Oberfläche des Workflow-Designer bearbeitet werden kann, aber die anderen müssen auf der Entwurfsoberfläche bearbeitet werden.

|Eigenschaftenname|Erforderlich|Verwendung|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Der optionale Anzeigename der <xref:System.ServiceModel.Activities.TransactedReceiveScope>-Aktivität. Der Standardwert lautet TransactedReceiveScope.<br /><br /> Obwohl der <xref:System.Activities.Activity.DisplayName%2A>-Name nicht unbedingt erforderlich ist, wird als Best Practice empfohlen, einen Anzeigenamen zu verwenden.|
|<xref:System.ServiceModel.Activities.TransactedReceiveScope.Request%2A>|True|Löscht eine <xref:System.ServiceModel.Activities.Receive> Aktivität in der **anfordern** Block auf der aktivitätsdesigneroberfläche.|
|<xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A>|False|Löscht eine <xref:System.Activities.Activity> in die **Text** Block auf der aktivitätsdesigneroberfläche.|

## <a name="see-also"></a>Siehe auch

- [CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)
- [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)
- [Empfangen](../workflow-designer/receive-activity-designer.md)
- [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)
- [Senden](../workflow-designer/send-activity-designer.md)
- [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)