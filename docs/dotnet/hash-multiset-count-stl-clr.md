---
title: hash_multiset::Count (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::hash_multiset::count
dev_langs: C++
helpviewer_keywords: count member [STL/CLR]
ms.assetid: 2b31e6b6-3f2c-4042-a06d-90d3074aad43
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: ec9c982f61e5ec5cf5e67f1096ae6d6183975f32
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="hashmultisetcount-stlclr"></a>hash_multiset::count (STL/CLR)
Belirtilen bir anahtar ile eşleşen öğe sayısını bulur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
size_type count(key_type key);  
```  
  
#### <a name="parameters"></a>Parametreler  
 anahtar  
 Aranacak anahtar değeri.  
  
## <a name="remarks"></a>Açıklamalar  
 Üye işlevi ile eşdeğer sıralama sahip denetlenen sıradaki öğelerin sayısını döndürür. `key`. Belirtilen anahtar eşleşen öğe şu anda denetlenen sıradaki sayısını belirlemek için kullanın.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_hash_multiset_count.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_multiset<wchar_t> Myhash_multiset;   
int main()   
    {   
    Myhash_multiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("count(L'A') = {0}", c1.count(L'A'));   
    System::Console::WriteLine("count(L'b') = {0}", c1.count(L'b'));   
    System::Console::WriteLine("count(L'C') = {0}", c1.count(L'C'));   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
count(L'A') = 0  
count(L'b') = 1  
count(L'C') = 0  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/hash_set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [hash_multiset (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)   
 [hash_multiset::equal_range (STL/CLR)](../dotnet/hash-multiset-equal-range-stl-clr.md)