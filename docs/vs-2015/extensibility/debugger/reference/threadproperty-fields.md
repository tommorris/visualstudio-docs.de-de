---
title: THREADPROPERTY_FIELDS | Microsoft-Dokumentation
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
- THREADPROPERTY_FIELDS
helpviewer_keywords:
- THREADPROPERTY_FIELDS enumeration
ms.assetid: 5b88acb9-03ea-4c29-a788-f0087dccbe23
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 861a7d51b69f72938750a3210c29b8ac560af016
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47511493"
---
# <a name="threadpropertyfields"></a>THREADPROPERTY_FIELDS
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [THREADPROPERTY_FIELDS](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/threadproperty-fields).  
  
Gibt an, welche Informationen über einen Thread abgerufen werden sollen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp#  
enum enum_THREADPROPERTY_FIELDS {   
   TPF_ID           = 0x0001,  
   TPF_SUSPENDCOUNT = 0x0002,  
   TPF_STATE        = 0x0004,  
   TPF_PRIORITY     = 0x0008,  
   TPF_NAME         = 0x0010,  
   TPF_LOCATION     = 0x0020,  
   TPF_ALLFIELDS    = 0xffffffff  
};  
typedef DWORD THREADPROPERTY_FIELDS;  
```  
  
```csharp  
public enum enum_THREADPROPERTY_FIELDS {   
   TPF_ID           = 0x0001,  
   TPF_SUSPENDCOUNT = 0x0002,  
   TPF_STATE        = 0x0004,  
   TPF_PRIORITY     = 0x0008,  
   TPF_NAME         = 0x0010,  
   TPF_LOCATION     = 0x0020,  
   TPF_ALLFIELDS    = 0xffffffff  
};  
```  
  
## <a name="members"></a>Member  
 TPF_ID  
 Initialisieren und Verwenden der `dwThreadId` Feld der [THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md) Struktur.  
  
 TPF_SUSPENDCOUNT  
 Initialisieren und Verwenden der `dwSuspendCount` Feld der `THREADPROPERTIE`S-Struktur.  
  
 TPF_STATE  
 Initialisieren und Verwenden der `dwThreadState` Feld der `THREADPROPERTIE`S-Struktur.  
  
 TPF_PRIORITY  
 Initialisieren und Verwenden der `bstrPriority` Feld der `THREADPROPERTIE`S-Struktur.  
  
 TPF_NAME  
 Initialisieren und Verwenden der `bstrName` Feld der `THREADPROPERTIE`S-Struktur.  
  
 TPF_LOCATION  
 Initialisieren und Verwenden der `bstrLocation` Feld der `THREADPROPERTIE`S-Struktur.  
  
 TPF_ALLFIELDS  
 Gibt alle Felder an.  
  
## <a name="remarks"></a>Hinweise  
 Diese Werte werden übergeben, als Argument an die [GetThreadProperties](../../../extensibility/debugger/reference/idebugthread2-getthreadproperties.md) Methode, um die Felder anzugeben der [THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md) sind, dass die Struktur initialisiert werden.  
  
 Diese Werte werden auch in verwendet `dwFields` Mitglied der `THREADPROPERTIES` Struktur, um anzugeben, welche Felder verwendet und gültig sind.  
  
 Diese Flags können kombiniert werden, mit einer bitweisen `OR`.  
  
## <a name="requirements"></a>Anforderungen  
 Header: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Siehe auch  
 [Enumerationen](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md)   
 [GetThreadProperties](../../../extensibility/debugger/reference/idebugthread2-getthreadproperties.md)

