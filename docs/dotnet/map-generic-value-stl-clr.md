---
title: Map::generic_value (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- cliext::map::generic_value
dev_langs:
- C++
helpviewer_keywords:
- generic_value member [STL/CLR]
ms.assetid: bd42ec86-fb9e-4c0d-8cae-7187a8742a94
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0a06b97eb84ebd6d8534c6d26c5f750cd9bd4562
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="mapgenericvalue-stlclr"></a>map::generic_value (STL/CLR)
Kapsayıcı için genel arabirimi ile kullanmak için öğenin türü.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef GValue generic_value;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Türünde bir nesne türünü açıklayan `GValue` kullanmak için saklı öğesi değeri bu şablonu kapsayıcı sınıfı için genel arabirimi açıklar.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_map_generic_value.cpp   
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
  
// construct a generic container   
    Mymap::generic_container^ gc1 = %c1;   
    for each (Mymap::value_type elem in gc1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// get an element and display it   
    Mymap::generic_iterator gcit = gc1->begin();   
    Mymap::generic_value gcval = *gcit;   
    System::Console::WriteLine(" [{0} {1}]", gcval->first, gcval->second);   
    return (0);   
    }  
  
```  
  
```Output  
[a 1] [b 2] [c 3]  
[a 1] [b 2] [c 3]  
[a 1]  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/map >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [eşleme (STL/CLR)](../dotnet/map-stl-clr.md)   
 [Map::generic_container (STL/CLR)](../dotnet/map-generic-container-stl-clr.md)   
 [Map::generic_iterator (STL/CLR)](../dotnet/map-generic-iterator-stl-clr.md)   
 [map::generic_reverse_iterator (STL/CLR)](../dotnet/map-generic-reverse-iterator-stl-clr.md)