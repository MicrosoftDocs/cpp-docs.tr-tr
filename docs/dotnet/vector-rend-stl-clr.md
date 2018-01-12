---
title: Vector::rend (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::vector::rend
dev_langs: C++
helpviewer_keywords: rend member [STL/CLR]
ms.assetid: 8dc1927f-9214-468d-877e-eda20c03e90d
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d322895e2421bfd11d6d402f332aa84daff74ece
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="vectorrend-stlclr"></a>vector::rend (STL/CLR)
Ters denetimli dizinin sonuna belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
reverse_iterator rend();  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Üye işlevini ters yineleyici başına yalnızca ötesinde işaret denetimli dizisi döndürür. Bu nedenle, atar `end` ters dizisi. Atayan bir yineleyici almak için kullandığınız `current` ters sırada görülen denetimli dizisi ancak durumunu sonuna denetimli sırası uzunluğu değişirse değiştirebilirsiniz.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_vector_rend.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items   
    cliext::vector<wchar_t>::reverse_iterator rit = c1.rend();   
    --rit;   
    System::Console::WriteLine("*-- --rend() = {0}", *--rit);   
    System::Console::WriteLine("*--rend() = {0}", *++rit);   
  
// alter first two items and reinspect   
    *--rit = L'x';   
    *++rit = L'y';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
*-- --rend() = b  
*--rend() = a  
 y x c  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/vektör >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [vektör (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [Vector::Begin (STL/CLR)](../dotnet/vector-begin-stl-clr.md)   
 [Vector::End (STL/CLR)](../dotnet/vector-end-stl-clr.md)   
 [vector::rbegin (STL/CLR)](../dotnet/vector-rbegin-stl-clr.md)