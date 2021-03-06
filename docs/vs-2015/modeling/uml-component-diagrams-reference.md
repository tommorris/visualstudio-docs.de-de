---
title: 'UML-Komponentendiagramme: Verweisen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.teamarch.componentdiagram.diagram
- vs.teamarch.componentdiagram.toolbox
- vs.teamarch.UMLModelExplorer.componentdiagram
helpviewer_keywords:
- UML diagrams, component
- diagrams - modeling, component
- diagrams - modeling, UML component
- UML, component diagrams
- component diagrams
ms.assetid: 5eddff6a-892a-4c3c-9278-687ac1eccc50
caps.latest.revision: 38
author: alexhomer1
ms.author: gewarren
manager: douge
ms.openlocfilehash: f628ebfa84246c6d991543352f4de36a51cc7fbf
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47522857"
---
# <a name="uml-component-diagrams-reference"></a>UML-Komponentendiagramme: Referenz
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [UML-Komponentendiagramme: Referenz](https://docs.microsoft.com/visualstudio/modeling/uml-component-diagrams-reference).  
  
In Visual Studio eine *Komponentendiagramm* zeigt die Teile eines Entwurfs für ein Softwaresystem. Ein Komponentendiagramm unterstützt Sie bei der Darstellung der allgemeinen Struktur des Systems und des Dienstverhaltens, das diese Teile bieten und über Schnittstellen nutzen. Zum Erstellen eines UML-Komponentendiagramms, auf die **Architektur** Menü klicken Sie auf **neues UML- oder Ebenendiagramm**.  
  
 Welche Versionen von Visual Studio dieses Feature unterstützen, erfahren Sie unter [Versionsunterstützung für Architektur- und Modellierungstools](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).  
  
 Sie können ein Komponentendiagramm zum Beschreiben eines Entwurfs nutzen, der in einer beliebigen Sprache oder einem beliebigen Stil implementiert wird. Sie müssen nur Teile des Entwurfs identifizieren, die mit den anderen Teilen des Entwurfs über einen beschränkten Satz von Eingaben und Ausgaben interagieren. Die Komponenten können einen beliebigen Umfang aufweisen und in beliebiger Weise miteinander verbunden sein.  
  
 Weitere Informationen zur Verwendung von Komponentendiagrammen während des Entwurfsprozesses finden Sie unter [Modellieren der Architektur Ihrer app](../modeling/model-your-app-s-architecture.md).  
  
> [!NOTE]
>  In diesem Thema werden die Elemente beschrieben, die Sie in Komponentendiagrammen verwenden können. Weitere Informationen finden Sie unter Informationen zum Zeichnen von Komponentendiagrammen finden Sie [UML-Komponentendiagramme: Richtlinien](../modeling/uml-component-diagrams-guidelines.md). Weitere Informationen zum allgemeinen Zeichnen von Modellierungsdiagrammen finden Sie unter [Bearbeiten von UML-Modellen und Diagrammen](../modeling/edit-uml-models-and-diagrams.md).  
  
## <a name="reading-component-diagrams"></a>Lesen von Komponentendiagrammen  
 In der folgenden Tabelle werden die Elemente beschrieben, die Sie in einem Komponentendiagramm verwenden können, sowie ihre Haupteigenschaften. Eine vollständige Liste der Eigenschaften der Elemente, finden Sie unter [Eigenschaften von Elementen in UML-Komponentendiagrammen](../modeling/properties-of-elements-on-uml-component-diagrams.md).  
  
 ![In Komponentendiagrammen verwendete Elemente](../modeling/media/uml-compovreading.png "UML_CompOvReading")  
  
|**Form "**|**Element**|**Beschreibung und Haupteigenschaften**|  
|---------------|-----------------|-----------------------------------------|  
|1|**Komponente**|Ein wiederverwendbarer Teil der Systemfunktionalität. Eine Komponente bietet und nutzt Verhalten über Schnittstellen und kann andere Komponenten verwenden.<br /><br /> Sie können die internen Teile einer Komponente mithilfe des Steuerelements zum Erweitern/Reduzieren (9) ausblenden oder anzeigen.<br /><br /> Eine Komponente ist eine Art von Klasse.<br /><br /> -   **Is Indirectly Instantiated**. Bei „true“ ist die Komponente nur als Entwurfsartefakt vorhanden. Zur Laufzeit sind nur die Teile vorhanden.|  
|2|**Bereitgestellter Schnittstellenanschluss**|Stellt ein Gruppe von Meldungen oder Aufrufen dar, die eine Komponente implementiert und die andere Komponenten oder externe Systeme verwenden können. Ein Anschluss ist eine Eigenschaft einer Komponente, die eine Schnittstelle als Typ aufweist.|  
|3|**Erforderlicher Schnittstellenanschluss**|Stellt ein Gruppe von Meldungen oder Aufrufen dar, die die Komponente an andere Komponenten oder externe Systeme sendet. Die Komponente ist darauf ausgelegt, mit Komponenten gekoppelt zu werden, die mindestens diese Vorgänge bereitstellen. Der Anschluss weist eine Schnittstelle als Typ auf.|  
|4|**Abhängigkeit**|Kann verwendet werden, um anzugeben, dass die Anforderung hinsichtlich einer erforderlichen Schnittstelle einer Komponente durch eine bereitgestellte Schnittstelle einer anderen Komponente erfüllt werden kann.<br /><br /> Abhängigkeiten können auch allgemeiner zwischen Modellelementen verwendet werden, um anzuzeigen, dass der Entwurf eines Elements von dem Entwurf des anderen abhängt.|  
|5|**Teil**|Ein Attribut einer Komponente, dessen Typ normalerweise eine andere Komponente ist. Ein Teil wird im internen Entwurf der übergeordneten Komponente verwendet. Teile werden grafisch innerhalb der übergeordneten Komponente geschachtelt angezeigt.<br /><br /> Um einen Teil eines vorhandenen Komponententyps zu erstellen, ziehen Sie die Komponente aus dem UML-Modell-Explorer auf die Besitzerkomponente.<br /><br /> Um einen Teil eines neuen Typs zu erstellen, klicken Sie auf die **Komponente** Konfigurationstool, und klicken Sie dann auf die Besitzerkomponente.<br /><br /> Angenommen, eine Komponente `Car` besitzt die Teile `engine:CarEngine`, `backLeft:Wheel`, `frontRight:Wheel` usw.<br /><br /> Mehr als ein Teil kann denselben Typ aufweisen, und unterschiedliche Komponenten können über Teile desselben Typs verfügen.<br /><br /> -   **Typ**. Der Typ des Teils, der an anderer Stelle im Modell definiert ist. Der Typ ist normalerweise eine andere Komponente.<br />-   **Multiplizität**. Der Standardwert ist 1. Sie können sie festlegen, um **0.. 1** anzugeben, dass das Teil den Wert kann **null**, **\*** , um anzugeben, dass das Teil eine Auflistung von Instanzen des angegebenen Typs, oder auf einen anderen Ausdruck, der zu einem Bereich von Nummern ausgewertet werden kann.|  
|6|**Teilassembly**|Eine Verbindung zwischen den erforderlichen Schnittstellenanschlüssen eines Teils und den bereitgestellten Schnittstellenanschlüssen eines anderen Teils. Die Implementierung einer Teilassembly kann sich bei den verschiedenen Komponenten unterscheiden. Die verbundenen Teile müssen dieselbe übergeordnete Komponente aufweisen.|  
|7|**Delegierung**|Verknüpft einen Anschluss mit einer Schnittstelle eines der Teile der Komponente. Gibt an, dass an die Komponente gesendete Meldungen von dem Teil behandelt werden, oder dass von dem Teil gesendete Meldungen von der übergeordneten Komponente aus gesendet werden.|  
|(nicht angezeigt)|**Generalisierung**|Gibt an, dass eine Komponente von einer anderen Komponente erbt. Teile und Schnittstellen werden geerbt.|  
|9|Steuerelement zum Reduzieren/Erweitern|Verwenden Sie dieses, um die internen Teile einer Komponente anzuzeigen oder auszublenden.|  
|(nicht angezeigt)|**Kommentar**|Für zusätzliche Hinweise. Sie können einen Kommentar auf eine beliebige Anzahl von Elementen im Diagramm verknüpfen, indem Sie mit der **Connector** Tool.|  
  
## <a name="see-also"></a>Siehe auch  
 [Bearbeiten von UML-Modellen und-Diagrammen](../modeling/edit-uml-models-and-diagrams.md)   
 [UML-Komponentendiagramme: Richtlinien](../modeling/uml-component-diagrams-guidelines.md)   
 [Überprüfen des Systems während der Entwicklung](../modeling/validate-your-system-during-development.md)   
 [UML-Anwendungsfalldiagramme: Referenz](../modeling/uml-use-case-diagrams-reference.md)   
 [UML-Klassendiagramme: Referenz](../modeling/uml-class-diagrams-reference.md)   
 [UML-Aktivitätsdiagramme: Referenz](../modeling/uml-activity-diagrams-reference.md)   
 [UML-Sequenzdiagramme: Referenz](../modeling/uml-sequence-diagrams-reference.md)



