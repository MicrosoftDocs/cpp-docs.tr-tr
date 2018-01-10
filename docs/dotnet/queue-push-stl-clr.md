---
title: Queue::push (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::queue::push
dev_langs: C++
helpviewer_keywords: push member [STL/CLR]
ms.assetid: 97cf1f98-d4c4-417f-b57a-89cdd351ef65
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 24a3617a355aaaba5b2dfe375ac7a139a4f8da44
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="queuepush-stlclr"></a>queue::push (STL/CLR)
Yeni bir son öğesi ekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void push(value_type val);  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Üye işlevini değeri olan bir öğe ekler `val` sıranın sonunda. Kuyruğa bir öğe eklemek için kullanın.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_queue_push.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
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
a b c  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/kuyruk >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [sıra (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [queue::pop (STL/CLR)](../dotnet/queue-pop-stl-clr.md)