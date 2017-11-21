---
title: priority_queue::Top (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::priority_queue::top
dev_langs: C++
helpviewer_keywords: top member [STL/CLR]
ms.assetid: e45211d5-e6df-4c03-97fd-57afb87af58c
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: db32b4e3a9b744940c2467176e23d986ef9df23c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="priorityqueuetop-stlclr"></a>priority_queue::top (STL/CLR)
En yüksek öncelikli öğenin erişir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
reference top();  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Üye işlevi boş olmalıdır denetimli dizisi (en yüksek öncelik) üst öğesine başvuru döndürür. Mevcut bildiğiniz durumlarda en yüksek öncelikli öğenin erişmek için kullanın.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_priority_queue_top.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last item   
    System::Console::WriteLine("top() = {0}", c1.top());   
  
// alter last item and reinspect   
    c1.top() = L'x';   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 c a b  
top() = c  
 x a b  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/kuyruk >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [priority_queue::top_item (STL/CLR)](../dotnet/priority-queue-top-item-stl-clr.md)