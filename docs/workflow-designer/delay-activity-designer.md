---
title: Workflow-Designer - Delay-Aktivitätsdesigner
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.Delay.UI
ms.assetid: f51742a8-2c9a-47d1-8a23-18459d03ae19
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 31b632177ba941ad0e5ddb5700ae430573fd817d
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36758452"
---
# <a name="delay-activity-designer"></a>Delay-Aktivitätsdesigner

Die **Verzögerung** Aktivitäts-Designer dient zum Erstellen und Konfigurieren einer <xref:System.Activities.Statements.Delay> Aktivität.

## <a name="the-delay-activity"></a>Die Delay-Aktivität

Die <xref:System.Activities.Statements.Delay>-Aktivität verzögert die Ausführung eines Workflows während einer bestimmten Zeitspanne.

### <a name="use-the-delay-activity-designer"></a>Verwenden Sie die Delay-Aktivitätsdesigner

Die **Verzögerung** Aktivitäts-Designer finden Sie in der **primitive** Kategorie der **Toolbox**, die erfolgt durch Klicken auf die **Toolbox**Registerkarte des Workflow-Designers. Wählen Sie alternativ **Toolbox** aus der **Ansicht** Menü, oder drücken Sie **STRG**+**Alt** + **X**.

Die **Verzögerung** Aktivitäts-Designer gezogen werden kann, aus der **Toolbox** und sich der Workflow-Designer-Oberfläche gelöscht werden, wo Aktivitäten normalerweise platziert werden, z. B. in einem <xref:System.Activities.Statements.Sequence>. Löschen die Aktivitäts-Designer erstellt eine <xref:System.Activities.Statements.Delay> -Aktivität mit dem standardmäßigen <xref:System.Activities.Activity.DisplayName%2A> Verzögerung. Die <xref:System.Activities.Activity.DisplayName%2A> kann im Header des bearbeitet werden die **Verzögerung** Aktivitäts-Designer oder in der **"DisplayName"** Feld des Eigenschaftenrasters.

### <a name="the-delay-properties"></a>Die Delay-Eigenschaften

Die folgende Tabelle zeigt die <xref:System.Activities.Statements.Delay> Eigenschaften und beschreibt, wie sie im Designer verwendet werden. Diese Eigenschaften können im Eigenschaftenraster bearbeitet werden, und einige davon können auf der Oberfläche des Workflow-Designer bearbeitet werden.

|Eigenschaftenname|Erforderlich|Verwendung|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Der Anzeigename der <xref:System.Activities.Statements.Delay>-Aktivität. Der Standardwert lautet Delay. Obwohl die <xref:System.Activities.Activity.DisplayName%2A> Wert ist nicht unbedingt erforderlich, es hat sich bewährt, eine zu verwenden.|
|<xref:System.Activities.Statements.Delay.Duration%2A>|True|Die Zeitspanne, um die der Workflow verzögert werden soll. Diese Eigenschaft wird im Eigenschaftenraster festgelegt. Geben Sie in entweder einen literalen <xref:System.TimeSpan>-Wert im Format 00:00:00 oder einem Visual Basic-Ausdruck ein, um die Zeitspanne anzugeben.|

## <a name="see-also"></a>Siehe auch

- [Primitive](../workflow-designer/primitives-activity-designers.md)
- [Weisen Sie](../workflow-designer/assign-activity-designer.md)
- [Delay-Aktivitätsdesigner](../workflow-designer/delay-activity-designer.md)
- [InvokeMethod](../workflow-designer/invokemethod-activity-designer.md)
- [WriteLine](../workflow-designer/writeline-activity-designer.md)