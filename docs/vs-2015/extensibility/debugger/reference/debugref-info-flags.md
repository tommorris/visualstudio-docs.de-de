---
title: DEBUGREF_INFO_FLAGS | Microsoft-Dokumentation
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
- DEBUGREF_INFO_FLAGS
helpviewer_keywords:
- DEBUGREF_INFO_FLAGS enumeration
ms.assetid: 1b043327-302a-4f6d-b51d-f94f9d7c7f9d
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: daa91fb99f11a3a41f80f7b9aa47c5cec0895f2d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47523023"
---
# <a name="debugrefinfoflags"></a>DEBUGREF_INFO_FLAGS
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [DEBUGREF_INFO_FLAGS](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/debugref-info-flags).  
  
Gibt an, welche Informationen Sie über ein Debug-Verweis-Objekt abzurufen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp#  
enum enum_DEBUGREF_INFO_FLAGS {   
   DEBUGREF_INFO_NAME             = 0x00000001,  
   DEBUGREF_INFO_TYPE             = 0x00000002,  
   DEBUGREF_INFO_VALUE            = 0x00000004,  
   DEBUGREF_INFO_ATTRIB           = 0x00000008,  
   DEBUGREF_INFO_REFTYPE          = 0x00000010,  
   DEBUGREF_INFO_REF              = 0x00000020,  
   DEBUGREF_INFO_VALUE_AUTOEXPAND = 0x00010000,  
   DEBUGREF_INFO_NONE             = 0x00000000,  
   DEBUGREF_INFO_ALL              = 0xffffffff  
};  
typedef DWORD DEBUGREF_INFO_FLAGS;  
```  
  
```csharp  
public enum enum_DEBUGREF_INFO_FLAGS {   
   DEBUGREF_INFO_NAME             = 0x00000001,  
   DEBUGREF_INFO_TYPE             = 0x00000002,  
   DEBUGREF_INFO_VALUE            = 0x00000004,  
   DEBUGREF_INFO_ATTRIB           = 0x00000008,  
   DEBUGREF_INFO_REFTYPE          = 0x00000010,  
   DEBUGREF_INFO_REF              = 0x00000020,  
   DEBUGREF_INFO_VALUE_AUTOEXPAND = 0x00010000,  
   DEBUGREF_INFO_NONE             = 0x00000000,  
   DEBUGREF_INFO_ALL              = 0xffffffff  
};  
```  
  
## <a name="members"></a>Member  
 DEBUGREF_INFO_NAME  
 Initialisieren und Verwenden der `bstrName` Feld in der Struktur.  
  
 DEBUGREF_INFO_TYPE  
 Initialisieren und Verwenden der `bstrType` Feld in der Struktur.  
  
 DEBUGREF_INFO_VALUE  
 Initialisieren und Verwenden der `bstrValue` Feld in der Struktur.  
  
 DEBUGREF_INFO_ATTRIB  
 Initialisieren und Verwenden der `dwAttrib` Feld in der Struktur.  
  
 DEBUGREF_INFO_REFTYPE  
 Initialisieren und Verwenden der `dwRefType` Feld in der Struktur.  
  
 DEBUGREF_INFO_REF  
 Initialisieren und Verwenden der `pReference` Feld in der Struktur.  
  
 DEBUGREF_INFO_VALUE_AUTOEXPAND  
 Feld mit dem Wert sollte den Wert automatisch erweitert, für diesen Objekttyp enthalten.  
  
 DEBUGREF_INFO_NONE  
 Gibt an, dass keine Flags festgelegt sind.  
  
 DEBUGREF_INFO_ALL  
 Gibt eine Maske der Flags an.  
  
## <a name="remarks"></a>Hinweise  
 Diese Flags werden an übergeben der [EnumChildren](../../../extensibility/debugger/reference/idebugreference2-enumchildren.md) und [GetReferenceInfo](../../../extensibility/debugger/reference/idebugreference2-getreferenceinfo.md) Methoden zum Erkennen der Felder der [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) sind, dass die Struktur initialisiert werden.  
  
 Verwendet für die `dwFields` Mitglied der `DEBUG_REFERENCE_INFO` Struktur, um anzugeben, welche Felder sind gültig und verwendet, wenn die Struktur zurückgegeben wird.  
  
 Diese Werte können kombiniert werden, mit einer bitweisen `OR`.  
  
## <a name="requirements"></a>Anforderungen  
 Header: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Siehe auch  
 [Enumerationen](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md)   
 [EnumChildren](../../../extensibility/debugger/reference/idebugreference2-enumchildren.md)   
 [GetReferenceInfo](../../../extensibility/debugger/reference/idebugreference2-getreferenceinfo.md)

