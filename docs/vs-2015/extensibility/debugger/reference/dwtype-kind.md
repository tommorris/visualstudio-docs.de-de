---
title: DwTYPE_KIND | Microsoft-Dokumentation
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
- dwTYPE_KIND
helpviewer_keywords:
- dwTYPE_KIND enumeration
ms.assetid: 6ff56b0f-c502-4e6c-9829-bfa05361b783
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 026cf5e3f26cc6faeb8e8829295c0875203d88d1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47520657"
---
# <a name="dwtypekind"></a>dwTYPE_KIND
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [DwTYPE_KIND](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/dwtype-kind).  
  
Gibt an, wie den Typ des interpretieren eine [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp#  
enum enum_dwTYPE_KIND {  
   TYPE_KIND_METADATA = 0x0001,  
   TYPE_KIND_PDB      = 0x0002,  
   TYPE_KIND_BUILT    = 0x0003,  
};  
  
typedef DWORD dwTYPE_KIND;  
```  
  
```csharp  
public enum enum_dwTYPE_KIND {  
   TYPE_KIND_METADATA = 0x0001,  
   TYPE_KIND_PDB      = 0x0002,  
   TYPE_KIND_BUILT    = 0x0003,  
};  
```  
  
#### <a name="parameters"></a>Parameter  
 TYPE_KIND_METADATA  
 Die [TYPE_INFO](../../../extensibility/debugger/reference/type-info.md) Union interpretiert werden soll, als eine [METADATA_TYPE](../../../extensibility/debugger/reference/metadata-type.md) Struktur.  
  
 TYPE_KIND_PDB  
 Die `TYPE_INFO` Union interpretiert werden soll, als eine [PDB_TYPE](../../../extensibility/debugger/reference/pdb-type.md) Struktur.  
  
 TYPE_KIND_BUILT  
 Die `TYPE_INFO` Union interpretiert werden soll, als eine [BUILT_TYPE](../../../extensibility/debugger/reference/built-type.md) Struktur.  
  
## <a name="remarks"></a>Hinweise  
 Die Werte dieser Enumeration werden in der `dwKind` Feld der [TYPE_INFO](../../../extensibility/debugger/reference/type-info.md) strukturieren und werden verwendet, um zu bestimmen, wie zum Interpretieren der `type` union-Member. Die `TYPE_INFO` Struktur wird zurückgegeben, durch einen Aufruf der [GetTypeInfo](../../../extensibility/debugger/reference/idebugfield-gettypeinfo.md) Methode.  
  
## <a name="requirements"></a>Anforderungen  
 Header: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Siehe auch  
 [Enumerationen](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [TYPE_INFO](../../../extensibility/debugger/reference/type-info.md)   
 [GetTypeInfo](../../../extensibility/debugger/reference/idebugfield-gettypeinfo.md)   
 [METADATA_TYPE](../../../extensibility/debugger/reference/metadata-type.md)   
 [PDB_TYPE](../../../extensibility/debugger/reference/pdb-type.md)   
 [BUILT_TYPE](../../../extensibility/debugger/reference/built-type.md)

