---
title: 'Idiaenumframedata:: Clone | Microsoft-Dokumentation'
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
- IDiaEnumFrameData::Clone Method
ms.assetid: 28a17300-1626-422f-a17a-3a4d3872c37c
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b9b658e0cf6d2d92df19d57051611e0ebb86663a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47509088"
---
# <a name="idiaenumframedataclone"></a>IDiaEnumFrameData::Clone
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [idiaenumframedata:: Clone](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiaenumframedata-clone).  
  
Erstellt einen Enumerator, der den gleichen Enumerationszustand wie der aktuelle Enumerator enthält.  
  
## <a name="syntax"></a>Syntax  
  
```cpp#  
HRESULT Clone(   
   IDiaEnumFrameData** ppenum  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 ppenum  
 [out] Gibt eine [IDiaEnumFrameData](../../debugger/debug-interface-access/idiaenumframedata.md) Objekt, das ein Duplikat des Enumerators enthält. Der Frame, die keine Daten sind doppelt vorhanden, nur den Enumerator.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, wird `S_OK`ist, andernfalls ein Fehlercode zurückgegeben.  
  
## <a name="see-also"></a>Siehe auch  
 [IDiaEnumFrameData](../../debugger/debug-interface-access/idiaenumframedata.md)



