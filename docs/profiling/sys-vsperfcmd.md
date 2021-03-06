---
title: Sys (VSPerfCmd) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 294a6f9e-b49f-4c83-b322-5ac5411b66fb
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6c202dbaec3ad1bf894d3892f4f89be75c3a7ad7
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2018
---
# <a name="sys-vsperfcmd"></a>Sys (VSPerfCmd)
Die „VSPerfCmd.exe“-Option **Sys** legt das Profilerstellungereignis fest, für das ein Sampling für Aufrufereignisse (Funktionsaufrufe des Betriebssystems der Anwendung mit einem Profil) durchgeführt werden soll, und ändert optional die Anzahl der Systemaufrufe (standardmäßig 10) in einem Samplingintervall.  
  
 **Sys** kann nur in einer Befehlszeile verwendet werden, die auch die Optionen **Launch** (Starten) und **Attach** (Anfügen) enthält.  
  
 Standardmäßig ist das Profiler-Samplingereignis auf Prozessortaktzyklen eingestellt und das Samplingintervall beträgt 10.000.000. Die Optionen **Timer**, **PF**, **Sys** und **Counter** ermöglichen es Ihnen, das Samplingereignis und das Samplingintervall festzulegen. Die Option **GC** sammelt die .NET-Speicherdaten bei jedem Zuordnungs- und Garbage Collection-Ereignis. In einer Befehlszeile kann nur eine dieser Optionen angegeben werden.  
  
 Das Samplingereignis und -intervall können nur in der ersten Befehlszeile festgelegt werden, die die Option **Launch** (Starten) oder **Attach** (Anfügen) enthält.  
  
## <a name="syntax"></a>Syntax  
  
```cmd  
VSPerfCmd.exe {/Launch:AppName|Attach:PID} /Sys[:Events] [Options]  
```  
  
#### <a name="parameters"></a>Parameter  
 `Events`  
 Ein ganzzahliger Wert, der die Anzahl der Systemaufrufe in einem Samplingintervall angibt. Wenn `Events` nicht festgelegt wurde, wird das Intervall auf 10 festgelegt.  
  
## <a name="required-options"></a>Erforderliche Optionen  
 Für **Sys** ist eine der folgenden Optionen erforderlich.  
  
 **Starten:** `AppName`  
 Startet den Profiler und die von `AppName` festgelegten Anwendungen.  
  
 **Attach:** `PID`  
 Fügt den Profiler an den von `PID` angegebenen Prozess an.  
  
## <a name="invalid-options"></a>Ungültige Optionen  
 Die folgenden Optionen können nicht in derselben Befehlszeile wie **Sys** festgelegt werden.  
  
 **PF**[**:**`Events`]  
 Legt die Seitenstandards für das Samplingereignis fest und optional das Samplingintervall auf `Events`. Das standardmäßige PF-Intervall beträgt 10.  
  
 **Timer**[**:**`Cycles`]  
 Legt das Samplingereignis auf die Prozessortaktzyklen und das Samplingintervall optional auf `Cycles` fest. Das Timer-Standardintervall beträgt 10.000.000.  
  
 **Counter:** `Name`[`,Reload`[`,FriendlyName`]]  
 Legt das Samplingereignis auf den von `Name` festgelegten CPU-Leistungsindikator fest und das Samplingintervall auf `Reload`.  
  
 **GC**[**:**{**Allocation**|**Lifetime**}]  
 Sammelt .NET-Speicherdaten. Wenn der Parameter **Allocation** angegeben wird (Standard), werden Daten bei jedem Speicherbelegungsereignis gesammelt. Wenn jedoch der **Lifetime**-Parameter angegeben wird, werden die Daten auch bei jedem Garbage Collection-Ereignis gesammelt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird dargestellt, wie das Profilersamplingereignis auf Symstemaufrufe und das Samplingintervall auf 20 Aufrufe pro Beispiel festgelegt wird.  
  
```cmd  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe /Sys:20  
```  
  
## <a name="see-also"></a>Siehe auch  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Profilerstellung für eigenständige Anwendungen](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilerstellung für ASP.NET-Webanwendungen](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Erstellen von Dienstprofilen](../profiling/command-line-profiling-of-services.md)