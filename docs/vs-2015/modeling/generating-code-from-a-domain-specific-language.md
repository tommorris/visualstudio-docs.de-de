---
title: Generieren von Code aus einer domänenspezifischen Sprache | Microsoft-Dokumentation
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e3706cc9-2afd-456a-a879-68425a248ebc
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 3fbe7e40a277174eb556a61b50eb88279adebfb2
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47522302"
---
# <a name="generating-code-from-a-domain-specific-language"></a>Generieren von Code für eine domänenspezifische Sprache
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [Generieren von Code aus einer domänenspezifischen Sprache](https://docs.microsoft.com/visualstudio/modeling/generating-code-from-a-domain-specific-language).  
  
Microsoft [!INCLUDE[dsl](../includes/dsl-md.md)] bietet eine leistungsstarke Möglichkeit zum Generieren von Code, Dokumenten, Konfigurationsdateien und andere Artefakte aus Daten, die in Modellen dargestellt. Mithilfe von [!INCLUDE[dsl](../includes/dsl-md.md)], können Sie einen Satz von Klassen, die Ihre Daten darstellen, erstellen und Sie können den Textvorlagen in schreiben Klassen, deren Namen und Eigenschaften stellen die Daten.  
  
 Fabrikam hat beispielsweise eine XML-Datei mit Kundennamen und e-Mail-Adressen. Ihre Entwickler erstellen Sie ein Modell, in denen Kunden eine Klasse mit Eigenschaften und die e-Mail-ist. Mehrere Textvorlagen zum Verarbeiten von Daten, einschließlich dieses Fragment der erzeugt eine Tabelle mit allen Kunden als Teil einer HTML-Seite geschrieben:  
  
```  
<table>  
<# foreach (Customer c in ContactList) {  #>  
  <tr><td> <#= c.FullName #> </td>   
      <td> <#= c.EmailAddress #> </td> </tr>  
<# } #>  </table>  
```  
  
 Wenn die Kundendatenbank verarbeitet wird, wird die XML-Datei in den Modellspeicher gelesen. Ein *anweisungsprozessor*, der mithilfe von [!INCLUDE[dsl](../includes/dsl-md.md)], stellt Sie die Customer-Klasse auf den Code zur Verfügung, in der Textvorlage. Viele Textvorlagen können für den gleichen Speicher ausgeführt werden.  
  
 Textvorlagen sind ein wesentlicher [!INCLUDE[dsl](../includes/dsl-md.md)]. Sie dienen zum Generieren von Quellcode für die Elemente des Domänenmodells sowie für das VSPackage und die Steuerelemente, die verwendet werden, um die Tools mit Integration [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].  
  
 Dieser Abschnitt beschreibt einige der Möglichkeiten zum Erstellen, ändern und Debuggen von Textvorlagen in verwendet [!INCLUDE[dsl](../includes/dsl-md.md)].  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Zugreifen auf Modelle aus Textvorlagen](../modeling/accessing-models-from-text-templates.md)  
  
 Enthält grundlegende Informationen zu einer domänenspezifischen Sprache in Textvorlagen auf.  
  
 [Exemplarische Vorgehensweise: Debuggen einer Textvorlage, die auf ein Modell zugreift](../modeling/walkthrough-debugging-a-text-template-that-accesses-a-model.md)  
  
 Beschreibt, wie Sie Problembehandlung und Debuggen in einer Textvorlage, die auf einer domänenspezifischen Sprache verweist.  
  
 [Exemplarische Vorgehensweise: Verbinden eines Hosts mit einem generierten Direktivenprozessor](../modeling/walkthrough-connecting-a-host-to-a-generated-directive-processor.md)  
  
 Beschreibt, wie die Verbindung mit einem generierten Direktivenprozessor einen benutzerdefinierten Host.  
  
 [Der DslTextTransform-Befehl](../modeling/the-dsltexttransform-command.md)  
  
 Beschreibt die Befehlsdatei, die die TextTransform ausführbare Datei in der Befehlszeile für Textvorlagen ausgeführt wird, die auf einer domänenspezifischen Sprachen zu verweisen.  
  
## <a name="reference"></a>Referenz  
 [Schreiben einer T4-Textvorlage](../modeling/writing-a-t4-text-template.md)  
  
 Enthält die Syntax der textvorlagenanweisungen und Kontrollblöcken.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Generieren von Code zur Entwurfszeit mithilfe von T4-Textvorlagen](../modeling/design-time-code-generation-by-using-t4-text-templates.md)  
  
 Erläutert das Textvorlagen-Transformationsprozess ab.  
  
 [Codegenerierung in einem Buildprozess](../modeling/code-generation-in-a-build-process.md)  
  
 Lesen Sie dieses Thema, wenn Sie aus einer DSL auf einem Buildserver-Dateien generieren.



