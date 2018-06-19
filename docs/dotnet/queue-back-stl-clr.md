---
title: Queue::Back (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::queue::back
dev_langs:
- C++
helpviewer_keywords:
- back member [STL/CLR]
ms.assetid: 983a5c0f-0a2f-475f-932b-e7dec9eaffbb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 5a8a7e107b624be256fbe3882a857af066ec4228
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33159905"
---
# <a name="queueback-stlclr"></a>queue::back (STL/CLR)
Son öğe erişir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
reference back();  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Üye işlevini son öğe boş olmalıdır denetimli dizisi için bir başvuru döndürür. Mevcut bildiğinizde son öğesine erişmek için kullanın.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_queue_back.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last item   
    System::Console::WriteLine("back() = {0}", c1.back());   
  
// alter last item and reinspect   
    c1.back() = L'x';   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
back() = c  
 a b x  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/kuyruk >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [sıra (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [Queue::back_item (STL/CLR)](../dotnet/queue-back-item-stl-clr.md)   
 [Queue::Front (STL/CLR)](../dotnet/queue-front-stl-clr.md)   
 [queue::front_item (STL/CLR)](../dotnet/queue-front-item-stl-clr.md)