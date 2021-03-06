---
title: Verwenden von PyLint zum Linting von Python-Code
description: Verwenden von PyLint in Visual Studio zum Überprüfen von Problemen in Python-Code.
ms.date: 06/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: fa037a9e674e6086fd3d558d621f9a7d7be616aa
ms.sourcegitcommit: 0cf1e63b6e0e6a0130668278489b21a6e5038084
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39468740"
---
# <a name="use-pylint-to-check-python-code"></a>Verwenden von PyLint zur Überprüfung von Python-Code

[PyLint](https://www.pylint.org/), ein häufig verwendetes Tool, das Python-Code auf Fehler überprüft und gute Python-Codemuster unterstützt, ist in Visual Studio für Python-Projekte integriert.

## <a name="run-pylint"></a>Ausführen von PyLint

Klicken Sie einfach im **Projektmappen-Explorer** mit der rechten Maustaste auf ein Python-Projekt, und wählen Sie **Python** > **PyLint ausführen** aus:

![PyLint-Befehl im Kontextmenü für Python-Projekte](media/code-pylint-command.png)

Wenn Sie diesen Befehl verwenden, werden Sie dazu aufgefordert, PyLint in Ihrer aktiven Umgebung zu installieren, wenn es noch nicht vorhanden ist.

PyLint-Warnungen und -Fehler werden im **Fehlerlistenfenster** angezeigt:

![PyLint-Fehlerliste](media/code-pylint-error-list.png)

Durch Doppelklicken auf einen Fehler gelangen Sie direkt zu dem Quellcode, der das Problem verursacht.

> [!Tip]
> Eine detaillierte Liste aller PyLint-Ausgabemeldungen finden Sie in der [PyLint-Funktionsreferenz](https://pylint.readthedocs.io/en/latest/technical_reference/features.html).

## <a name="set-pylint-command-line-options"></a>Festlegen von PyLint-Befehlszeilenoptionen

Der Abschnitt mit [Befehlszeilenoptionen](https://pylint.readthedocs.io/en/latest/user_guide/run.html#command-line-options) in der PyLint-Dokumentation beschreibt, wie das Verhalten von PyLint über eine *.pylintrc*-Konfigurationsdatei gesteuert wird. Eine solche Datei kann im Stammverzeichnis eines Python-Projekts in Visual Studio oder in einem anderen Verzeichnis platziert werden, je nachdem, in welchem Umfang die Einstellungen angewendet werden sollen (Details finden Sie in den [Befehlszeilenoptionen](https://pylint.readthedocs.io/en/latest/user_guide/run.html#command-line-options)).

Um z.B. die in der obigen Abbildung gezeigten „missing-docstring“-Warnungen mit einer *.pylintrc*-Datei in einem Projekt zu unterdrücken, gehen Sie folgendermaßen vor:

1. Navigieren Sie in der Befehlszeile zum Stammverzeichnis Ihres Projekts (dort finden Sie Ihre *.pyproj*-Datei), und führen Sie den folgenden Befehl aus, um eine kommentierte Konfigurationsdatei zu generieren:

   ```command
   pylint --generate-rcfile > .pylintrc
   ```

1. Wählen Sie im Visual Studio-Projektmappen-Explorer mit der rechten Maustaste Ihr Projekt, wählen Sie **Hinzufügen** > **Vorhandenes Element** aus, navigieren Sie zur neuen *.pylintrc*-Datei, wählen Sie sie aus, und wählen Sie **Hinzufügen** aus.

1. Öffnen Sie die Datei zum Bearbeiten, die eine Reihe von Einstellungen enthält, mit denen Sie arbeiten können. Um eine Warnung zu deaktivieren, suchen Sie den Abschnitt `[MESSAGES CONTROL]` und darin die Einstellung `disable`. Es gibt eine lange Zeichenfolge mit spezifischen Meldungen, an die Sie beliebige Warnungen anfügen können. Im vorliegenden Beispiel wird `,missing-docstring` angefügt (einschließlich des trennenden Kommas).

1. Speichern Sie die *.pylintrc*-Datei, und führen Sie PyLint erneut aus. Sie werden feststellen, dass die Warnungen jetzt unterdrückt werden.

> [!Tip]
> Um eine *.pylintrc*-Datei aus einer Netzwerkfreigabe zu verwenden, erstellen Sie auf der Netzwerkfreigabe eine Umgebungsvariable namens `PYLINTRC` mit dem Wert des Dateinamens und verwenden dazu einen UNC-Pfad oder einen zugeordneten Laufwerkbuchstaben. Beispielsweise `PYLINTRC=\\myshare\python\.pylintrc`.
