---
title: Queue::get_container (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::queue::get_container
dev_langs: C++
helpviewer_keywords: get_container member [STL/CLR]
ms.assetid: d87e7433-a352-4bea-8041-1ffc03287436
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c1badd817ab433a8bf6ca24d488a7ee8823005c0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="queuegetcontainer-stlclr"></a>queue::get_container (STL/CLR)
Temel alınan kapsayıcı erişir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
container_type^ get_container();  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Üye işlevi temel alınan kapsayıcı döndürür. Kapsayıcı sarmalayıcı tarafından uygulanan kısıtlamalar atlamak için kullanın.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_queue_get_container.cpp   
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
 [Queue::container_type (STL/CLR)](../dotnet/queue-container-type-stl-clr.md)