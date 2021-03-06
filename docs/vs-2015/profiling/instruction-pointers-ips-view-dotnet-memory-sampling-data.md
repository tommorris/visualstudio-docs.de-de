---
title: 'Anweisungszeigeransicht: .NET-Speichersamplingdaten | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Instruction Pointers view
ms.assetid: 7d91cc14-e8e9-4ebb-b14f-b9f0da770508
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 21141483d462df0faee099c22e2b79fc1718880d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47509582"
---
# <a name="instruction-pointers-ips-view---net-memory-sampling-data"></a>Anweisungszeigeransicht: .NET-Speichersamplingdaten
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [Anweisungszeigern (IPs)-Ansicht – Samplingdaten für .NET Memory](https://docs.microsoft.com/visualstudio/profiling/instruction-pointers-ips-view-dotnet-memory-sampling-data).  
  
In der Anweisungszeigeransicht der Profilerstellungsdaten für die .NET-Speicherbelegung, die mithilfe der Samplingmethode erfasst wurden, werden die Assemblyanweisungen angezeigt, die während der Profilerstellungsausführung Arbeitsspeicher belegt haben. In den Spalten in der Ansicht werden auch die Größe und Anzahl der Zuordnungen aufgeführt.  
  
 Es sind nur exklusive Werte aufgeführt.  
  
|Spalte|Beschreibung|  
|------------|-----------------|  
|**Prozess-ID**|Die Prozess-ID (PID) der Profilerstellung.|  
|**Prozessname**|Der Prozessname.|  
|**Modulname**|Der Name des Moduls, das die Anweisung enthält|  
|**Modulpfad**|Der Pfad des Moduls, das die Anweisung enthält|  
|**Quelldatei**|Die Quelldatei, die die Anweisung enthält|  
|**Funktionsname**|Der Name der Funktion.|  
|**Funktionszeilennummer**|Die Zeilennummer des Anfangs dieser Funktion in der Quelldatei.|  
|**Funktionsadresse**|Die Startadresse der Funktion.|  
|**Quellanfangszeile**|Die Nummer der Anfangszeile in der Quelldatei, an der die Zuordnung aufgetreten ist.|  
|**Quellendzeile**|Die Nummer der Endzeile in der Quelldatei, an der die Zuordnung aufgetreten ist.|  
|**Quellanfangszeichen**|Das Offset des Startzeichens in der Quelldateizeile, an dem die Zuordnung aufgetreten ist.|  
|**Quellendzeichen**|Der Offset des Endzeichens der Quelldateizeile, an dem die Zuordnung aufgetreten ist.|  
|**Anweisungsadresse**|Die Adresse der Anweisung.|  
|**Exklusive Speicherbelegungen**|Die Gesamtanzahl der Objekte, die von dieser Anweisung erstellt wurden.|  
|**Exklusive Zuordnungen %**|Der Anteil aller Objekte, die während der Profilerstellung erstellt und von dieser Anweisung zugeordnet wurden.|  
|**Exklusive Bytes**|Die Anzahl von Bytes im Speicher, die während der Profilerstellung von der Anweisung zugeordnet wurden.|  
|**Exklusive Bytes %**|Der Anteil aller Bytes im Speicher, die während der Profilerstellung durch diese Anweisung zugeordnet wurden.|  
  
## <a name="see-also"></a>Siehe auch  
 [Anweisungszeigeransicht](../profiling/instruction-pointers-ips-view-sampling-data.md)



