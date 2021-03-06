---
title: RequiresFramework35SP1Assembly-Aufgabe | Microsoft-Dokumentation
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- RequiresFramework35SP1Assembly task [MSBuild]
- MSBuild, RequiresFramework35SP1Assembly task
ms.assetid: 755c018a-8a8b-4c94-8aee-3f171fc419e5
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a0ffc3b685314983949026a67f9be95f0fce1245
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47514739"
---
# <a name="requiresframework35sp1assembly-task"></a>RequiresFramework35SP1Assembly-Aufgabe
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [RequiresFramework35SP1Assembly-Aufgabe](https://docs.microsoft.com/visualstudio/msbuild/requiresframework35sp1assembly-task).  
  
  
Bestimmt, ob die Anwendung .NET Framework 3.5 SP1 erfordert  
  
## <a name="parameters"></a>Parameter  
 In der folgenden Tabelle werden die Parameter der `RequiresFramework35SP1Assembly` -Aufgabe beschrieben.  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`Assemblies`|Optionaler <xref:Microsoft.Build.Framework.ITaskItem>`[]`-Parameter<br /><br /> Gibt die Assemblys an, auf die in der Anwendung verwiesen wird.|  
|`CreateDesktopShortcut`|Optionaler `Boolean` -Parameter.<br /><br /> Wenn `true` wird bei der Installation ein Verknüpfungssymbol auf dem Desktop erstellt.|  
|`DeploymentManifestEntryPoint`|Optionaler <xref:Microsoft.Build.Framework.ITaskItem> -Parameter.<br /><br /> Gibt den Namen der Manifestdatei für die Anwendung an.|  
|`EntryPoint`|Optionaler <xref:Microsoft.Build.Framework.ITaskItem> -Parameter.<br /><br /> Gibt die Assembly an, die ausgeführt werden soll, wenn die Anwendung ausgeführt wird.|  
|`ErrorReportUrl`|Optionaler `String` -Parameter.<br /><br /> Gibt die URL der Website an, die in Dialogfeldern angezeigt wird, die bei den ClickOnce-Installationen auftreten.|  
|`Files`|Optionaler <xref:Microsoft.Build.Framework.ITaskItem>`[]`-Parameter<br /><br /> Gibt die Liste der Dateien an, die bereitgestellt werden, wenn die Anwendung veröffentlicht wird.|  
|`ReferencedAssemblies`|Optionaler <xref:Microsoft.Build.Framework.ITaskItem>`[]`-Parameter<br /><br /> Gibt die Assemblys an, auf die in dem Projekt verwiesen wird.|  
|`RequiresMinimumFramework35SP1`|Optionaler `Boolean`-Ausgabeparameter.<br /><br /> Wenn `true`, erfordert die Anwendung .NET Framework 3.5 SP1.|  
|`SigningManifests`|Optionaler `Boolean`-Ausgabeparameter.<br /><br /> Wenn `true`, werden die ClickOnce-Manifeste signiert.|  
|`SuiteName`|Optionaler `String` -Parameter.<br /><br /> Gibt den Namen des Ordners im Menü **Start** an, in dem die Anwendung installiert wird.|  
|`TargetFrameworkVersion`|Optionaler `String` -Parameter.<br /><br /> Gibt die .NET Framework-Version an, auf die diese Anwendung ausgerichtet ist.|  
  
## <a name="remarks"></a>Hinweise  
 Zusätzlich zu den in der Tabelle aufgeführten Parametern erbt dieser Task Parameter von der <xref:Microsoft.Build.Tasks.TaskExtension>-Klasse, die selbst von der <xref:Microsoft.Build.Utilities.Task>-Klasse erbt. Eine Liste mit diesen zusätzlichen Parametern und ihren Beschreibungen finden Sie unter [TaskExtension Base Class](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Tasks (Aufgaben)](../msbuild/msbuild-tasks.md)   
 [Aufgabenreferenz](../msbuild/msbuild-task-reference.md)



