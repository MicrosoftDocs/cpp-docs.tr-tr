---
title: multimap::Find (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::multimap::find
dev_langs: C++
helpviewer_keywords: find member [STL/CLR]
ms.assetid: 94b42497-3be4-448c-8de9-0a072ae14fbf
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8bc962e8baf8b13b631f1346e1cf6098207a27a2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="multimapfind-stlclr"></a>multimap::find (STL/CLR)
Belirtilen bir anahtarla eşleşen bir öğeyi bulur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
iterator find(key_type key);  
```  
  
#### <a name="parameters"></a>Parametreler  
 anahtar  
 Aranacak anahtar değeri.  
  
## <a name="remarks"></a>Açıklamalar  
 Denetlenen sıradaki en az bir öğe ile eşdeğer sıralama varsa `key`, bu öğelerden birine belirleme yineleyici üyesi fonksiyonunu döndürür; Aksi halde döner [multimap::end (STL/CLR)](../dotnet/multimap-end-stl-clr.md) `()`. Bir öğe şu anda belirtilen anahtarla eşleşen denetimli sırayla bulmak için kullanın.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_multimap_find.cpp   
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
  
    System::Console::WriteLine("find {0} = {1}",   
        L'A', c1.find(L'A') != c1.end());   
  
    Mymultimap::iterator it = c1.find(L'b');   
    System::Console::WriteLine("find {0} = [{1} {2}]",   
        L'b', it->first, it->second);   
  
    System::Console::WriteLine("find {0} = {1}",   
        L'C', c1.find(L'C') != c1.end());   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
find A = False  
find b = [b 2]  
find C = False  
```  
  
## <a name="description"></a>Açıklama  
 Unutmayın `find` , bulduğu birkaç öğenin garanti etmez.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/map >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [multimap (STL/CLR)](../dotnet/multimap-stl-clr.md)   
 [multimap::equal_range (STL/CLR)](../dotnet/multimap-equal-range-stl-clr.md)   
 [multimap::lower_bound (STL/CLR)](../dotnet/multimap-lower-bound-stl-clr.md)   
 [multimap::upper_bound (STL/CLR)](../dotnet/multimap-upper-bound-stl-clr.md)