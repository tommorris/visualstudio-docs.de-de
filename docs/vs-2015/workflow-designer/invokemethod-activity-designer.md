---
title: InvokeMethod-Aktivitätsdesigner | Microsoft-Dokumentation
ms.custom: ''
ms.date: 2018-06-30
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- System.Activities.Statements.InvokeMethod.UI
ms.assetid: 15e6efdc-52ca-46d8-9c5e-063f7c8265a6
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 871e684c3503567411f49b419fcf8c47866a35d9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47514424"
---
# <a name="invokemethod-activity-designer"></a>InvokeMethod-Aktivitätsdesigner
**InvokeMethod** -Designer dient zum Erstellen und Konfigurieren einer <xref:System.Activities.Statements.InvokeMethod> Aktivität.  
  
## <a name="the-invokemethod-activity"></a>Die InvokeMethod-Aktivität  
 Die <xref:System.Activities.Statements.InvokeMethod>-Aktivität ruft eine öffentliche Methode eines angegebenen Objekts oder Typs auf.  
  
### <a name="using-the-invokemethod-activity-designer"></a>Verwenden des InvokeMethod-Aktivitätsdesigners  
 Die **InvokeMethod** Aktivitäts-Designer finden Sie in der **primitive** Kategorie der **Toolbox**, die erfolgt durch Klicken auf die **Toolbox** Registerkarte [!INCLUDE[wfd2](../includes/wfd2-md.md)] (Wählen Sie alternativ **Symbolleiste** aus der **Ansicht** Menü oder STRG + ALT + X.)  
  
 Die **InvokeMethod** Aktivitäts-Designer gezogen werden kann, aus der **Toolbox** und auf die [!INCLUDE[wfd2](../includes/wfd2-md.md)] Oberfläche, wo Aktivitäten normalerweise platziert, etwa innerhalb einer <xref:System.Activities.Statements.Sequence>. Daraufhin wird eine <xref:System.Activities.Statements.InvokeMethod>-Aktivität mit dem <xref:System.Activities.Activity.DisplayName%2A>-Standardwert InvokeMethod erstellt. Die <xref:System.Activities.Activity.DisplayName%2A> kann im Header des bearbeitet werden die **InvokeMethod** Aktivitäts-Designer oder in der **"DisplayName"** Feld des Eigenschaftenrasters.  
  
### <a name="the-invokemethod-properties"></a>Die InvokeMethod-Eigenschaften  
 In der folgenden Tabelle werden die <xref:System.Activities.Statements.InvokeMethod>-Eigenschaften aufgeführt, und es wird beschrieben, wie sie im Designer verwendet werden. Diese Eigenschaften können im Eigenschaftenraster bearbeitet werden, einige davon können auch in der [!INCLUDE[wfd2](../includes/wfd2-md.md)]-Designeroberfläche bearbeitet werden.  
  
|Eigenschaftenname|Erforderlich|Verwendung|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Der Anzeigename der <xref:System.Activities.Statements.InvokeMethod>-Aktivität. Der Standardwert lautet InvokeMethod.<br /><br /> Obwohl der <xref:System.Activities.Activity.DisplayName%2A> nicht zwingend erforderlich ist, wird empfohlen, einen Anzeigenamen zu verwenden.|  
|<xref:System.Activities.Statements.InvokeMethod.MethodName%2A>|True|Der Name der Methode, die bei Ausführung der Aktivität aufgerufen werden soll. Die aufgerufene Methode muss deklariert werden, als **öffentliche**. Diese Eigenschaft kann in der Designeroberfläche bearbeitet werden. Dies ist eine obligatorische Eigenschaft.|  
|<xref:System.Activities.Statements.InvokeMethod.Parameters%2A>|False|Die Parameterauflistung der aufgerufenen Methode. Die Parameter müssen der Auflistung in derselben Reihenfolge wie in der Methodensignatur hinzugefügt werden. Klicken Sie im Eigenschaftenraster auf die Schaltfläche mit den Auslassungspunkten, in der **Parameter** -Feld die **Parameter** Dialogfeld Sie diese Eigenschaft festlegen können. Klicken Sie auf die **Argument erstellen** , um die Parameter hinzuzufügen.|  
|<xref:System.Activities.Statements.InvokeMethod.Result%2A>|False|Der Rückgabewert des Methodenaufrufs.|  
|<xref:System.Activities.Statements.InvokeMethod.RunAsynchronously%2A>|True|Gibt an, ob die Methode asynchron aufgerufen wird. Der Standardwert ist **"false"**.|  
|<xref:System.Activities.Statements.InvokeMethod.TargetObject%2A>|False|Das Objekt, das die aufzurufende Methode enthält. Diese Eigenschaft kann in der Designeroberfläche bearbeitet werden.<br /><br /> Es muss entweder das <xref:System.Activities.Statements.InvokeMethod.TargetObject%2A>-Objekt oder der <xref:System.Activities.Statements.InvokeMethod.TargetType%2A>-Typ festgelegt werden.|  
|<xref:System.Activities.Statements.InvokeMethod.TargetType%2A>|False|Der <xref:System.Activities.Statements.InvokeMethod.TargetObject%2A>-Typ. Diese Eigenschaft kann in der Designeroberfläche bearbeitet werden. Diese Eigenschaft muss nur festgelegt werden, wenn die aufgerufene Methode statisch ist.|  
  
 Zum Übergeben von Parametern als c# **out** Parameter (z. B. `Method1(out myParam)),` verwenden Sie **OutArgument** anstelle von **InOutArgument**  
  
 Methoden mit Argumenten namens **TargetObject** oder **Ergebnis** kann nicht aufgerufen werden, mithilfe der <xref:System.Activities.Statements.InvokeMethod> Aktivität. Der Grund dafür ist, dass die <xref:System.Activities.Statements.InvokeMethod>-Aktivität <xref:System.Activities.Statements.InvokeMethod.GenericTypeArguments%2A>, <xref:System.Activities.Statements.InvokeMethod.TargetObject%2A> und <xref:System.Activities.Statements.InvokeMethod.Result%2A> in <xref:System.Activities.Activity.CacheMetadata%2A> registriert.  
  
 Der Algorithmus zum Registrieren der Parameter in <xref:System.Activities.Activity.CacheMetadata%2A> wird in der folgenden Liste dargestellt:  
  
1.  Registrieren Sie das <xref:System.Activities.Statements.InvokeMethod.TargetObject%2A>-Argument.  
  
2.  Registrieren Sie das <xref:System.Activities.Statements.InvokeMethod.Result%2A>-Argument.  
  
3.  Durchlaufen Sie die <xref:System.Activities.Statements.InvokeMethod.Parameters%2A>-Auflistung, und registrieren Sie jedes Argument.  
  
 Die resultierende Ausnahme hat den Typ <xref:System.Activities.InvalidWorkflowException> mit der folgenden Meldung: 'InvokeMethod': Eine Variable, RuntimeArgument oder ein DelegateArgument ist bereits mit dem Namen 'TargetObject' vorhanden. Namen müssen innerhalb einer Umgebung eindeutig sein.  
  
 Diese Einschränkung gilt nicht für <xref:System.Activities.Statements.InvokeMethod.TargetType%2A> und <xref:System.Activities.Statements.InvokeMethod.RunAsynchronously%2A>, da sie keine Workflowargumente sind und daher nicht in der <xref:System.Activities.Statements.InvokeMethod.GenericTypeArguments%2A>-Auflistung der <xref:System.Activities.Statements.InvokeMethod>-Aktivität in der <xref:System.Activities.Activity.CacheMetadata%2A>-Methode registriert werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Primitive Typen](../workflow-designer/primitives-activity-designers.md)   
 [Weisen Sie](../workflow-designer/assign-activity-designer.md)   
 [Verzögerung](../workflow-designer/delay-activity-designer.md)   
 [WriteLine](../workflow-designer/writeline-activity-designer.md)