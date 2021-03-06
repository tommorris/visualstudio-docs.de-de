---
title: 'Schritt 8: Anpassen des Quiz | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dc8edb13-1b23-47d7-b859-8c6f7888c1a9
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 72e630a3d065e196d33919045316fad27c912750
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47523381"
---
# <a name="step-8-customize-the-quiz"></a>Schritt 8: Anpassen des Quiz
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [Schritt 8: Anpassen des Quiz](https://docs.microsoft.com/visualstudio/ide/step-8-customize-the-quiz).  
  
Im letzten Teil des Lernprogramms untersuchen Sie mehrere Möglichkeiten, das Quiz anzupassen. Damit erweitern Sie Ihre bereits erworbenen Kenntnisse. Sie können z. B. überlegen, wie das Programm zufällige Divisionsaufgaben erstellt, für die die Antwort nie eine Bruchzahl ist. Um den Lerneffekt zu erhöhen, können Sie für das `timeLabel`-Steuerelement eine andere Farbe festlegen und dem Quizteilnehmer einen Hinweis geben.  
  
### <a name="to-customize-the-quiz"></a>So passen Sie das Quiz an  
  
-   Ändern Sie das Steuerelement **timeLabel** in Rot, wenn nur noch fünf Sekunden zur Durchführung des Quiz verbleiben. Legen Sie dazu die Eigenschaft **BackColor** (`timeLabel.BackColor = Color.Red;`) für das Steuerelement fest. Setzen Sie die Farbe zurück, wenn das Quiz vorbei ist.  
  
-   Geben Sie dem Quizteilnehmer einen Hinweis, indem Sie einen Sound wiedergeben, wenn in ein NumericUpDown-Steuerelement die richtige Antwort eingegeben wird. (Sie müssen für jedes Steuerelement einen Ereignishandler für das `ValueChanged()`-Ereignis schreiben, das ausgelöst wird, wenn der Quizteilnehmer den Wert des Steuerelements ändert.)  
  
### <a name="to-continue-or-review"></a>So fahren Sie fort oder überprüfen die Angaben  
  
-   Informationen zum Herunterladen einer vollständigen Version des Quiz finden Sie unter [Tutorialbeispiel des vollständigen Mathequiz](http://code.msdn.microsoft.com/Complete-Math-Quiz-8581813c).  
  
-   Um zum nächsten Tutorial zu wechseln, klicken Sie auf [Tutorial 3: Erstellen eines Vergleichsspiels](../ide/tutorial-3-create-a-matching-game.md).  
  
-   Um zum vorhergehenden Schritt des Tutorials zurückzukehren, klicken Sie auf [Schritt 7: Hinzufügen von Multiplikations- und Divisionsaufgaben](../ide/step-7-add-multiplication-and-division-problems.md).



