---
title: TASK_STATE_WAITING_ON_CHILDREN-Feld | Microsoft-Dokumentation
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- TASK_STATE_WAITING_ON_CHILDREN field, Task class [.NET Framework debug engines]
ms.assetid: 6f26b098-84ad-4f6e-ba27-6136581ba630
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e69d8473e877807a6f1d80ca7844d78a38aa82d7
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47512675"
---
# <a name="taskstatewaitingonchildren-field"></a>TASK_STATE_WAITING_ON_CHILDREN-Feld
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [TASK_STATE_WAITING_ON_CHILDREN-Feld](https://docs.microsoft.com/visualstudio/extensibility/debugger/task-state-waiting-on-children-field).  
  
Die Aufgabe der Delegat Ausführung abgeschlossen hat und wartet implizit angefügter untergeordneter Aufgaben ausführen.  
  
 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **Assembly:** "mscorlib" (in "mscorlib.dll")  
  
 Da Sie diesen internen Member von .NET Framework zugreifen können, wird die folgende Syntax in Common Intermediate Language (CIL) bereitgestellt.  
  
## <a name="syntax"></a>Syntax  
  
```  
.field static assembly literal int32 TASK_STATE_WAITING_ON_CHILDREN = int32(0x01000000)  
```  
  
## <a name="remarks"></a>Hinweise  
 Wenn die [M_stateFlags](../../extensibility/debugger/m-stateflags-field.md) Feld enthält diesen Wert, der <xref:System.Threading.Tasks.Task.Status%2A> -Eigenschaft gibt <xref:System.Threading.Tasks.TaskStatus?displayProperty=fullName>.  
  
## <a name="see-also"></a>Siehe auch  
 [Aufgabenklasse](../../extensibility/debugger/task-class-internal-members.md)

