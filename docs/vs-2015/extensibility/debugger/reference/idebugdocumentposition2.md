---
title: IDebugDocumentPosition2 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugDocumentPosition2
helpviewer_keywords:
- IDebugDocumentPosition2 interface
ms.assetid: 0e838ced-12bb-4efc-b811-2b7c034b77b0
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d240388ee1331e8dbdb2148f58f7a761ddde7a83
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47513144"
---
# <a name="idebugdocumentposition2"></a>IDebugDocumentPosition2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [IDebugDocumentPosition2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugdocumentposition2).  
  
Diese Schnittstelle stellt eine abstrakte Position in einer Quelldatei dar.  
  
## <a name="syntax"></a>Syntax  
  
```  
IDebugDocumentPosition2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Hinweise für Implementierer  
 Diese Schnittstelle wird von Visual Studio in der Regel implementiert. Ein Debugmodul (DE) würde auch diese Schnittstelle implementieren, wenn sie einen eigenen Quellcode bereitstellen muss (wie bei der DE implementiert die [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md) Schnittstelle).  
  
## <a name="notes-for-callers"></a>Hinweise für Aufrufer  
 Diese Schnittstelle wird als Argument übergeben [EnumCodeContexts](../../../extensibility/debugger/reference/idebugprogram2-enumcodecontexts.md). Es ebenfalls als Teil des angegeben wird eine [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md) Union (insbesondere eine [BP_LOCATION_CODE_FILE_LINE](../../../extensibility/debugger/reference/bp-location-code-file-line.md) Struktur), die wiederum stammt von der [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) -Struktur wird verwendet, erstellen einen ausstehenden Haltepunkt.  
  
## <a name="methods-in-vtable-order"></a>Methoden in Vtable-Reihenfolge  
 Die folgende Tabelle zeigt die Methoden der `IDebugDocumentPosition2`.  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetFileName](../../../extensibility/debugger/reference/idebugdocumentposition2-getfilename.md)|Ruft ab, der Dateiname der Quelldatei, die Dokumentposition dieses enthält.|  
|[GetDocument](../../../extensibility/debugger/reference/idebugdocumentposition2-getdocument.md)|Ruft das Containerdokument ab.|  
|[IsPositionInDocument](../../../extensibility/debugger/reference/idebugdocumentposition2-ispositionindocument.md)|Bestimmt, ob dieser Position in dem angegebenen Dokument enthalten ist.|  
|[GetRange](../../../extensibility/debugger/reference/idebugdocumentposition2-getrange.md)|Ruft den Bereich für dieses Dokumentposition ab.|  
  
## <a name="requirements"></a>Anforderungen  
 Header: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Siehe auch  
 [EnumCodeContexts](../../../extensibility/debugger/reference/idebugprogram2-enumcodecontexts.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [BP_LOCATION_CODE_FILE_LINE](../../../extensibility/debugger/reference/bp-location-code-file-line.md)

