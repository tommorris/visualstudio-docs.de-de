---
title: Erste Schritte (Debug Interface Access SDK) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- .dbg files
- DBG files
ms.assetid: cb3d040a-2846-40d7-bdbc-8a5beb5dd2f6
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 68b87c3789d0cc54f8492eed36c3028cf7a87df9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47512467"
---
# <a name="getting-started-debug-interface-access-sdk"></a>Erste Schritte (Debug Interface Access SDK)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [erste Schritte (Debug Interface Access SDK)](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/getting-started-debug-interface-access-sdk).  
  
Die Debug Interface Access (DIA) SDK stellt Sie bereit, mit dem Lehrzwecken Dokumentation und ein Beispiel, das veranschaulicht, wie Sie die DIA-API verwenden. Verwenden Sie die Schnittstellen und Methoden in DIA-SDK zum Entwickeln von benutzerdefinierter Anwendungen, die die PDB-Datei und .dbg-Dateien öffnen, und suchen Sie ihre Inhalte für Symbole, Werte, Attribute, Adressen und andere Debugginginformationen. Dieses SDK stellt außerdem Verweistabellen für die Eigenschaften für Symbole finden Sie in der C++-Anwendungen.  
  
 Um die DIA-SDK zu verwenden, sollten Sie mit folgendem vertraut sein:  
  
-   Programmiersprache C++  
  
-   COM-Programmierung  
  
-   Visual Studio integrierte Entwicklungsumgebung (IDE) für die Beispiele kompilieren  
  
 Die DIA-SDK wird normalerweise mit Visual Studio installiert und wird von seinem Standardspeicherort *[Laufwerk]* \Programme\Microsoft Visual Studio-9.0\DIA SDK. Im Rahmen der Installation wird der "MSDIA90.dll", das die DIA-SDK implementiert, wird automatisch registriert, daher müssen Sie es verwenden sollen `dia2.h` in Ihrem Programm und Verknüpfung mit `diaguids.lib`.  
  
 Header: include\dia2.h  
  
 Bibliothek: lib\diaguids.lib  
  
 DLL: bin\msdia80.dll  
  
 IDL: idl\dia2.idl  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Übersicht](../../debugger/debug-interface-access/overview-debug-interface-access-sdk.md)  
 Überprüft die grundlegende Architektur von Dia  
  
 [Abfragen der PDB-Datei](../../debugger/debug-interface-access/querying-the-dot-pdb-file.md)  
 Enthält schrittweise Anleitungen zur Verwendung der DIA-API zum Abfragen der PDB-Datei an.  
  
## <a name="see-also"></a>Siehe auch  
 [Debug Interface Access SDK](../../debugger/debug-interface-access/debug-interface-access-sdk.md)



