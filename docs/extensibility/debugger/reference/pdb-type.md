---
title: PDB_TYPE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- PDB_TYPE
helpviewer_keywords:
- PDB_TYPE structure
ms.assetid: 1c1bb772-77d6-4870-90b2-fd9247d0004e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: dc610963fa1ca82fec30e04abb90583db48bdf55
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
ms.locfileid: "31125373"
---
# <a name="pdbtype"></a>PDB_TYPE
Diese Struktur gibt Informationen über ein Symbol PDB entnommen Feldtyp an.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef struct _tagTYPE_PDB {  
   ULONG32 ulAppDomainID;  
   GUID    guidModule;  
   DWORD   symid;  
} PDB_TYPE;  
```  
  
```csharp  
public struct PDB_TYPE {  
   public uint ulAppDomainID;  
   public Guid guidModule;  
   public uint symid;  
};  
```  
  
#### <a name="parameters"></a>Parameter  
 ulAppDomainID  
 Die ID der Anwendung, von der das Symbol stammt. Dient zur eindeutigen Identifizierung eine Instanz der Anwendung.  
  
 guidModule  
 Die GUID des Moduls, das dieses Feld enthält.  
  
 symid  
 Die ID des Symbols, das dieses Feld entspricht.  
  
## <a name="remarks"></a>Hinweise  
 Diese Struktur wird als Teil der Union der [TYPE_INFO](../../../extensibility/debugger/reference/type-info.md) strukturieren, wenn die `dwKind` -Feld der der `TYPE_INFO` Struktur auf festgelegt ist `TYPE_KIND_PDB` (ein Wert aus der [DwTYPE_KIND](../../../extensibility/debugger/reference/dwtype-kind.md) die Enumeration).  
  
## <a name="requirements"></a>Anforderungen  
 Header: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen und Unions](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [TYPE_INFO](../../../extensibility/debugger/reference/type-info.md)   
 [dwTYPE_KIND](../../../extensibility/debugger/reference/dwtype-kind.md)