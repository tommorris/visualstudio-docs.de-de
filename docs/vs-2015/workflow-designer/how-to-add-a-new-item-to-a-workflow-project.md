---
title: 'Vorgehensweise: Hinzufügen eines neuen Elements zu einem Workflowprojekt | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 5c6180ca-af10-4513-b0cb-7d478fd84eab
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 1779fa4f3f644913bfe39164e707dfee4673502b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47511889"
---
# <a name="how-to-add-a-new-item-to-a-workflow-project"></a>Gewusst wie: Hinzufügen eines neuen Elements zu einem Workflowprojekt
Nach der Erstellung eines Workflowprojekts können Sie diesem Projekt Workflowaktivitäten, Designer und andere bekannte [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]-Elemente hinzufügen.  
  
 In der folgenden Tabelle werden die [!INCLUDE[wf](../includes/wf-md.md)]-Elemente aufgeführt, die Sie einem Workflowprojekt hinzufügen können.  
  
|Name|Beschreibung|  
|----------|-----------------|  
|Aktivität|Eine Aktivität, die aus anderen Aktivitäten besteht. Durch die Auswahl dieses Elements die gleiche XAML-Datei dem Projekt hinzugefügt, die Sie erhalten würden, bei der Auswahl der **Aktivitätsbibliothek** Vorlage für ein neues Projekt. [!INCLUDE[crabout](../includes/crabout-md.md)] In diesem Verfahren finden Sie unter [Vorgehensweise: Erstellen einer Aktivitätsbibliothek](../workflow-designer/how-to-create-an-activity-library.md).|  
|Aktivitätsdesigner|Ein Designer, mit dem die Behandlung einer Aktivität zur Entwurfszeit angepasst wird. Durch die Auswahl dieses Elements die gleichen Dateien dem Projekt hinzugefügt, die Sie erhalten würden, bei der Auswahl der **Aktivitäts-Designerbibliothek** Vorlage für ein neues Projekt. [!INCLUDE[crabout](../includes/crabout-md.md)] In diesem Verfahren finden Sie unter [Vorgehensweise: Erstellen einer Aktivitätsdesignerbibliothek](../workflow-designer/how-to-create-an-activity-designer-library.md).|  
|Codeaktivität|Eine Aktivität mit in Code geschriebener Ausführungslogik. Eine Quellcodedatei mit einer Überschreibung der <xref:System.Activities.CodeActivity.Execute%2A>-Methode wird bereits für Sie generiert.|  
|WCF-Workflowdienst|Ein [!INCLUDE[indigo2](../includes/indigo2-md.md)]-Dienst, der mithilfe von Workflowaktivitäten erstellt wurde. Durch die Auswahl dieses Elements die gleichen Dateien dem Projekt hinzugefügt, die Sie erhalten würden, bei der Auswahl der **WCF-Workflowdienstanwendung** Vorlage für ein neues Projekt. [!INCLUDE[crabout](../includes/crabout-md.md)] In diesem Verfahren finden Sie unter [Vorgehensweise: Erstellen einer Dienstanwendung für WCF-Workflows](../workflow-designer/how-to-create-a-wcf-workflow-service-application.md).|  
  
### <a name="to-add-a-new-item-to-a-workflow-project"></a>So fügen Sie ein neues Element zu einem Workflowprojekt hinzu  
  
1.  Auf der **Projekt** Menü klicken Sie auf **neues Element hinzufügen...** .  
  
     Die **Hinzufügen eines neuen Elements** Dialogfeld wird geöffnet.  
  
2.  In der **installierte Vorlagen** wählen Sie im Bereich **Workflow** Gruppe.  
  
3.  Wählen Sie eines der vier Elemente aus. In der vorherigen Tabelle ist die verfügbare Auswahl aufgeführt.  
  
4.  Geben Sie einen geeigneten Namen für das Element in der **Namen** Feld am unteren Rand des Dialogfelds.  
  
5.  Klicken Sie auf **hinzufügen** um das Element dem aktuellen Workflowprojekt hinzuzufügen.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen eines Workflowprojekts](../workflow-designer/creating-a-workflow-project.md)