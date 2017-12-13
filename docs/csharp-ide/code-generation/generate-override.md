---
title: "Generieren Sie eine Außerkraftsetzung - Generierung von Code (c#) | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b3c8cfc4-7c1f-4606-970e-3f7651604bab
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: f7193722e7ec1bee7c63e2495ed2d07155cc663b
ms.sourcegitcommit: 5f5587a1bcf4aae995c80d54a67b4b461f8695f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/29/2017
---
# <a name="generate-an-override-in-c"></a>Generieren Sie eine Außerkraftsetzung in c# #

**Was:** können Sie sofort den Code für jede Methode überschrieben werden kann von einer Basisklasse generieren.

**Wann:** eine Methode der Basisklasse überschreiben und die Signatur automatisch generiert werden sollen.

**Grund:** Sie konnte die Signatur der Methode selbst schreiben, aber diese Funktion die Signatur automatisch generiert.

**Vorgehensweise:**

1. Typ der **überschreiben** -Schlüsselwort, gefolgt von einem Leerzeichen, in dem Sie eine Signatur außer Kraft gesetzte Methode einfügen möchten und eine IntelliSense-Dropdownliste wird angezeigt.

   ![Überschreiben von IntelliSense](media/override_intellisense.png)

1. Wählen Sie die Methode, die Sie von der Basisklasse zu überschreiben, indem Sie darauf klicken, mit der Maus, oder navigieren, mit der Tastatur drücken möchten **EINGABETASTE**.

   >[!TIP]
   >* Verwenden Sie das Symbol "Eigenschaft" ![Eigenschaftssymbol](media/override_property.png) zum Anzeigen oder Ausblenden von Eigenschaften in der Liste.
   >* Verwenden Sie das Symbol "Methode" ![Methodensymbol](media/override_method.png) zum Anzeigen oder Ausblenden von Methoden in der Liste.

1. Die ausgewählte Methode oder Eigenschaft wird auf die Klasse als eine Außerkraftsetzung, die implementiert werden können hinzugefügt werden.

   ![Überschreiben Sie Ergebnis](media/override_result.png)

## <a name="see-also"></a>Siehe auch

[Codegenerierung (C#)](../code-generation-csharp.md)