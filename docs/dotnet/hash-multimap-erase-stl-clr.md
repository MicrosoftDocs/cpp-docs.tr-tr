---
title: hash_multimap::ERASE (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::hash_multimap::erase
dev_langs: C++
helpviewer_keywords: erase member [STL/CLR]
ms.assetid: 663c67f6-8070-47db-abdc-58f7ace69736
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 312284499ec87f2425c02ce6e2bdec2a2d3f533f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="hashmultimaperase-stlclr"></a>hash_multimap::erase (STL/CLR)
Belirtilen konumlardaki öğeleri kaldırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
iterator erase(iterator where);  
iterator erase(iterator first, iterator last);  
bool erase(key_type key)  
```  
  
#### <a name="parameters"></a>Parametreler  
 ilk  
 Silme aralığını başlangıcı.  
  
 anahtar  
 Silmek için anahtar değeri.  
  
 Son  
 Silinecek aralığı sonu.  
  
 Burada  
 Silinecek öğe.  
  
## <a name="remarks"></a>Açıklamalar  
 İlk üye işlevi gösterdiği denetimli sırasının öğeyi kaldırır `where`ve kaldırıldı, öğenin dışında kalan ilk öğe atayan bir yineleyici döndürür veya [hash_multimap::end (STL/CLR)](../dotnet/hash-multimap-end-stl-clr.md) `()` böyle bir öğe varsa. Tek bir öğe kaldırmak için kullanın.  
  
 İkinci üye işlevi denetlenen sıradaki aralığında kaldırır [`first`, `last`) ve kaldırıldı, herhangi bir öğenin dışında kalan ilk öğe atayan bir yineleyici döndürür veya `end()` böyle bir öğe varsa mevcut... Sıfır veya daha fazla bitişik öğeleri kaldırmak için kullanın.  
  
 Üçüncü üye işlevi olan anahtara sahip eşdeğer sıralama denetimli sırasının herhangi bir öğeyi kaldırır için `key`ve kaldırılan öğelerin sayısını döndürür. Kaldırmak ve belirtilen bir anahtarı eşleşen tüm öğeleri saymak için kullanın.  
  
 Her öğe Silinme zaman öğe sayısını logaritmasını orantılı denetimli sırayla alır.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_hash_multimap_erase.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;   
int main()   
    {   
    cliext::hash_multimap<wchar_t, int> c1;   
    c1.insert(cliext::hash_multimap<wchar_t, int>::make_value(L'a', 1));   
    c1.insert(cliext::hash_multimap<wchar_t, int>::make_value(L'b', 2));   
    c1.insert(cliext::hash_multimap<wchar_t, int>::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (cliext::hash_multimap<wchar_t, int>::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// erase an element and reinspect   
    cliext::hash_multimap<wchar_t, int>::iterator it =   
        c1.erase(c1.begin());   
    System::Console::WriteLine("erase(begin()) = [{0} {1}]",   
        it->first, it->second);   
  
// add elements and display " b c d e"   
    c1.insert(cliext::hash_multimap<wchar_t, int>::make_value(L'd', 4));   
    c1.insert(cliext::hash_multimap<wchar_t, int>::make_value(L'e', 5));   
    for each (cliext::hash_multimap<wchar_t, int>::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// erase all but end   
    it = c1.end();   
    it = c1.erase(c1.begin(), --it);   
    System::Console::WriteLine("erase(begin(), end()-1) = [{0} {1}]",   
        it->first, it->second);   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// erase end   
    System::Console::WriteLine("erase(L'x') = {0}", c1.erase(L'x'));   
    System::Console::WriteLine("erase(L'e') = {0}", c1.erase(L'e'));   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
erase(begin()) = [b 2]  
 [b 2] [c 3] [d 4] [e 5]  
erase(begin(), end()-1) = [e 5]  
size() = 1  
erase(L'x') = 0  
erase(L'e') = 1  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/hash_map >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [hash_multimap (STL/CLR)](../dotnet/hash-multimap-stl-clr.md)   
 [hash_multimap::clear (STL/CLR)](../dotnet/hash-multimap-clear-stl-clr.md)