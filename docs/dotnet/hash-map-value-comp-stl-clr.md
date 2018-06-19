---
title: hash_map::value_comp (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_map::value_comp
dev_langs:
- C++
helpviewer_keywords:
- value_comp member [STL/CLR]
ms.assetid: b11a2dee-07e8-450c-8f85-979c0a15ae64
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 743fb3e77378949f3017b0324ef688c997400b12
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33109384"
---
# <a name="hashmapvaluecomp-stlclr"></a>hash_map::value_comp (STL/CLR)
İki öğenin değerleri için sıralama temsilci kopyalar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
value_compare^ value_comp();  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Üye işlevini denetimli sırasını belirlemek için kullanılan sıralama temsilci döndürür. İki öğenin değerleri karşılaştırmak için kullanın.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_hash_map_value_comp.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_map<wchar_t, int> Myhash_map;   
int main()   
    {   
    Myhash_map c1;   
    Myhash_map::value_compare^ kcomp = c1.value_comp();   
  
    System::Console::WriteLine("compare([L'a', 1], [L'a', 1]) = {0}",   
        kcomp(Myhash_map::make_value(L'a', 1),   
            Myhash_map::make_value(L'a', 1)));   
    System::Console::WriteLine("compare([L'a', 1], [L'b', 2]) = {0}",   
        kcomp(Myhash_map::make_value(L'a', 1),   
            Myhash_map::make_value(L'b', 2)));   
    System::Console::WriteLine("compare([L'b', 2], [L'a', 1]) = {0}",   
        kcomp(Myhash_map::make_value(L'b', 2),   
            Myhash_map::make_value(L'a', 1)));   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
compare([L'a', 1], [L'a', 1]) = True  
compare([L'a', 1], [L'b', 2]) = True  
compare([L'b', 2], [L'a', 1]) = False  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/hash_map >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [hash_map (STL/CLR)](../dotnet/hash-map-stl-clr.md)   
 [hash_map::value_compare (STL/CLR)](../dotnet/hash-map-value-compare-stl-clr.md)   
 [hash_map::value_type (STL/CLR)](../dotnet/hash-map-value-type-stl-clr.md)