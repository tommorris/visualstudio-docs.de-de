---
title: Modellieren Ihrer app&#39;s-Architektur
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- UML, modeling architecture
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 0d75627eac18fa20edad222d168c858b073cecae
ms.sourcegitcommit: 5b767247b3d819a99deb0dbce729a0562b9654ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2018
ms.locfileid: "39178903"
---
# <a name="model-your-app39s-architecture"></a>Modellieren Ihrer app&#39;s-Architektur
Um sicherzustellen, dass das Softwaresystem oder die Anwendung Ihrer Benutzer erfüllen müssen, können Sie Modelle als Teil der Beschreibung von Gesamtstruktur und das Verhalten des Softwaresystems oder der Anwendung in Visual Studio erstellen. Mit Modellen können Sie auch Muster beschreiben, die im gesamten Entwurf verwendet werden. Mithilfe dieser Modelle können Sie die vorhandene Architektur verstehen, Änderungen erörtern und Ihre Absichten eindeutig vermitteln.

 Welche Versionen von Visual Studio dieses Feature unterstützen, erfahren Sie unter [Versionsunterstützung für Architektur- und Modellierungstools](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).

 Ein Modell soll die Mehrdeutigkeiten in Beschreibungen in natürlicher Sprache reduzieren und Ihnen und Ihren Kollegen helfen, den Entwurf visuell darzustellen sowie alternative Entwürfe zu erörtern. Ein Modell sollte zusammen mit anderen Dokumenten oder Diskussionen verwendet werden. Ein Modell an sich stellt keine vollständige Spezifikation der Architektur dar.

> [!NOTE]
>  In diesem gesamten Thema wird als „System“ die Software bezeichnet, die Sie entwickeln. Dabei kann es sich um eine umfangreiche Sammlung vieler Software- und Hardwarekomponenten, eine einzelne Anwendung oder einen Teil einer Anwendung handeln.

 Die Architektur eines Systems kann in zwei Bereiche unterteilt werden:

-   [Allgemeiner Entwurf](#Structure). Dieser Begriff beschreibt die Hauptkomponenten und ihre Interaktion zum Erfüllen der einzelnen Anforderungen. Wenn es sich um ein umfangreiches System handelt, kann jede Komponente über einen eigenen allgemeinen Entwurf verfügen, der darstellt, wie er aus kleineren Komponenten zusammengesetzt ist.

-   [Entwurfsmuster](#Patterns) und Konventionen, die in allen Entwürfen der Komponenten verwendet. Ein Muster beschreibt eine bestimmte Methode zum Erreichen eines Programmierziels. Wenn das Team während des gesamten Entwurfs die gleichen Entwurfsmuster verwendet, lässt sich der Aufwand zum Durchführen von Änderungen und Entwickeln neuer Software verringern.

##  <a name="Structure"></a> Allgemeiner Entwurf
 Ein allgemeiner Entwurf beschreibt die Hauptkomponenten des Systems und ihre Interaktion zum Erreichen der Ziele des Entwurfs. Das Entwickeln des allgemeinen Entwurfs umfasst die Aktivitäten in der folgenden Liste, wenn auch nicht unbedingt in einer bestimmten Reihenfolge.

 Wenn Sie vorhandenen Code aktualisieren, sollten Sie zunächst die Hauptkomponenten beschreiben. Stellen Sie sicher, dass Sie ggf. vorhandene Änderungen der Benutzeranforderungen verstehen, und fügen Sie dann Interaktionen zwischen den Komponenten hinzu, oder ändern Sie diese. Wenn Sie ein neues System entwickeln, ermitteln Sie zunächst die Hauptmerkmale der Benutzeranforderungen. Sie können dann Sequenzen von Interaktionen für die Hauptanwendungsfälle untersuchen und anschließend die Sequenzen in einem Komponentenentwurf konsolidieren.

 In jedem Fall ist es hilfreich, die verschiedenen Aktivitäten parallel zu entwickeln und Code und Tests bereits in einer frühen Phase zu entwerfen. Versuchen Sie nicht, einen dieser Aspekte abzuschließen, bevor Sie mit einem anderen Aspekt beginnen. In der Regel ändern sich sowohl die Anforderungen als auch Ihre Auffassung von dem besten Verfahren zum Entwerfen des Systems, während Sie den Code schreiben und testen. Daher sollten Sie zunächst die Hauptmerkmale der Anforderungen und des Entwurfs ermitteln und codieren. Behandeln Sie die Details in späteren Iterationen des Projekts.

-   [Grundlegendes zu den Anforderungen](#Requirements). Der Ausgangspunkt jedes Entwurfs sind fundierte Kenntnisse der Benutzeranforderungen.

-   [Architektonische Muster](#BigDecisions). Die Kerntechnologien und Architekturelemente des Systems, die Sie ausgewählt haben.

-   Datenmodell der Komponenten und Schnittstellen. Sie können Klassendiagramme zeichnen, um die Informationen zu beschreiben, die zwischen Komponenten übergeben und in den Komponenten gespeichert werden.

##  <a name="Requirements"></a> Grundlegendes zu den Anforderungen
 Der allgemeine Entwurf für eine vollständige Anwendung wird am effektivsten zusammen mit einem Anforderungsmodell oder einer anderen Beschreibung der Benutzeranforderungen entwickelt. Weitere Informationen über Anforderungsmodelle finden Sie unter [Modellieren von benutzeranforderungen](../modeling/model-user-requirements.md).

 Wenn das System, das Sie entwickeln, eine Komponente in einem größeren System ist, können Ihre Anforderungen vollständig oder teilweise in programmgesteuerte Schnittstellen aufgenommen werden.

 Das Anforderungsmodell stellt die folgenden wesentlichen Informationen bereit:

-   Bereitgestellte Schnittstellen. Eine bereitgestellte Schnittstelle führt die Dienste oder Vorgänge auf, die das System oder die Komponente für die Benutzer bereitstellen muss, unabhängig davon, ob es sich um menschliche Benutzer oder andere Softwarekomponenten handelt.

-   Erforderliche Schnittstellen. Eine erforderliche Schnittstelle führt die Dienste oder Vorgänge auf, die das System oder die Komponente verwenden kann. In einigen Fällen können Sie alle diese Dienste als Teil des eigenen Systems entwerfen. In anderen Fällen, insbesondere wenn Sie eine Komponente entwerfen, die mit anderen Komponenten in vielen Konfigurationen kombiniert werden kann, wird die erforderliche Schnittstelle auf Grundlage externer Aspekte festgelegt.

-   Servicequalitätsanforderungen. Leistung, Sicherheit, Stabilität und andere Ziele und Einschränkungen, die das System erfüllen muss.

 Das Anforderungsmodell wird aus der Perspektive der Benutzer des Systems geschrieben, bei denen es sich um Personen oder andere Softwarekomponenten handeln kann. Die internen Funktionen des Systems sind ihnen nicht bekannt. Im Gegensatz dazu soll ein Architekturmodell die internen Funktionen beschreiben und darstellen, wie sie die Anforderungen der Benutzer erfüllen.

 Die Anforderungen und Architekturmodelle sollten getrennt bleiben, um das Erörtern der Anforderungen mit den Benutzern zu erleichtern. Dies erleichtert es außerdem, den Entwurf umzugestalten und alternative Architekturen zu erwägen, während die Anforderungen unverändert beibehalten werden.

 Der Umfang an Informationen, die Sie in ein Anforderungsmodell oder ein Architekturmodell aufnehmen sollten, hängt vom Umfang des Projekts sowie der Größe des Teams und der räumlichen Verteilung seiner Mitglieder ab. Ein kleines Team in einem kurzen Projekt braucht eventuell lediglich ein Klassendiagramm der Geschäftskonzepte und einige Entwurfsmuster zu skizzieren; ein großes Projekt, das über mehr als einen Bereich ausgeliefert wurde, wird deutlich mehr Details erfordern.

##  <a name="BigDecisions"></a> Architektonische Muster
 Sie müssen zu einem frühen Zeitpunkt der Entwicklung Optionen für die wichtigsten Technologien und Elemente auswählen, von denen der Entwurf abhängt. Diese Optionen müssen in den folgenden Bereichen ausgewählt werden:

-   Basistechnologie, z. B. die Auswahl zwischen einer Datenbank und ein Dateisystem und die Wahl zwischen einer netzwerkanwendung oder eines Webclients und so weiter.

-   Frameworkoptionen, z. B. Auswahl von Windows Workflow Foundation oder ADO.NET Entity Framework.

-   Optionen für Integrationsmethoden, z. B. Auswahl eines Enterprise Service Bus oder eines Punkt-zu-Punkt-Channels.

 Diese Optionen werden häufig von Servicequalitätsanforderungen bestimmt, z. B. Größe und Flexibilität, und die Auswahl kann getroffen werden, bevor die Anforderungsdetails bekannt sind. In einem umfangreichen System besteht eine enge Wechselbeziehung zwischen der Konfiguration von Hardware und Software.

 Die von Ihnen ausgewählten Optionen wirken sich darauf aus, wie Sie das Architekturmodell verwenden und interpretieren. Beispielsweise können in einem System mit einer Datenbank Zuordnungen in einem Klassendiagramm Beziehungen oder Fremdschlüssel in der Datenbank darstellen, während in einem auf XML-Dateien basierenden System Zuordnungen Querverweise angeben können, die XPath verwenden. In einem verteilten System können Meldungen in einem Sequenzdiagramm Meldungen in einer Verbindung darstellen, und in einer unabhängigen Anwendung können sie Funktionsaufrufe darstellen.

##  <a name="Patterns"></a> Entwurfsmuster
 Ein Entwurfsmuster skizziert den Entwurf eines bestimmten Aspekts der Software, insbesondere eines Aspekts, der in verschiedenen Teilen des Systems vorhanden ist. Wenn Sie im gesamten Projekt eine einheitliche Vorgehensweise anwenden, können Sie den Aufwand für den Entwurf verringern, die Konsistenz der Benutzeroberfläche sicherstellen und den Aufwand für das Verstehen und Ändern des Codes reduzieren.

 Einige allgemeine Entwurfsmuster, z. B. das Beobachtermuster, sind bekannt und in vielfältigen Szenarien anwendbar. Darüber hinaus gibt es Muster, die nur auf das spezifische Projekt anwendbar sind. Z. B. in einem Vertriebssystem Web stehen mehrere Vorgänge im Code, in denen Änderungen an einer kundenbestellung vorgenommen werden. Um sicherzustellen dass der Zustand der Bestellung in jeder Phase korrekt angezeigt wird, müssen all diese Vorgänge einem bestimmten Protokoll zum Aktualisieren der Datenbank entsprechen.

 Das Erstellen der Softwarearchitektur umfasst das Bestimmen der Muster, die im gesamten Entwurf angewendet werden sollen. Dies ist normalerweise eine permanente Aufgabe, da während des Projekts neue Muster und Verbesserungen vorhandener Muster erkannt werden. Es ist hilfreich, den Entwicklungsplan so zu organisieren, dass Sie jedes der Hauptentwurfsmuster in einer frühen Phase ausführen.

 Die meisten Entwurfsmuster können teilweise in Frameworkcode dargestellt werden. Ein Teil des Musters kann auf die Anforderung reduziert werden, dass der Entwickler bestimmte Klassen oder Komponenten verwendet, z. B. eine Datenbankzugriffsebene, die sicherstellt, dass die Datenbank ordnungsgemäß behandelt wird.

 Ein Entwurfsmuster wird in einem Dokument beschrieben, und es enthält in der Regel die folgenden Teile:

-   Name.

-   Eine Beschreibung des Kontexts, in dem es anwendbar ist. Aufgrund welcher Kriterien sollte der Entwickler das Anwenden des Musters in Betracht ziehen?

-   Eine kurze Erläuterung des Problems, das durch das Muster gelöst wird.

-   Ein Modell der Hauptbestandteile und ihrer Beziehungen. Dabei kann es sich um Klassen oder Komponenten und Schnittstellen handeln, mit Zuordnungen und Abhängigkeiten zwischen ihnen. Die Elemente gehören normalerweise zu einer von zwei Kategorien:

-   Benennungskonventionen

-   Eine Beschreibung, wie das Muster das Problem löst.

-   Eine Beschreibung von Varianten, die Entwickler möglicherweise anwenden können.

## <a name="see-also"></a>Siehe auch

- [Visualisieren von Code](../modeling/visualize-code.md)
- [Modellieren von Benutzeranforderungen](../modeling/model-user-requirements.md)
- [Entwickeln von Tests aus einem Modell](../modeling/develop-tests-from-a-model.md)
- [Verwenden von Modellen im Entwicklungsprozess](../modeling/use-models-in-your-development-process.md)