---
title: 'Vorgehensweise: ändern ein Standardmenübefehls in einer domänenspezifischen Sprache | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- .vsct files, adding commands to a domain-specific language
- Domain-Specific Language, adding custom commands
ms.assetid: 9b9d8314-d0d8-421a-acb9-d7e91e69825c
caps.latest.revision: 12
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 740e26434190857907af61170222922180abc9b8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47513118"
---
# <a name="how-to-modify-a-standard-menu-command-in-a-domain-specific-language"></a>Gewusst wie: Ändern eines Standardmenübefehls in einer domänenspezifischen Sprache
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [Vorgehensweise: Ändern Sie einen Befehl in einer domänenspezifischen Sprache Standard](https://docs.microsoft.com/visualstudio/modeling/how-to-modify-a-standard-menu-command-in-a-domain-specific-language).  
  
Sie können das Verhalten einiger Standardbefehle ändern, die automatisch im DSL definiert sind. Sie könnten z. B. ändern **Ausschneiden** , damit sie vertrauliche Informationen ausschließt. Hierzu überschreiben Sie Methoden in einer festgelegten Klasse des Befehls. Diese Klassen sind in der CommandSet.cs-Datei im DslPackage-Projekt definiert und von <xref:Microsoft.VisualStudio.Modeling.Shell.CommandSet> abgeleitet.  
  
 Alles in allem ändern Sie einen Befehl folgendermaßen:  
  
1.  [Ermitteln, welche Befehle Sie ändern können](#what).  
  
2.  [Erstellen Sie eine partielle Deklaration der festgelegten Klasse des entsprechenden Befehls](#extend).  
  
3.  [Überschreiben Sie die Methoden ProcessOnStatus und ProcessOnMenu](#override) für den Befehl.  
  
 In diesem Thema wird diese Vorgehensweise erläutert.  
  
> [!NOTE]
>  Wenn Sie eigene Menübefehle erstellen möchten, finden Sie unter [Vorgehensweise: Hinzufügen eines Befehls zum Kontextmenü](../modeling/how-to-add-a-command-to-the-shortcut-menu.md).  
  
##  <a name="what"></a> Welche Befehle können Sie ändern?  
  
#### <a name="to-discover-what-commands-you-can-modify"></a>So ermitteln Sie, welche Befehle Sie ändern können  
  
1.  In der `DslPackage` geöffneten Projekt `GeneratedCode\CommandSet.cs`. Diese C#-Datei finden Sie im Projektmappen-Explorer als untergeordnete `CommandSet.tt`.  
  
2.  Suchen von Klassen in dieser Datei, deren Namen enden mit "`CommandSet`", z. B. `Language1CommandSet` und `Language1ClipboardCommandSet`.  
  
3.  Geben Sie in jeder festgelegten Klasse des Befehls "`override`" gefolgt von einem Leerzeichen ein. IntelliSense zeigt eine Liste der Methoden an, die Sie überschreiben können. Jeder Befehl verfügt über ein Paar von Methoden, deren Namen mit "`ProcessOnStatus`" und "`ProcessOnMenu`" beginnen.  
  
4.  Beachten Sie, welche der festgelegten Klassen des Befehls den Befehl enthält, den Sie verändern möchten.  
  
5.  Schließen Sie die Datei, ohne Ihre Änderungen zu speichern.  
  
    > [!NOTE]
    >  Normalerweise sollten Sie keine Dateien bearbeiten, die generiert wurden. Änderungen gehen verloren, wenn die Dateien das nächste Mal generiert werden.  
  
##  <a name="extend"></a> Erweitern Sie den entsprechenden Befehl Set-Klasse  
 Erstellen Sie eine neue Datei, die eine partielle Deklaration der festgelegten Klasse des Befehls enthält.  
  
#### <a name="to-extend-the-command-set-class"></a>So erweitern Sie die festgelegte Klasse des Befehls  
  
1.  Öffnen Sie im Solution Explorer, im DslPackage-Projekt, den Ordner "GeneratedCode". Öffnen Sie dann unter "CommandSet.tt" die generierte Datei "CommandSet.cs". Notieren Sie sich den Namespace und den Namen der ersten dort definierten Klasse. Sie könnten dort z. B. Folgendes sehen:  
  
     `namespace Company.Language1`  
  
     `{ ...  internal partial class Language1CommandSet : ...`  
  
2.  In **DslPackage**, erstellen Sie einen Ordner mit dem Namen **benutzerdefinierter Code**. Erstellen Sie in diesem Ordner eine neue Klassendatei mit dem Namen `CommandSet.cs`.  
  
3.  Schreiben Sie in die neue Datei eine partielle Deklaration mit demselben Namespace und Namen wie die generierte partielle Klasse. Zum Beispiel:  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.ComponentModel.Design;  
    namespace Company.Language1 /* Make sure this is correct */  
    { internal partial class Language1CommandSet { ...  
    ```  
  
     **Beachten Sie** , wenn Sie die klassendateivorlage verwendet, um die neue Datei erstellen, müssen Sie korrigieren, sowohl den Namespace und den Namen der Klasse.  
  
##  <a name="override"></a> Überschreiben der Befehlsmethoden  
 Die meisten Befehle haben zwei zugehörige Methoden: die Methode mit einem Namen wie `ProcessOnStatus`... bestimmt, ob der Befehl sichtbar und aktiviert werden soll. Sie wird aufgerufen, wenn der Benutzer mit der rechten Maustaste auf das Diagramm klickt und sollte schnell ausgeführt werden sowie keine Änderungen vornehmen. `ProcessOnMenu`... wird aufgerufen, wenn der Benutzer klickt auf den Befehl aus, und führen Sie die Funktion des Befehls sollte. Sie können eine dieser oder beide Methoden überschreiben.  
  
### <a name="to-change-when-the-command-appears-on-a-menu"></a>Ändern, wann der Befehl in einem Menü angezeigt wird  
 Überschreiben Sie die ProcessOnStatus... Methode. Diese Methode sollte für den Parameter MenuCommand die Eigenschaften "Visible" (sichtbar) und "Enabled" (aktiviert) festlegen. Meist prüft der Befehl CurrentSelection, um zu bestimmen, ob der Befehl auf die ausgewählten Elemente zutrifft. Möglicherweise werden auch die Eigenschaften geprüft, um zu bestimmen, ob der Befehl bei deren aktuellem Status angewendet werden kann.  
  
 Allgemein gilt, die Eigenschaft "Visible" sollte dadurch bestimmt werden, welche Elemente ausgewählt sind. Die Eigenschaft "Enabled", die bestimmt, ob der Befehl im Menü schwarz oder ausgegraut angezeigt wird, sollte vom aktuellen Status der Auswahl abhängen.  
  
 Im folgenden Beispiel wird das Menüelement "Delete" (Löschen) deaktiviert, wenn der Benutzer mehr als eine Form ausgewählt hat.  
  
> [!NOTE]
>  Diese Methode beeinflusst nicht, ob der Befehl über eine Tastatureingabe verfügbar ist. Zum Beispiel verhindert das Deaktivieren des Menüelements "Delete" (Löschen) nicht, dass der Befehl über die Entf-Taste ausgelöst wird.  
  
```  
/// <summary>  
/// Called when user right-clicks on the diagram or clicks the Edit menu.  
/// </summary>  
/// <param name="command">Set Visible and Enabled properties.</param>  
protected override void ProcessOnStatusDeleteCommand (MenuCommand command)  
{  
  // Default settings from the base method.  
  base.ProcessOnStatusDeleteCommand(command);  
  if (this.CurrentSelection.Count > 1)  
  {  
    // If user has selected more than one item, Delete is greyed out.  
    command.Enabled = false;  
  }  
}  
```  
  
 Es ist empfehlenswert, zuerst die Basismethode aufzurufen, um alle Fälle und Einstellungen zu behandeln, die nicht enthalten sind.  
  
 Die ProcessOnStatus-Methode sollte Elemente im Speicher nicht erstellen, löschen oder aktualisieren.  
  
### <a name="to-change-the-behavior-of-the-command"></a>So ändern Sie das Verhalten des Befehls  
 Überschreiben Sie die ProcessOnMenu... Methode. Im folgenden Beispiel wird der Benutzer davon abgehalten, mehr als ein Element auf einmal zu löschen, selbst mit der Entf-Taste.  
  
```  
/// <summary>  
/// Called when user presses Delete key   
/// or clicks the Delete command on a menu.  
/// </summary>  
protected override void ProcessOnMenuDeleteCommand()  
{  
  // Allow users to delete only one thing at a time.  
  if (this.CurrentSelection.Count <= 1)  
  {  
    base.ProcessOnMenuDeleteCommand();  
  }  
}  
```  
  
 Wenn der Code Änderungen am Speicher vornimmt, wie Erstellen, Löschen oder Aktualisieren von Elementen oder Links, muss dies innerhalb einer Transaktion erfolgen. Weitere Informationen finden Sie unter [wie erstellen und Aktualisieren von Modellelementen](../modeling/how-to-modify-a-standard-menu-command-in-a-domain-specific-language.md).  
  
### <a name="writing-the-code-of-the-methods"></a>Schreiben des Methodencodes  
 Die folgenden Fragmente sind innerhalb dieser Methoden oft hilfreich:  
  
-   `this.CurrentSelection` Die Form, die der Benutzer mit der rechten Maustaste angeklickt hat, ist immer in dieser Liste mit Formen und Konnektoren enthalten. Wenn der Benutzer auf einen leeren Teil des Diagramms klickt, ist das Diagramm als einziges Teil der Liste.  
  
-   `this.IsDiagramSelected()` - `true` Wenn der Benutzer einen leeren Bereich des Diagramms geklickt hat.  
  
-   `this.IsCurrentDiagramEmpty()`  
  
-   `this.IsSingleSelection()` -der Benutzer hat nicht mehrere Formen ausgewählt  
  
-   `this.SingleSelection` – die Form oder das Diagramm, auf das der Benutzer mit der rechten Maustaste geklickt hat  
  
-   `shape.ModelElement as MyLanguageElement` – das Modellelement, das durch eine Form dargestellt wird  
  
 Weitere Informationen zur Verwendung von Element zu Element navigieren und Informationen zum Erstellen von Objekten und Links finden Sie unter [Navigieren in und Aktualisieren von Modellen im Programmcode](../modeling/navigating-and-updating-a-model-in-program-code.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ComponentModel.Design.MenuCommand>   
 [Schreiben von Code zum Anpassen einer domänenspezifischen Sprache](../modeling/writing-code-to-customise-a-domain-specific-language.md)   
 [Vorgehensweise: Hinzufügen eines Befehls zum Kontextmenü](../modeling/how-to-add-a-command-to-the-shortcut-menu.md)   
 [Exemplarische Vorgehensweise: Abrufen von Informationen von einem ausgewählten Link](../misc/walkthrough-getting-information-from-a-selected-link.md)   
 [Wie VSPackages Benutzeroberflächenelemente hinzufügen](../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [Visual Studio-Befehlstabelle (. VSCT)-Dateien](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)   
 [VSCT-XML-Schemareferenz](../extensibility/vsct-xml-schema-reference.md)   
 [VMSDK: Circuit Diagrams Sample. Umfassende DSL-Anpassung](http://code.msdn.microsoft.com/Visualization-Modeling-SDK-763778e8)   
 [Beispielcode: Schaltpläne](http://code.msdn.microsoft.com/Visualization-Modeling-SDK-763778e8)



