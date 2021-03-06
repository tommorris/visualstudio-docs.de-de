---
title: Meldungsmarker | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.markers.message
ms.assetid: 721f40ca-5af2-4a01-b8b6-2b90f6cb7f89
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 72b93d497a68ba09237c28fc56159c379b50c9c1
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "35254562"
---
# <a name="message-markers"></a>Meldungsmarker
Ein Meldungsmarker stellt Protokollausgaben dar. Eine Meldung ist eine Zeichenfolge, die von einem bestimmten Thread zu einem bestimmten Zeitpunkt ausgegeben wird. Sie können Meldungen für die Verwendung mit anderen Tools in eine Textdatei exportieren. Sie können den Mauszeiger auf eine Nachricht in der Parallelitätsschnellansicht zeigen, um die Meldung anzuzeigen. Außerdem können Sie alle Meldungsmarker im [Markerbericht](../profiling/markers-report.md) anzeigen.  Die folgende Abbildung zeigt einen Meldungsmarker.  
  
## <a name="message-aggregation-markers"></a>Meldungsaggregationsmarker  
 Manchmal treten mehrere Meldungen so nah beieinander in der Nebenläufigkeitsschnellansicht auf, dass sie nicht einzeln gezeichnet werden können. Wenn dies geschieht, wird ein *Meldungsaggregationsmarker* angezeigt, der die zugrundeliegenden Meldungen darstellt. Wenn Sie mit dem Mauszeiger über eines dieser Symbole fahren, zeigt eine QuickInfo die Anzahl der zugrunde liegenden Meldungen an, die dargestellt werden. Um die Nachrichten anzuzeigen, zoomen Sie herein.  Wenn Sie bis zur maximalen Stufe vergrößern und weiterhin einen Aggregationsmarker angezeigt wird, können Sie die zugrunde liegenden Meldungen im [Markerbericht](../profiling/markers-report.md) anzeigen.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency Visualizer markers (Parallelitätsschnellansichtsmarker)](../profiling/concurrency-visualizer-markers.md)   
 [SDK der Nebenläufigkeitsschnellansicht](../profiling/concurrency-visualizer-sdk.md)