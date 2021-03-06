---
title: Suchen von Verweisen im Code
ms.date: 09/26/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- code editor, find all references
- find all references
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8ac09eace078ef60f36bd57e9a2c4a1e5f1c510c
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
ms.locfileid: "31942320"
---
# <a name="find-references-in-your-code"></a>Suchen von Verweisen im Code

Mithilfe des Befehls **Alle Verweise suchen** können Sie in Ihrer gesamten Codebasis die Stellen finden, an denen auf bestimmte Codeelemente verwiesen wird. Den Befehl **Alle Verweise suchen** finden Sie im Kontextmenü (Rechtsklick) des Elements, für das Sie Verweise suchen möchten. Wenn Sie eine Tastatur verwenden, können Sie einfach **UMSCHALT+F12** drücken.

Die Ergebnisse werden in einem Toolfenster mit der Bezeichnung **<element>-Verweise** angezeigt, wobei *element* dem Namen des gesuchten Elements entspricht. Mit einer Symbolleiste im **Verweisfenster** können Sie Folgendes tun:
- Den Suchbereich über ein Dropdown-Listenfeld ändern. Sie können auswählen, nur in geänderten Dokumenten bis hin zur gesamten Projektmappe zu suchen.
- Das ausgewählte Verweiselement durch Auswählen der Schaltfläche **Kopieren** kopieren.
- Schaltflächen auswählen, um zum nächsten oder vorherigen Element in der Liste zu wechseln. Drücken Sie dazu alternativ die Tasten **F8** und **UMSCHALT+F8**.
- Alle Filter auf den zurückgegebenen Ergebnissen durch Auswählen der Schaltflächen **Alle Filter löschen** entfernen.
- Ändern, wie zurückgegebene Elemente gruppiert werden, indem Sie eine Einstellung im Dropdown-Listenfeld **Gruppieren nach:** auswählen.
- Das Fenster der aktuellen Suchergebnisse beibehalten, indem Sie auf die Schaltfläche **Ergebnisse beibehalten** drücken. Wenn Sie diese Schaltfläche auswählen, verbleiben die aktuellen Suchergebnisse in diesem Fenster und neue Suchergebnisse erscheinen in einem neuen Toolfenster.
- Zeichenfolgen innerhalb der Suchergebnisse suchen, indem Sie Text in das Feld **Suche: Alle Verweise suchen** eingeben.

Sie können auch mit dem Mauszeiger auf ein Suchergebnis zeigen, um eine Vorschau des Verweises einzublenden.

![Toolfenster „Alle Verweise suchen“](../ide/media/vside_findallreferences.png)

## <a name="navigate-to-references"></a>„Navigieren zu“-Verweise
Mithilfe der folgenden Methoden können Sie zu den **Verweisen** im entsprechenden Fenster wechseln:

- Drücken Sie **F8**, um zum nächsten Verweis zu springen, oder **UMSCHALT+F8**, um zum vorherigen Verweis zu wechseln.
- Drücken Sie auf einem Verweis die **EINGABETASTE**, oder führen Sie einen Doppelklick aus, um zu der entsprechenden Stelle im Code zu wechseln.
- Wählen Sie im Kontextmenü eines Verweises den Befehl **Gehe zu vorheriger Position** oder **Gehe zu nächster Position** aus.
- Drücken Sie die **NACH-OBEN-TASTE** und die **NACH-UNTEN-TASTE** (falls diese im Dialogfeld **Optionen** aktiviert sind). Klicken Sie zum Aktivieren dieser Funktionalität im Menü auf **Extras** > **Optionen** > **Umgebung** > **Registerkarten und Fenster** > **Vorschauregisterkarte**, und aktivieren Sie anschließend die Kontrollkästchen **Das Öffnen neuer Dateien in der Vorschauregisterkarte zulassen** und **Vorschau der ausgewählten Dateien in „Ergebnisse suchen“ anzeigen**.

## <a name="change-reference-groupings"></a>Änderung von Verweisgruppierungen
Standardmäßig werden Verweise vom Projekt dann per Definition gruppiert. Sie können diese Gruppierungsreihenfolge jedoch ändern, indem Sie im Dropdown-Listenfeld auf der Symbolleiste die Einstellung **Gruppieren nach:** ändern. Sie können sie beispielsweise von der Standardeinstellung **Projekt, dann Definition** in **Definition, dann Projekt** ändern.

**Definition** und **Projekt** sind die beiden verwendeten Standardgruppierungen, aber Sie können andere hinzufügen, indem Sie den Befehl **Gruppierung** im Kontextmenü des ausgewählten Elements auswählen. Das Hinzufügen weiterer Gruppen kann hilfreich sein, wenn Ihre Projektmappe viele Dateien und Pfade enthält.

## <a name="see-also"></a>Siehe auch

- [Navigieren im Code](../ide/navigating-code.md)