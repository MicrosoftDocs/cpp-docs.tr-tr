---
title: hash_multimap::size_type (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::hash_multimap::size_type
dev_langs: C++
helpviewer_keywords: size_type member [STL/CLR]
ms.assetid: 4d266b1f-d0d6-4575-9abd-70fab719eb76
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: bd2887c6ada923d60b501dcc29f12d0c065cae1d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="hashmultimapsizetype-stlclr"></a>hash_multimap::size_type (STL/CLR)
İki öğe arasındaki imzalı uzaklığı türü.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef int size_type;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Türünü negatif olmayan öğe sayısını tanımlar.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_hash_multimap_size_type.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;   
int main()   
    {   
    Myhash_multimap c1;   
    c1.insert(Myhash_multimap::make_value(L'a', 1));   
    c1.insert(Myhash_multimap::make_value(L'b', 2));   
    c1.insert(Myhash_multimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Myhash_multimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// compute positive difference   
    Myhash_multimap::size_type diff = 0;   
    for (Myhash_multimap::iterator it = c1.begin(); it != c1.end(); ++it)   
        ++diff;   
    System::Console::WriteLine("end()-begin() = {0}", diff);   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
end()-begin() = 3  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/hash_map >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [hash_multimap (STL/CLR)](../dotnet/hash-multimap-stl-clr.md)   
 [hash_multimap::empty (STL/CLR)](../dotnet/hash-multimap-empty-stl-clr.md)