---
title: Anzeigen von Dateien öffnen mit-Befehl mit | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- project types, supporting Open With command
- Open With command
- persistence, supporting Open With command
ms.assetid: 53794bc3-1b73-4d40-954e-cfade1abddcf
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6983e9ee7b7cc88efb4870ab0836b856621aeeee
ms.sourcegitcommit: 1c2ed640512ba613b3bbbc9ce348e28be6ca3e45
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/03/2018
ms.locfileid: "39497527"
---
# <a name="display-files-by-using-the-open-with-command"></a>Anzeigen von Dateien mithilfe des Befehls Öffnen mit
Ein Projekt lassen die IDE zum Anzeigen der **Öffnen mit** Dialogfeld. Diese Anforderung fordert den Benutzer zum Öffnen einer Datei, die eine Auswahl von standard-Editoren. Die folgenden Schritte beschreiben, diesen Prozess:  
  
1.  Die projektaufrufe <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A>, geben Sie einen Wert `OSE_UseOpenWithDialog` für die `OSEOpenDocEditor` Parameter.  
  
2.  Basierend auf der Dateinamenerweiterung des Dokuments ab, die IDE bestimmt, welche Editoren aufgeführt, die in der Registrierung kann das angegebene Dokument geöffnet und zeigt diese Informationen in den **Öffnen mit** Dialogfeld.  
  
    > [!NOTE]
    >  Projekte, die einen systeminternen Editor verfügen, die im enthalten sein müssen die **Öffnen mit** im Dialogfeld eine Editorfactory für jeden solchen Editor registrieren muss. Systeminterne Editoren funktionieren nur zusammen mit der eine bestimmte Art von Projekt, das in der Implementierung der erzwungen wird die <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> Methode. Die IDE hat eine integrierten Editorfactory für die kerntext-Editor und dem Binär-Editor. Die IDE erstellt auch eine Instanz von einer Editorfactory für jede registrierte Windows-dateizuordnung. Ein Beispiel für eine solche Datei ist Microsoft Word.  
  
3.  Sobald der Benutzer ein Element auswählt der **Öffnen mit** (Dialogfeld), klicken Sie dann die IDE Öffnet das Dokument durch Aufrufen von <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> Methode. Weitere Informationen finden Sie unter [Vorgehensweise: Öffnen Sie die standard-Editoren](../../extensibility/how-to-open-standard-editors.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Öffnen und Speichern von Projektelementen](../../extensibility/internals/opening-and-saving-project-items.md)   
 [Anzeigen von Dateien mithilfe des Befehls Öffnen von Dateien](../../extensibility/internals/displaying-files-by-using-the-open-file-command.md)   
 [Gewusst wie: Öffnen Sie die standard-Editoren](../../extensibility/how-to-open-standard-editors.md)
