---
title: hash_map::ERASE (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::hash_map::erase
dev_langs: C++
helpviewer_keywords: erase member [STL/CLR]
ms.assetid: 1d2a79aa-62f7-461c-8f7c-7b660eb189be
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8102d87f0770d4bbe702c235986805f03d0d782d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="hashmaperase-stlclr"></a>hash_map::erase (STL/CLR)
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
 İlk üye işlevi gösterdiği denetimli sırasının öğeyi kaldırır `where`ve kaldırıldı, öğenin dışında kalan ilk öğe atayan bir yineleyici döndürür veya [hash_map::end (STL/CLR)](../dotnet/hash-map-end-stl-clr.md) `()` böyle bir öğe varsa. Tek bir öğe kaldırmak için kullanın.  
  
 İkinci üye işlevi denetlenen sıradaki aralığında kaldırır [`first`, `last`) ve kaldırıldı, herhangi bir öğenin dışında kalan ilk öğe atayan bir yineleyici döndürür veya `end()` böyle bir öğe varsa mevcut... Sıfır veya daha fazla bitişik öğeleri kaldırmak için kullanın.  
  
 Üçüncü üye işlevi olan anahtara sahip eşdeğer sıralama denetimli sırasının herhangi bir öğeyi kaldırır için `key`ve kaldırılan öğelerin sayısını döndürür. Kaldırmak ve belirtilen bir anahtarı eşleşen tüm öğeleri saymak için kullanın.  
  
 Her öğe Silinme zaman öğe sayısını logaritmasını orantılı denetimli sırayla alır.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_hash_map_erase.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_map<wchar_t, int> Myhash_map;   
int main()   
    {   
    cliext::hash_map<wchar_t, int> c1;   
    c1.insert(cliext::hash_map<wchar_t, int>::make_value(L'a', 1));   
    c1.insert(cliext::hash_map<wchar_t, int>::make_value(L'b', 2));   
    c1.insert(cliext::hash_map<wchar_t, int>::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (cliext::hash_map<wchar_t, int>::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// erase an element and reinspect   
    cliext::hash_map<wchar_t, int>::iterator it =   
        c1.erase(c1.begin());   
    System::Console::WriteLine("erase(begin()) = [{0} {1}]",   
        it->first, it->second);   
  
// add elements and display " b c d e"   
    c1.insert(cliext::hash_map<wchar_t, int>::make_value(L'd', 4));   
    c1.insert(cliext::hash_map<wchar_t, int>::make_value(L'e', 5));   
    for each (cliext::hash_map<wchar_t, int>::value_type elem in c1)   
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
 [hash_map (STL/CLR)](../dotnet/hash-map-stl-clr.md)   
 [hash_map::Clear (STL/CLR)](../dotnet/hash-map-clear-stl-clr.md)