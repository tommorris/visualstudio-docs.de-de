---
title: 'Vorgehensweise: Lokalisieren einer Funktion | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- features [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, localizing
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: c143016aaec81c65c118923ff9513bb4607353dc
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2018
ms.locfileid: "37118950"
---
# <a name="how-to-localize-a-feature"></a>Vorgehensweise: Lokalisieren einer Funktion
  Standardmäßig die featuretitel und Beschreibungen, verwenden die hartcodierten Zeichenfolgenwerte. Um den Funktionstitel und die Beschreibung lokalisieren möchten, ersetzen Sie die Zeichenfolgen mit Ausdrücken, die lokalisierte Ressourcen zu verweisen.  
  
## <a name="localize-a-feature"></a>Lokalisieren einer Funktion  
  
#### <a name="to-localize-a-feature"></a>Zum Lokalisieren einer Funktion  
  
1.  In **Projektmappen-Explorer**, öffnen Sie das Kontextmenü für die **Feature1** Knoten, und wählen Sie dann **Funktionsressource hinzufügen**.  
  
2.  In der **Ressource hinzufügen** Dialogfeld wählen **invarianten Sprache** aus der Liste als Kultur für die Funktionsressourcendatei der Standardsprache.  
  
3.  Wiederholen Sie den vorherigen Schritt für jede lokalisierte Sprache, und wählen die Sprachen Ihrer Wahl für das lokalisierte Feature Ressourcendateien.  
  
     Separates Feature Ressourcendateien werden erstellt: eine für die Standardsprache und eine für jede lokalisierte Sprache, die Sie unterstützen möchten.  
  
4.  Öffnen Sie alle Ressourcen im Ressourcen-Editor, und geben Sie dann die Zeichenfolgen-IDs und ihre Werte.  
  
     Geben Sie beispielsweise in der Standard-Funktionsressourcendatei eine Zeichenfolgen-ID der **Titel** mit einem Wert von **Meine Funktionstitel**, und ein zweites Zeichenfolgen-ID des **Beschreibung** mit einem Wert von **Meine Featurebeschreibung**. Verwenden Sie für jede lokalisierte Ressourcendatei die gleiche Zeichenfolgen-IDs, die in der Standard-Feature-Ressource verwendet allerdings Geben Sie lokalisierte Zeichenfolgen für die Werte ein.  
  
5.  Nachdem Sie alle Werte der eingegeben haben, öffnen Sie das Kontextmenü für das Feature (z. B. *"Feature1.Feature"*), und wählen Sie dann **Ansicht-Designer** um das Feature in der Funktions-Designer zu öffnen.  
  
6.  Zum Lokalisieren der **Titel** und **Beschreibung** Felder in der Funktion verwenden Sie das folgende Format, Werte in die Felder einzugeben:  
  
     `$Resources:` *Zeichenfolgen-ID*  
  
     Geben Sie beispielsweise die $Resources:**Titel** in die **Funktionstitel** Box und $Resources:**Beschreibung** in die **Featurebeschreibung** Feld .  
  
     Die Zeichenfolgen-IDs muss denen entsprechen, die in den Ressourcendateien verwendet werden.  
  
7.  Wählen Sie die **F5** Schlüssel zu erstellen und Ausführen der Anwendung.  
  
8.  Öffnen Sie in SharePoint die **Websiteaktionen** Menü wählen **Standorteinstellungen**, und dann auf die **Websiteaktionen** "die Option" der **Websitefunktionen verwalten** Link.  
  
9. Legen Sie die Anzeigesprache in SharePoint auf eine Sprache fest, die nicht der Standardsprache entspricht.  
  
     Lokalisierte Feature Titel und Beschreibung werden in der Anwendung angezeigt. Zum Anzeigen lokalisierter Ressourcen muss auf dem SharePoint-Server ein Sprachpaket installiert sein, das der Kultur der Ressourcendatei entspricht.  
  
## <a name="see-also"></a>Siehe auch
 [Lokalisieren von SharePoint-Lösungen](../sharepoint/localizing-sharepoint-solutions.md)   
 [Gewusst wie: Hinzufügen einer Ressourcendatei](../sharepoint/how-to-add-a-resource-file.md)   
 [Vorgehensweise: Lokalisieren von ASPX-Markup](../sharepoint/how-to-localize-aspx-markup.md)   
 [Vorgehensweise: Lokalisieren von Code](../sharepoint/how-to-localize-code.md)  
  
