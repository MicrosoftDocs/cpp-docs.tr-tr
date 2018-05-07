---
title: multimap::mapped_type (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::multimap::mapped_type
dev_langs:
- C++
helpviewer_keywords:
- mapped_type member [STL/CLR]
ms.assetid: 0b59c9a9-7f6a-4c3d-bdc6-0b90c28eff34
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 6d81a2ba04cdf5f9cd8bf53ad225f1e495bf2c0f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="multimapmappedtype-stlclr"></a>multimap::mapped_type (STL/CLR)
Her bir anahtar ile ilişkili bir eşlenen değer türü.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef Mapped mapped_type;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Şablon parametresi için bir eş anlamlı türüdür `Mapped`.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_multimap_mapped_type.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::multimap<wchar_t, int> Mymultimap;   
int main()   
    {   
    Mymultimap c1;   
    c1.insert(Mymultimap::make_value(L'a', 1));   
    c1.insert(Mymultimap::make_value(L'b', 2));   
    c1.insert(Mymultimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]" using mapped_type   
    for (Mymultimap::iterator it = c1.begin(); it != c1.end(); ++it)   
        {   // store element in mapped_type object   
        Mymultimap::mapped_type val = it->second;   
  
        System::Console::Write(" {0}", val);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
1 2 3  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/map >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [multimap (STL/CLR)](../dotnet/multimap-stl-clr.md)   
 [multimap::key_compare (STL/CLR)](../dotnet/multimap-key-compare-stl-clr.md)   
 [multimap::value_type (STL/CLR)](../dotnet/multimap-value-type-stl-clr.md)