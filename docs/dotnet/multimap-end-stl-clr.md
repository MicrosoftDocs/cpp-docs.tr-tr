---
title: multimap::End (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::multimap::end
dev_langs: C++
helpviewer_keywords: end member [STL/CLR]
ms.assetid: 8d3f9347-794d-4bd3-9bd1-50534fcf4ffe
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 055c24a2038c03c7a37d78b5f75bc5c169c7e280
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="multimapend-stlclr"></a>multimap::end (STL/CLR)
Denetlenen dizinin bitişini belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
iterator end();  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Üye işlevi yalnızca denetimli dizisi ötesinde işaret çift yönlü yineleyici döndürür. Denetimli bitişinde atayan bir yineleyici almak için kullanın; kendi durumu denetimli sırası uzunluğu değişirse değiştirmek içermiyor.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_multimap_end.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::multimap<wchar_t, int> Mymultimap;   
int main()   
    {   
    Mymultimap c1;   
    c1.insert(Mymultimap::make_value(L'a', 1));   
    c1.insert(Mymultimap::make_value(L'b', 2));   
    c1.insert(Mymultimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymultimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// inspect last two items   
    Mymultimap::iterator it = c1.end();   
    --it;   
    --it;   
    System::Console::WriteLine("*-- --end() = [{0} {1}]",   
        it->first, it->second);   
    ++it;   
    System::Console::WriteLine("*--end() = [{0} {1}]",   
        it->first, it->second);   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
*-- --end() = [b 2]  
*--end() = [c 3]  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/map >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [multimap (STL/CLR)](../dotnet/multimap-stl-clr.md)   
 [multimap::Begin (STL/CLR)](../dotnet/multimap-begin-stl-clr.md)