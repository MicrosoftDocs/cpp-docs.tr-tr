---
title: Vector::pop_back (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::vector::pop_back
dev_langs: C++
helpviewer_keywords: pop_back member [STL/CLR]
ms.assetid: 7e9fb72c-e733-4434-a71c-e4389629a821
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: fd4d93caf98a9a79ccf88799239d93bcefc830f3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="vectorpopback-stlclr"></a>vector::pop_back (STL/CLR)
Son öğeyi kaldırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void pop_back();  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Üye işlevi boş olmalıdır denetimli dizisi son öğeyi kaldırır. Vektör arkadaki bir öğe tarafından kısaltmak için kullanın.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_vector_pop_back.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// pop an element and redisplay   
    c1.pop_back();   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/vektör >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [vektör (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [vector::push_back (STL/CLR)](../dotnet/vector-push-back-stl-clr.md)