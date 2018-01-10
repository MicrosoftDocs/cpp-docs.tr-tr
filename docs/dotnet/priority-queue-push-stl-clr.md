---
title: priority_queue::push (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::priority_queue::push
dev_langs: C++
helpviewer_keywords: push member [STL/CLR]
ms.assetid: 317d3feb-0688-4658-866b-a26cae060354
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d4b88448d1566076841b5f20754d02f3b62428b9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="priorityqueuepush-stlclr"></a>priority_queue::push (STL/CLR)
Yeni bir öğe ekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void push(value_type val);  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Üye işlevini değeri olan bir öğe ekler `val` içine denetimli dizisi ve yığın uzmanlık korumak için denetimli dizisi yeniden sıralar. Sıraya başka bir öğe eklemek için kullanın.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_priority_queue_push.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c a b  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/kuyruk >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [priority_queue::pop (STL/CLR)](../dotnet/priority-queue-pop-stl-clr.md)