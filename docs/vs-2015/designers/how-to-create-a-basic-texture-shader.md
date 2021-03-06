---
title: 'Vorgehensweise: Erstellen eines Basistextur-Shaders | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5af113fb-6415-4be0-8b23-10fddb10e80a
caps.latest.revision: 25
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 421b02692af0235582845a5884c228933f0ca7c2
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47523920"
---
# <a name="how-to-create-a-basic-texture-shader"></a>Gewusst wie: Erstellen eines Basistextur-Shaders
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [Vorgehensweise: Erstellen eines Basistextur-Shaders](https://docs.microsoft.com/visualstudio/designers/how-to-create-a-basic-texture-shader).  
  
In diesem Dokument wird gezeigt, wie der Shader-Designer und die Directed Graph Shader Language (DGSL) zum Erstellen eines Ein-Textur-Shaders verwendet wird. Dieser Shader legt die endgültige Farbe direkt auf die RGB- und Alphawerte fest, die von der Textur bezogen werden.  
  
 In diesem Dokument werden die folgenden Aktivitäten veranschaulicht:  
  
-   Entfernen von Knoten aus einen Shader-Diagramm  
  
-   Hinzufügen von Knoten in ein Diagramm  
  
-   Festlegen der Shader-Parameter  
  
-   Einstellen des Parameters „Sichtbarkeit“  
  
-   Verbinden der Knoten  
  
## <a name="creating-a-basic-texture-shader"></a>So erstellen Sie einen Basistexturshader  
 Sie können einen grundlegenden, Ein-Textur-Shader implementieren, indem die Farb- und Alphawerte direkt in die endgültige Farbe geschrieben werden.  
  
 Bevor Sie beginnen, stellen Sie sicher, dass das Fenster **Eigenschaften** und die **Toolbox** angezeigt werden.  
  
#### <a name="to-create-a-basic-texture-shader"></a>So erstellen Sie einen Basistexturshader  
  
1.  Erstellen Sie einen DGSL-Shader, mit dem Sie arbeiten können. Wie Sie dem Projekt einen DGSL-Shader hinzufügen, erfahren Sie im Abschnitt „Erste Schritte“ unter [Shader-Designer](../designers/shader-designer.md)  
  
2.  Löschen Sie den Knoten **Punktfarbe**. Wählen Sie im Modus **Auswählen** den Knoten **Farbpunkt** aus, und klicken Sie anschließend in der Menüleiste auf **Bearbeiten** > **Löschen**. Dadurch wird Platz für den Knoten geschaffen, der im nächsten Schritt hinzugefügt wird.  
  
3.  Fügen Sie einen Knoten **Textursample** in das Diagramm ein. Klicken Sie in der **Toolbox** unter **Textur** auf **Textursample**, und verschieben Sie es auf die Entwurfsoberfläche.  
  
4.  Fügen Sie einen Knoten **Texturkoordinate** in das Diagramm ein. Klicken Sie in der **Toolbox** unter **Textur** auf **Texturkoordinate**, und verschieben Sie es auf die Entwurfsoberfläche.  
  
5.  Wählen Sie eine Textur zum Anwenden aus. Klicken sie im Modus **Auswählen** auf den Knoten **Textursample**, und geben Sie im Fenster **Eigenschaften** die zu verwendende Textur an, indem Sie die Eigenschaft **Dateiname** verwenden.  
  
6.  Machen Sie die Textur öffentlich verfügbar. Klicken Sie auf den Knoten **Textursample**, und stellen Sie im Fenster **Eigenschaften** die Eigenschaft **Zugriff** auf **Öffentlich**. Sie können nun die Textur von einem anderen Tool wie dem **Modell-Editor** festlegen.  
  
7.  Verbinden Sie die Texturkoordinaten mit dem Textursample. Verschieben Sie im Modus **Auswählen** das Terminal **Ausgabe** des Knotens **Texturkoordinate** auf das Terminal **UV** des Knotens **Textursample**. Diese Verbindung prüft die Textur an den angegebenen Koordinaten.  
  
8.  Verbinden Sie das Textursample mit der endgültigen Farbe. Verschieben Sie das Terminal **RGB** des Knotens **Textursample** auf das Terminal **RGB** des Knotens **Endgültige Farbe**. Verschieben Sie anschließend das Terminal **Alpha** des Knotens **Textursample** auf das Terminal **Alpha** des Knotens **Endgültige Farbe**.  
  
 In der folgenden Abbildung wird das fertige Shaderdiagramm sowie eine Vorschau eines Würfels gezeigt, auf dem der Shader angewandt wurde.  
  
> [!NOTE]
>  In dieser Abbildung wird eine Ebene als Vorschauform verwendet, und eine Textur wurde angegeben, um den Effekt des Shaders besser zu veranschaulichen.  
  
 ![Shader-Diagramm und eine Vorschau seiner Effekte](../designers/media/digit-texture-effect.png "Digit-Texture-Graph")  
  
 Bestimmte Formen sorgen vielleicht für bessere Vorschauen für einige Shader. Weitere Informationen zur Verwendung der Vorschau von Shadern im Shader-Designer finden Sie unter [Shader-Designer](../designers/shader-designer.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Anwenden eines Shaders auf ein 3D-Modell](../designers/how-to-apply-a-shader-to-a-3-d-model.md)   
 [Bildbearbeitung](../designers/image-editor.md)   
 [Shader-Designer](../designers/shader-designer.md)   
 [Shader-Designer-Knoten](../designers/shader-designer-nodes.md)



