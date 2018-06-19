---
title: Map::upper_bound (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::map::upper_bound
dev_langs:
- C++
helpviewer_keywords:
- upper_bound member [STL/CLR]
ms.assetid: d772b4a8-d0dc-439a-8b5b-3c91836d9256
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 30badf4dfc9113456ba9a32e1260b6a53005c782
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33133811"
---
# <a name="mapupperbound-stlclr"></a>map::upper_bound (STL/CLR)
Belirtilen anahtarla eşleşen aralığın sonuna bulur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
iterator upper_bound(key_type key);  
```  
  
#### <a name="parameters"></a>Parametreler  
 anahtar  
 Aranacak anahtar değeri.  
  
## <a name="remarks"></a>Açıklamalar  
 Üye fonksiyonu son öğe belirler `X` için eşdeğer sıralama sahip denetlenen sıradaki `key`. Böyle bir öğe varsa veya `X` Son denetlenen sıradaki döndürdüğü öğedir [map::end (STL/CLR)](../dotnet/map-end-stl-clr.md)`()`; Aksi takdirde, ilk öğe ötesindeatayanyineleyicidöndürür`X`. Öğelerin dizinin sonuna şu anda belirtilen bir anahtar ile denetlenen sırayla bulmak için kullanın.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_map_upper_bound.cpp   
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
  
    System::Console::WriteLine("upper_bound(L'x')==end() = {0}",   
        c1.upper_bound(L'x') == c1.end());   
  
    Mymap::iterator it = c1.upper_bound(L'a');   
    System::Console::WriteLine("*upper_bound(L'a') = [{0} {1}]",   
        it->first, it->second);   
    it = c1.upper_bound(L'b');   
    System::Console::WriteLine("*upper_bound(L'b') = [{0} {1}]",   
        it->first, it->second);   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
upper_bound(L'x')==end() = True  
*upper_bound(L'a') = [b 2]  
*upper_bound(L'b') = [c 3]  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/map >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [eşleme (STL/CLR)](../dotnet/map-stl-clr.md)   
 [Map::Count (STL/CLR)](../dotnet/map-count-stl-clr.md)   
 [Map::equal_range (STL/CLR)](../dotnet/map-equal-range-stl-clr.md)   
 [Map::Find (STL/CLR)](../dotnet/map-find-stl-clr.md)   
 [map::lower_bound (STL/CLR)](../dotnet/map-lower-bound-stl-clr.md)