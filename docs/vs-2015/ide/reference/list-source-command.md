---
title: Befehl „Quelle auflisten“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- Debug.ListSource
helpviewer_keywords:
- Debug.ListSource command
- list source command
- ListSource command
ms.assetid: e45f08d2-f4a3-49c3-9452-aa60508e2f74
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ce57d39d609268e2570d588e6863eb1e8b8d3111
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47514747"
---
# <a name="list-source-command"></a>Befehl "Quelle auflisten"
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [Befehl "Quelle auflisten"](https://docs.microsoft.com/visualstudio/ide/reference/list-source-command).  
  
  
Zeigt die angegebenen Quellcodezeilen an.  
  
## <a name="syntax"></a>Syntax  
  
```  
Debug.ListSource [/Count:number] [/Current] [/File:filename]  
[/Line:number] [/ShowLineNumbers:yes|no]  
```  
  
## <a name="switches"></a>Schalter  
 /Count:`number`  
 Dies ist optional. Gibt die Anzahl der anzuzeigenden Zeilen an.  
  
 /Current  
 Dies ist optional. Zeigt die aktuelle Zeile an.  
  
 /File:`filename`  
 Dies ist optional. Pfad der anzuzeigenden Datei. Ist kein Dateiname angegeben, zeigt der Befehl den Quellcode für die Zeile der aktuellen Anweisung an.  
  
 /Line:`number`  
 Dies ist optional. Zeigt eine bestimmte Zeilennummer an.  
  
 /ShowLineNumbers:`yes|no`  
 Dies ist optional. Gibt an, ob Zeilennummern angezeigt werden sollen.  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel listet den Quellcode aus Zeile 4 der Datei „Form1.vb“ mit eingeblendeten Zeilennummern an.  
  
```  
Debug.ListSource /File:"C:\Visual Studio Projects\Form1.vb" /Line:4 /ShowLineNumbers:yes  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Studio-Befehle](../../ide/reference/visual-studio-commands.md)   
 [Befehlsfenster](../../ide/reference/command-window.md)



