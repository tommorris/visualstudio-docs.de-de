---
title: "EX_DBGPROP_INFO_FLAGS | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: EX_DBGPROP_INFO_FLAGS
apilocation: scrobj.dll
helpviewer_keywords: 
  - "EX_DBGPROP_INFO_FLAGS"
ms.assetid: ee309dfe-9432-4dff-8756-7a8d677f9dcc
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# EX_DBGPROP_INFO_FLAGS
Wird verwendet, um `ExtendedDebugPropertyInfo` Felder angeben.  
  
## Syntax  
  
```  
enum {  
   EX_DBGPROP_INFO_ID  =0x0100,  
   EX_DBGPROP_INFO_NTYPE  =0x0200,  
   EX_DBGPROP_INFO_NVALUE  =0x0400,  
   EX_DBGPROP_INFO_LOCKBYTES  =0x0800,  
   EX_DBGPROP_INFO_DEBUGEXTPROP  =0x1000  
};  
```  
  
## Mitglieder  
 EX\_DBGPROP\_INFORMATION\_ID  
 Initialisiert Bezeichner für die Eigenschaft.  
  
 EX\_DBGPROP\_INFORMATION\_NTYPE  
 Initialisiert Typ der Eigenschaft.  
  
 EX\_DBGPROP\_INFORMATION\_NVALUE  
 Initialisiert Wert der Eigenschaft.  
  
 EX\_DBGPROP\_INFORMATION\_LOCKBYTES  
 Initialisiert das `plb` Feld.  
  
 EX\_DBGPROP\_INFORMATION\_DEBUGEXTPROP  
 Initialisiert das `pDebugExtProp` Feld, das eine `IDebugExtendedProperty`\-Schnittstelle enthält.  
  
## Siehe auch  
 [ExtendedDebugPropertyInfo\-Struktur](../../winscript/reference/extendeddebugpropertyinfo-structure.md)   
 [IDebugExtendedProperty\-Schnittstelle](../../winscript/reference/idebugextendedproperty-interface.md)