---
title: Visual Studio-Befehlstabelle (. VSCT)-Dateien | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSCT files, overview
- Visual Studio command table configuration files (VSCT), overview
ms.assetid: 1313adb4-add4-4e74-90e2-f4be522f5259
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: eb1cf61f1c1120e27ffcb5a93eff35817f1ed0b3
ms.sourcegitcommit: 9765b3fcf89375ca499afd9fc42cf4645b66a8a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2018
ms.locfileid: "46495868"
---
# <a name="visual-studio-command-table-vsct-files"></a>VSCT-Dateien (Visual Studio Command Table)
Konfiguration eine Befehlsdatei-Tabelle ist eine Textdatei, die den Satz von Befehlen zu beschreiben, die VSPackages enthält. Die [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Befehl Tabelle (VSCT)-Compiler kompiliert XML-basierten Konfiguration (VSCT-Dateien) in binäre Befehl Tabelle Ausgabedateien (CTO). Die resultierende CTO-Dateien sind identisch mit denen, die mit dem Befehl-Tabelle (CTC)-Compiler zum Kompilieren der CTC-Konfigurationsdateien erstellt werden. XML-basierte VSCT-Dateien hat jedoch einige Vorteile, z. B. eine XML-Editor und IntelliSense für XML.  
  
 Weitere Informationen zu der Syntax und Semantik der VSCT-Dateien finden Sie unter [Entwerfen von XML-Command Table (. VSCT)-Dateien](../../extensibility/internals/designing-xml-command-table-dot-vsct-files.md)  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Entwerfen von Dateien für XML-Befehlstabellen (VSCT)](../../extensibility/internals/designing-xml-command-table-dot-vsct-files.md)  
 Beschreibt das Entwerfen der VSCT-Dateien.  
  
 [Gewusst wie: Erstellen einer VSCT-Datei](../../extensibility/internals/how-to-create-a-dot-vsct-file.md)  
 Vergleicht die Methoden zum Erstellen einer VSCT-Datei an. Beschreibt den Prozess zum manuellen Erstellen eine neue VSCT-Datei.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [VSCT-XML-Schemareferenz](../../extensibility/vsct-xml-schema-reference.md)  
 Enthält Details zu jedem Abschnitt des Befehls Tabelle XML-Datei.  
  
 [Konfiguration der Befehl (. CTC)-Dateien](https://msdn.microsoft.com/library/3413dda1-f372-4669-bcf0-c64d3463842c)  
 Bietet eine Übersicht über das veraltete CTC-Dateiformat.  
  
 [Hinzufügen von Benutzeroberflächenelementen mit VSPackages](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)  
 Beschreibt die Formatspezifikation der Befehl-Tabelle.  
  
 [Ressourcen in VSPackages](../../extensibility/internals/resources-in-vspackages.md)  
 Beschreibt die Verwendung von verwalteten und nicht verwalteten Ressourcen in verwaltete VSPackages.  
  
 [Befehle, Menüs und Symbolleisten](../../extensibility/internals/commands-menus-and-toolbars.md)  
 Erläutert, wie eine Benutzeroberfläche mit Menüs, Symbolleisten und Kombinationsfeldern für Befehle erstellt wird.