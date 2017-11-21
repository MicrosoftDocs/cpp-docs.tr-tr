---
title: priority_queue::top_item (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::priority_queue::top_item
dev_langs: C++
helpviewer_keywords: top_item member [STL/CLR]
ms.assetid: d497403b-6b1d-4c6e-a0f4-c744cc5fad75
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4196146afe7f72ed9d72d4fb5696492079da9673
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="priorityqueuetopitem-stlclr"></a>priority_queue::top_item (STL/CLR)
En yüksek öncelikli öğenin erişir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
property value_type back_item;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Özelliği üst (en yüksek öncelik) öğe boş olmalıdır denetimli dizisi erişir. Okumak veya mevcut bildiğiniz durumlarda en yüksek öncelikli öğenin yazmak için kullanın.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_priority_queue_top_item.cpp   
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
    System::Console::WriteLine("top_item = {0}", c1.top_item);   
  
// alter last item and reinspect   
    c1.top_item = L'x';   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 c a b  
top_item = c  
 x a b  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/kuyruk >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [priority_queue::Top (STL/CLR)](../dotnet/priority-queue-top-stl-clr.md)