---
title: Verwenden von Modellen im Entwicklungsprozess
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- UML, using models
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c1d780f8ab293a9503f3c2c8675e4de1e3584b28
ms.sourcegitcommit: d7209d61e812b34d06c2aa267bdf50fbc714d0e0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2018
ms.locfileid: "42623596"
---
# <a name="use-models-in-your-development-process"></a>Verwenden von Modellen im Entwicklungsprozess

In Visual Studio können Sie ein Modell verwenden, um ein System, eine Anwendung oder eine Komponente zu verstehen und zu ändern. Mit einem Modell können Sie das Umfeld des Systems visuell darstellen, Anforderungen der Benutzer verdeutlichen, die Architektur des Systems definieren, den Code analysieren und sicherstellen, dass der Code die Anforderungen erfüllt. Finden Sie unter [Channel 9-Video: Verbessern der Architektur durch Modellierung](http://go.microsoft.com/fwlink/?LinkID=252078).

Informationen dazu, welche Versionen von Visual Studio die einzelnen Modelltypen unterstützen, finden Sie unter [Version support for architecture and modeling tools](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).

Modelle können auf verschiedene Weise von Nutzen sein:

- Durch das Zeichnen von Modellierungsdiagrammen können Sie die Konzepte für Anforderungen, Architektur und allgemeinen Entwurf verdeutlichen. Weitere Informationen finden Sie unter [Modellieren von benutzeranforderungen](../modeling/model-user-requirements.md).

- Durch das Arbeiten mit Modellen können Sie mangelnde Übereinstimmungen in den Anforderungen aufzeigen.

- Mithilfe von Modellen können Sie wichtige Konzepte eindeutiger als mithilfe von natürlicher Sprache mitteilen. Weitere Informationen finden Sie unter [Modellieren der Architektur Ihrer app](../modeling/model-your-app-s-architecture.md).

- Manchmal können Sie mithilfe von Modellen Code oder andere Artefakte generieren, z. B. Datenbankschemas oder Dokumente. Beispielsweise werden die Modellierungskomponenten von Visual Studio aus einem Modell generiert. Weitere Informationen finden Sie unter [generieren und Konfigurieren von Apps aus Modellen](../modeling/generate-and-configure-your-app-from-models.md).

Sie können Modelle in einer Vielzahl von Prozessen verwenden: von äußerst agilen bis zu sehr förmlichen Prozessen.

## <a name="use-models-to-reduce-ambiguity"></a>Verwenden Sie Modelle, um Mehrdeutigkeit zu reduzieren.

Die Modellierungssprache ist weniger mehrdeutig als natürliche Sprache, und sie ist zum Darstellen der Konzepte vorgesehen, die normalerweise während der Softwareentwicklung erforderlich sind.

Wenn das Projekt von einem kleinen Team mit agilen Verfahren durchgeführt wird, können Sie mithilfe von Modellen User Stories verdeutlichen. In Gesprächen mit den Kunden über ihre Anforderungen lassen sich durch das Erstellen eines Modells viel schneller hilfreiche Fragen generieren, und zwar zu einem breiteren Bereich des Produkts, als durch das Schreiben von Spike- oder Prototypcode.

Wenn das Projekt umfangreich ist und Teams aus verschiedenen Ländern auf dem Globus umfasst, können Sie mithilfe von Modellen die Anforderungen und Architektur effizienter als mit Klartext vermitteln.

In beiden Fällen lassen sich durch das Erstellen eines Modells mangelnde Übereinstimmungen und Mehrdeutigkeiten fast immer erheblich reduzieren. Unterschiedliche Projektbeteiligte verfügen über unterschiedliche Vorstellungen von dem Geschäftsumfeld, in dem das System eingesetzt wird, und unterschiedliche Entwickler verfügen häufig über unterschiedliche Vorstellungen von der Funktionsweise des Systems. Mit einem Modell als Mittelpunkt eines Gesprächs werden diese Unterschiede in der Regel aufgezeigt. Weitere Informationen dazu, wie Sie ein Modell zu verwenden, um Inkonsistenzen zu verringern, finden Sie unter [Modellieren von benutzeranforderungen](../modeling/model-user-requirements.md).

## <a name="use-models-with-other-artifacts"></a>Verwenden von Modellen mit anderen Artefakten

Ein Modell allein ist noch keine Anforderungsspezifikation oder Architektur. Es ist ein Werkzeug, um einige Aspekte klarer darzustellen, jedoch können nicht alle während des Softwareentwurfs erforderlichen Aspekte dargestellt werden. Die Modelle sollten daher zusammen mit anderen Kommunikationsmitteln, z. B. OneNote-Seiten oder -Absätzen, Microsoft Office-Dokumenten, Arbeitsaufgaben in [!INCLUDE[esprfound](../code-quality/includes/esprfound_md.md)] oder Haftnotizen an der Wand des Projektraums, verwendet werden. Außer dem letzten Element können alle diese Objekttypen mit Elementteilen des Modells verknüpft werden.

Zusammen mit Modellen werden gewöhnlich folgende weitere Spezifikationsaspekte verwendet. Je nach Umfang und Art des Projekts verwenden Sie eventuell mehrere oder keinen dieser Aspekte:

- User Stories: Eine User Story ist eine kurze Beschreibung eines Aspekts des Systemverhaltens, der mit Benutzern und anderen Projektbeteiligten erörtert und in einer der Iterationen des Projekts bereitgestellt wird. Eine typische User Story beginnt mit "Kunden können werden..." Eine User Story kann eine Gruppe von Anwendungsfällen einführen oder Erweiterungen von Anwendungsfällen definieren, die zuvor entwickelt wurden. Das Definieren oder Erweitern der Anwendungsfälle trägt zur größeren Verständlichkeit der User Story bei.

- Änderungsanforderungen: Ein Änderungsanforderung in einem eher formalen Projekt ist einer User Story in einem agilen Projekt sehr ähnlich. Bei der agilen Vorgehensweise werden alle Anforderungen als Änderungen der Entwicklung in vorherigen Iterationen behandelt.

- Anwendungsfallbeschreibung: Ein Anwendungsfall stellt eine der Methoden dar, mithilfe derer ein Benutzer mit dem System interagieren kann, um ein bestimmtes Ziel zu erreichen. Die vollständige Beschreibung enthält das Ziel, die Hauptsequenz und alternative Sequenzen von Ereignissen sowie außergewöhnliche Ergebnisse. Ein Anwendungsfalldiagramm bietet eine Zusammenfassung und einen Überblick über die Anwendungsfälle.

- Szenarien: Ein Szenario ist eine ausführliche Beschreibung einer Sequenz von Ereignissen, die darstellt, wie sich durch die Interaktion von System, Benutzern und anderen Systemen sinnvolle Ergebnisse für die Projektbeteiligten ergeben. Dabei kann es sich um eine Bildschirmpräsentation der Benutzeroberfläche oder einen Prototyp der Benutzeroberfläche handeln. Ein Szenario kann einen Anwendungsfall oder eine Sequenz von Anwendungsfällen beschreiben.

- Glossar: Das Glossar zu den Anforderungen des Projekts beschreibt die Wörter, mit denen die Kunden ihre Welt beschreiben. Diese Begriffe sollten auch im Benutzeroberflächenmodell und Anforderungsmodell verwendet werden. Ein Klassendiagramm kann dazu beitragen, die Beziehungen zwischen den meisten von diesen Begriffen zu verdeutlichen. Durch das Erstellen der Diagramme und des Glossars werden nicht nur Missverständnisse zwischen Benutzern und Entwicklern reduziert, sondern fast immer auch Missverständnisse zwischen unterschiedlichen Projektbeteiligten aufgeklärt.

- Geschäftsregeln: Viele Geschäftsregeln können als unveränderliche Einschränkungen der Zuordnungen und Attribute im Anforderungsklassenmodell und als Einschränkungen in Sequenzdiagrammen dargestellt werden.

- Allgemeiner Entwurf: Beschreibt die Hauptbestandteile und wie sie zusammenpassen. Komponenten-, Sequenz- und Schnittstellendiagramme sind wesentliche Teile eines allgemeinen Entwurfs.

- Entwurfsmuster: Beschreiben die gemeinsamen Entwurfsregeln für die verschiedenen Teile des Systems.

- Testspezifikationen: In Testskripts und den Entwürfen für Testcode können Aktivitäts- und Sequenzdiagramme zum Beschreiben der Sequenzen von Testschritten genutzt werden. Systemtests sollten im Anforderungsmodell dargestellt werden, damit sie leicht geändert werden können, wenn sich die Anforderungen ändern.

- Projektplan: Der Projektplan oder -rückstand legt fest, wann die einzelnen Funktionen bereitgestellt werden. Sie können jede Funktion definieren, indem Sie angeben, welche Anwendungsfälle und Geschäftsregeln von ihr implementiert oder erweitert werden. Sie können entweder direkt im Plan auf die Anwendungsfälle und Geschäftsregeln verweisen, oder Sie können in einem eigenen Dokument einen Satz von Funktionen definieren und im Plan die Funktionstitel verwenden.

## <a name="use-models-in-iteration-planning"></a>Verwenden von Modellen in der iterationsplanung

Obwohl sich alle Projekte hinsichtlich Umfang und Organisation unterscheiden, wird ein typisches Projekt als eine Reihe von Iterationen mit einer Dauer von zwei bis sechs Wochen geplant. Es ist wichtig, eine ausreichende Anzahl von Iterationen zu planen, um Feedback von frühen Iterationen zu ermöglichen, mit dem der Umfang und die Pläne für spätere Iterationen angepasst werden können.

Möglicherweise tragen die folgenden Empfehlungen dazu bei, die Vorteile der Modellierung in einem iterativen Projekt auszuschöpfen.

### <a name="sharpen-focus-as-each-iteration-approaches"></a>Erweitern Sie den Fokus jeder Iteration

Definieren Sie vor Beginn jeder Iteration mithilfe von Modellen, was am Ende der Iteration bereitgestellt werden muss.

- Modellieren Sie in frühen Iterationen nicht ausführlich alle Details. Erstellen Sie in der ersten Iteration ein Klassendiagramm für die Hauptelemente im Benutzerglossar, zeichnen Sie ein Diagramm der Hauptanwendungsfälle, und zeichnen Sie ein Diagramm der Hauptkomponenten. Beschreiben Sie nicht die Details dieser Elemente, da sich die Details später im Projekt ändern. Verwenden Sie die in diesem Modell definierten Begriffe, um eine Liste von Funktionen oder wichtigen User Stories zu erstellen. Weisen Sie Iterationen Funktionen zu, um die Arbeitsauslastung während des gesamten Projekts ungefähr gleichmäßig zu verteilen. Diese Zuweisungen werden später im Projekt geändert.

- Versuchen Sie, in einer frühen Iteration vereinfachte Versionen aller besonders wichtigen Anwendungsfälle zu implementieren. Erweitern Sie diese Anwendungsfälle in späteren Iterationen. Auf diese Weise verringern Sie das Risiko, einen Fehler in den Anforderungen oder der Architektur zu einem Zeitpunkt des Projekts zu erkennen, zu dem der Fehler nicht mehr behoben werden kann.

- Veranstalten Sie gegen Ende jeder Iteration einen Anforderungsworkshop, um die Details der Anforderungen oder User Stories zu definieren, die in der nächsten Iteration entwickelt werden. Laden Sie Benutzer und Projektbeteiligte, die Entscheidungen zu Prioritäten treffen können, sowie Entwickler und Systemtester zur Teilnahme ein. Planen Sie zum Definieren der Anforderungen für eine Iteration von 2 Wochen eine Workshopdauer von 3 Stunden ein.

- Der Workshop soll dazu führen, dass alle Projektbeteiligten Übereinstimmung über die bis zum Ende der nächsten Iteration zu erreichenden Ergebnisse erzielen. Verwenden Sie Modelle als eines der Instrumente zum Klarstellen der Anforderungen. Das Ergebnis des Workshops ist ein Iterationsrückstand. Dabei handelt es sich um eine Liste von Entwicklungsaufgaben in [!INCLUDE[esprfound](../code-quality/includes/esprfound_md.md)] und von Testsammlungen in [!INCLUDE[TCMext](../misc/includes/tcmext_md.md)].

- Besprechen Sie im Anforderungsworkshop den Entwurf nur insoweit, als Sie die Entwicklungsaufgaben schätzungsweise bestimmen müssen. Begrenzen Sie ansonsten die Besprechung auf Systemverhalten, das Benutzer direkt wahrnehmen können. Halten Sie das Anforderungsmodell vom Architekturmodell getrennt.

- Projektbeteiligte ohne technischen Hintergrund verstehen normalerweise UML-Diagramme ohne Probleme, wenn sie von Ihnen Erläuterungen erhalten.

### <a name="link-model-to-work-items"></a>Verknüpfen Sie das Modell mit Arbeitsaufgaben

Bestimmen Sie nach dem Anforderungsworkshop die Details des Anforderungsmodells, und verknüpfen Sie das Modell mit Entwicklungsaufgaben. Sie können zu diesem Zweck Arbeitsaufgaben in [!INCLUDE[esprfound](../code-quality/includes/esprfound_md.md)] mit Elementen im Modell verknüpfen.

Sie können jedes Element mit Arbeitsaufgaben verknüpfen, die zweckmäßigsten Elemente lauten jedoch wie folgt:

- Kommentare, die Geschäftsregeln oder Servicequalitätsanforderungen beschreiben. Weitere Informationen finden Sie unter [Modellieren von benutzeranforderungen](../modeling/model-user-requirements.md).

### <a name="link-model-to-tests"></a>Verknüpfen Sie das Modell für tests

Verwenden Sie das Anforderungsmodell als Orientierungshilfe für den Entwurf der Akzeptanztests. Erstellen Sie diese Tests während der Entwicklungsarbeit.

Weitere Informationen zu diesem Verfahren finden Sie unter [Entwickeln von Tests aus einem Modell](../modeling/develop-tests-from-a-model.md).

### <a name="estimate-remaining-work"></a>Schätzen Sie die verbleibende Arbeit

Mithilfe eines Anforderungsmodells lässt sich der Gesamtumfang des Projekts im Verhältnis zum Umfang der einzelnen Iterationen schätzen. Durch Bestimmen von Anzahl und Komplexität der Anwendungsfälle und Klassen können Sie die erforderliche Entwicklungsarbeit genauer schätzen. Wenn Sie die ersten Iterationen abgeschlossen haben, können Sie durch den Vergleich der erfüllten Anforderungen mit den noch zu erfüllenden Anforderungen den restlichen Aufwand und Umfang des Projekts näherungsweise bestimmen.

Überprüfen Sie gegen Ende jeder Iteration die Zuweisung von Anforderungen zu zukünftigen Iterationen. Es kann sinnvoll sein, den Zustand der Software am Ende jeder Iteration als Subsystem in einem Anwendungsfalldiagramm darzustellen. In den Besprechungen können Sie Anwendungsfälle und Anwendungsfallerweiterungen zwischen den Subsystemen verschieben.

## <a name="levels-of-abstraction"></a>Abstraktionsebenen

Modelle abstrahieren die Software in unterschiedlichem Ausmaß. Die konkretesten Modelle stellen direkt den Programmcode dar, und die abstraktesten Modelle stellen Geschäftskonzepte dar, die nicht in jedem Fall im Code dargestellt werden.

Ein Modell kann über mehrere Arten von Diagrammen dargestellt werden. Weitere Informationen zu Modellen und Diagrammen, finden Sie unter [Erstellen von Modellen für Ihre app](../modeling/create-models-for-your-app.md).

Zum Beschreiben des Entwurfs auf unterschiedlichen Abstraktionsebenen eignen sich unterschiedliche Arten von Diagrammen. Viele der Diagrammtypen sind für mehrere Ebenen sinnvoll. In der folgenden Tabelle wird gezeigt, wie jeder Diagrammtyp verwendet werden kann.

|Entwurfsebene|Diagrammtypen|
|------------------|-------------------|
|Geschäftsprozess<br /><br /> Wenn Sie den Kontext kennen, in dem das System verwendet wird, erleichtert dies das Verständnis der Anforderungen der Benutzer an das System.|– Konzeptionelle Klassendiagramme beschreiben die innerhalb des Geschäftsprozesses verwendeten Geschäftskonzepte.|
|Benutzeranforderungen<br /><br /> Die Definition der Anforderungen der Benutzer an das System.|– Die Geschäftsregeln und servicequalitätsanforderungen können in separaten Dokumenten beschrieben werden.|
|Allgemeiner Entwurf<br /><br /> Die Gesamtstruktur des Systems: die Hauptkomponenten und wie sie verknüpft sind.|-Abhängigkeitsdiagrammen wird beschrieben, wie das System in voneinander abhängige Teile gegliedert ist. Sie können überprüfen, dass Programmcode anhand von Abhängigkeitsdiagrammen, um sicherzustellen, dass er der Architektur entspricht.|
|Codeanalyse<br /><br /> Diagramme können aus dem Code generiert werden.|-Abhängigkeitsdiagramme zeigen die Abhängigkeiten zwischen Klassen an. Aktualisierten Code kann gegen ein Abhängigkeitsdiagramm überprüft werden.<br />-Class-Diagramme zeigen die Klassen im Code.|

## <a name="external-resources"></a>Externe Ressourcen

|**Kategorie**|**Links**|
|------------------|---------------|
|**Videos**|![Link zum Video](../data-tools/media/playvideo.gif) [MSDN Anleitungsvideos: Erstellen und Verwenden von UML-Modellen und Diagrammen (Visual Studio 2010 Ultimate)](http://go.microsoft.com/fwlink/?LinkId=214460)<br /><br /> ![Link zum Video](../data-tools/media/playvideo.gif) [Channel 9: UML mit Visual Studio 2010](http://go.microsoft.com/fwlink/?LinkID=201106)<br /><br /> ![Link zum Video](../data-tools/media/playvideo.gif) [wie Reihe von MSDN: UML-Tools und Erweiterbarkeit (Visual Studio 2010 Ultimate)](http://go.microsoft.com/fwlink/?LinkID=214467)|
|**Foren**|- [Visual Studio-Visualisierungs- & Modellierungstools](http://go.microsoft.com/fwlink/?LinkId=184720)<br />- [Visual Studio Visualization & Modeling SDK (DSL-Tools)](http://go.microsoft.com/fwlink/?LinkId=184721)|
|**Blogs**|[Microsoft DevOps](https://blogs.msdn.microsoft.com/devops/)|
|**Technische Artikel und Journale**|[MSDN Architecture Center](http://go.microsoft.com/fwlink/?LinkId=201343)<br /><br /> [Visual Studio Architecture Tooling Guidance](../modeling/visual-studio-architecture-tooling-guidance.md)|

## <a name="see-also"></a>Siehe auch

- [Verwenden von Modellen in Agile-Entwicklung](http://msdn.microsoft.com/592ac27c-3d3e-454a-9c38-b76658ed137f)
- [Erstellen von Modellen für Ihre App](../modeling/create-models-for-your-app.md)
- [Modellieren von Benutzeranforderungen](../modeling/model-user-requirements.md)
- [Modellieren der Architektur Ihrer App](../modeling/model-your-app-s-architecture.md)
- [Entwickeln von Tests aus einem Modell](../modeling/develop-tests-from-a-model.md)
- [Strukturieren der Modellierungslösung](../modeling/structure-your-modeling-solution.md)

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]
