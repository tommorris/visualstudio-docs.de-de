---
title: Dialogfeld „Befehlszeile für Präbuildereignis“/„Befehlszeile für Postbuildereignis“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- cs.ProjectPropertiesBuildEventsBuilder
- vb.ProjectPropertiesBuildEventsBuilder
helpviewer_keywords:
- $(SolutionExt)
- $(ProjectDir)
- $(TargetPath)
- $(ProjectExt)
- $(TargetFileName)
- $(PlatformName)
- $(SolutionName)
- macros, build events
- $(SolutionPath)
- $(ProjectPath)
- $(ProjectFileName)
- $(DevEnvDir)
- $(TargetName)
- $(TargetDir)
- $(SolutionDir)
- $(TargetExt)
- $(OutDir)
- $(ConfigurationName)
- $(SolutionFileName)
- $(ProjectName)
- build events, macros
ms.assetid: d49b2c57-24bf-4fb2-8351-5c4b6cca938f
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 57dae16903a8ee1398a6e5e19c4c111585ec29f8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47509084"
---
# <a name="pre-build-eventpost-build-event-command-line-dialog-box"></a>Dialogfeld "Befehlszeile für Präbuildereignis"/"Befehlszeile für Postbuildereignis"
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [Pre-Build Event-Post-Build Event Command Line Dialog Box](https://docs.microsoft.com/visualstudio/ide/reference/pre-build-event-post-build-event-command-line-dialog-box).  
  
  
Sie können Prä- oder Postbuildereignisse für die [Seite „Buildereignisse“, Projekt-Designer (C#)](../../ide/reference/build-events-page-project-designer-csharp.md) direkt in das Bearbeitungsfeld eingeben oder Prä- und Postbuildmakros aus der Liste der verfügbaren Makros auswählen.  
  
> [!NOTE]
>  Präbuildereignisse werden nicht ausgeführt, wenn das Projekt auf dem neuesten Stand ist, und es wird kein Build gestartet.  
  
## <a name="ui-element-list"></a>Liste der Elemente der Benutzeroberfläche  
 **Bearbeitungsfeld der Befehlszeile**  
 Enthält die auszuführenden Ereignisse für den Prä- oder Postbuild.  
  
> [!NOTE]
>  Fügen Sie allen Postbuildbefehlen, die BAT-Dateien ausführen, eine `call`-Anweisung hinzu. Beispielsweise `call C:\MyFile.bat` oder `call C:\MyFile.bat call C:\MyFile2.bat`.  
  
 **Makros**  
 Erweitert das Bearbeitungsfeld, um eine Liste der Makros anzuzeigen, die in das Bearbeitungsfeld der Befehlszeile eingefügt werden sollen.  
  
 **Makrotabelle**  
 Listet die verfügbaren Makros und deren Werte auf. Im Folgenden finden Sie eine Beschreibung der einzelnen Makros. Sie können nur ein Makro gleichzeitig in das Bearbeitungsfeld der Befehlszeile einfügen.  
  
 **Einfügen**  
 Fügt das in der Makrotabelle ausgewählte Makro in das Bearbeitungsfeld der Befehlszeile ein.  
  
### <a name="macros"></a>Makros  
 Sie können diese Makros verwenden, um Speicherorte für Dateien anzugeben oder bei einer Mehrfachauswahl den tatsächlichen Namen der Eingabedatei abrufen. Bei diesen Makros wird nicht zwischen Groß-/Kleinschreibung unterschieden.  
  
|Makro|Beschreibung|  
|-----------|-----------------|  
|`$(ConfigurationName)`|Der Name der aktuellen Projektkonfiguration, z.B. „Debug“.|  
|`$(OutDir)`|Der Pfad des Ausgabedateiverzeichnisses relativ zum Projektverzeichnis. Dies wird in den Wert für die Eigenschaft „Output Directory“ aufgelöst. Ein nachgestellter umgekehrter Schrägstrich („\\“) ist enthalten.|  
|`$(DevEnvDir)`|Das Installationsverzeichnis von Visual Studio (durch Laufwerk und Pfad definiert). Dieses enthält den nachgestellten umgekehrten Schrägstrich („\\“).|  
|`$(PlatformName)`|Der Name der aktuellen Zielplattform. Zum Beispiel „AnyCPU“.|  
|`$(ProjectDir)`|Das Verzeichnis des Projekts (durch Laufwerk und Pfad definiert). Dieses enthält den nachgestellten umgekehrten Schrägstrich („\\“).|  
|`$(ProjectPath)`|Der absolute Pfadname des Projekts (durch Laufwerk, Pfad, Basisname und Dateierweiterung definiert).|  
|`$(ProjectName)`|Der Basisname des Projekts.|  
|`$(ProjectFileName)`|Der Dateiname des Projekts (durch Basisname und Dateierweiterung definiert).|  
|`$(ProjectExt)`|Die Dateierweiterung des Projekts. Sie umfasst den „.“ vor der Dateierweiterung.|  
|`$(SolutionDir)`|Das Verzeichnis der Projektmappe (durch Laufwerk und Pfad definiert). Dieses enthält den nachgestellten umgekehrten Schrägstrich („\\“).|  
|`$(SolutionPath)`|Der absolute Pfadname der Projektmappe (durch Laufwerk, Pfad, Basisname und Dateierweiterung definiert).|  
|`$(SolutionName)`|Der Basisname der Projektmappe.|  
|`$(SolutionFileName)`|Der Dateiname der Projektmappe (durch Basisname und Dateierweiterung definiert).|  
|`$(SolutionExt)`|Die Dateierweiterung der Projektmappe. Sie umfasst den „.“ vor der Dateierweiterung.|  
|`$(TargetDir)`|Das Verzeichnis der primären Ausgabedatei für den Build (durch Laufwerk und Pfad definiert). Ein nachgestellter umgekehrter Schrägstrich („\\“) ist enthalten.|  
|`$(TargetPath)`|Der absolute Pfadname der primären Ausgabedatei für den Build (durch Laufwerk, Pfad, Basisname und Dateierweiterung definiert).|  
|`$(TargetName)`|Der Basisname der primären Ausgabedatei für den Build.|  
|`$(TargetFileName)`|Der Dateiname der primären Ausgabedatei für den Build (als Basisname und Dateierweiterung definiert).|  
|`$(TargetExt)`|Die Dateierweiterung der primären Ausgabedatei für den Build. Sie umfasst den „.“ vor der Dateierweiterung.|  
  
## <a name="see-also"></a>Siehe auch  
 [Angeben von benutzerdefinierten Buildereignissen in Visual Studio](../../ide/specifying-custom-build-events-in-visual-studio.md)   
 [Seite "Buildereignisse", Projekt-Designer (C#)](../../ide/reference/build-events-page-project-designer-csharp.md)   
 [Vorgehensweise: Festlegen von Buildereignissen (Visual Basic)](../../ide/how-to-specify-build-events-visual-basic.md)   
 [Gewusst wie: Angeben von Buildereignissen (C#)](../../ide/how-to-specify-build-events-csharp.md)



