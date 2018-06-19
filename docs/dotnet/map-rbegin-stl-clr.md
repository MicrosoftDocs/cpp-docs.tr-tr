---
title: Map::rbegin (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::map::rbegin
dev_langs:
- C++
helpviewer_keywords:
- rbegin member [STL/CLR]
ms.assetid: bd7165a3-561f-48d4-9791-7aaafc2cf3a5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 65ae106d9d0e2593f5c06612a04494d2372ec82d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33135059"
---
# <a name="maprbegin-stlclr"></a>map::rbegin (STL/CLR)
Ters denetimli dizisi başlangıcını belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
reverse_iterator rbegin();  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Üye işlevini denetimli dizisi ya da boş bir dizi başına ötesinde yalnızca son öğesi atar ters bir yineleyici döndürür. Bu nedenle, atar `beginning` ters dizisi. Atayan bir yineleyici almak için kullandığınız `current` ters sırada görülen denetimli dizisi ancak durumunu başında denetimli sırası uzunluğu değişirse değiştirebilirsiniz.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_map_rbegin.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
int main()   
    {   
    Mymap c1;   
    c1.insert(Mymap::make_value(L'a', 1));   
    c1.insert(Mymap::make_value(L'b', 2));   
    c1.insert(Mymap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// inspect first two items in reversed sequence   
    Mymap::reverse_iterator rit = c1.rbegin();   
    System::Console::WriteLine("*rbegin() = [{0} {1}]",   
        rit->first, rit->second);   
    ++rit;   
    System::Console::WriteLine("*++rbegin() = [{0} {1}]",   
        rit->first, rit->second);   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
*rbegin() = [c 3]  
*++rbegin() = [b 2]  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/map >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [eşleme (STL/CLR)](../dotnet/map-stl-clr.md)   
 [Map::Begin (STL/CLR)](../dotnet/map-begin-stl-clr.md)   
 [Map::End (STL/CLR)](../dotnet/map-end-stl-clr.md)   
 [map::rend (STL/CLR)](../dotnet/map-rend-stl-clr.md)