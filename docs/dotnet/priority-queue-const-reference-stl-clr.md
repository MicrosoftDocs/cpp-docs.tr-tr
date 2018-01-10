---
title: priority_queue::const_reference (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::priority_queue::const_reference
dev_langs: C++
helpviewer_keywords: const_reference member [STL/CLR]
ms.assetid: 53829d08-f875-497a-bb90-655e7f1fd213
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7a95ee848f52fd493970b509171cd2155230a1d3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="priorityqueueconstreference-stlclr"></a>priority_queue::const_reference (STL/CLR)
Bir öğe için sabit bir başvuru türü.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef value_type% const_reference;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bir öğe için sabit bir başvuru türü açıklanmaktadır.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_priority_queue_const_reference.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display reversed contents " c b a"   
    for (; !c1.empty(); c1.pop())   
        {   // get a const reference to an element   
        Mypriority_queue::const_reference cref = c1.top();   
        System::Console::Write(" {0}", cref);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c b a  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/kuyruk >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [priority_queue::Reference (STL/CLR)](../dotnet/priority-queue-reference-stl-clr.md)   
 [priority_queue::value_type (STL/CLR)](../dotnet/priority-queue-value-type-stl-clr.md)