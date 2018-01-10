---
title: multiset::upper_bound (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::multiset::upper_bound
dev_langs: C++
helpviewer_keywords: upper_bound member [STL/CLR]
ms.assetid: 4a5af99f-a2a1-45be-9b01-c0055d4d0e35
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 94d3b2a9c127b11904583eab2e65e8b679b69db0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="multisetupperbound-stlclr"></a>multiset::upper_bound (STL/CLR)
Belirtilen anahtarla eşleşen aralığın sonuna bulur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
iterator upper_bound(key_type key);  
```  
  
#### <a name="parameters"></a>Parametreler  
 anahtar  
 Aranacak anahtar değeri.  
  
## <a name="remarks"></a>Açıklamalar  
 Üye fonksiyonu son öğe belirler `X` için eşdeğer sıralama sahip denetlenen sıradaki `key`. Böyle bir öğe varsa veya `X` Son denetlenen sıradaki döndürdüğü öğedir [multiset::end (STL/CLR)](../dotnet/multiset-end-stl-clr.md)`()`; Aksi takdirde, ilk öğe ötesindeatayanyineleyicidöndürür`X`. Öğelerin dizinin sonuna şu anda belirtilen bir anahtar ile denetlenen sırayla bulmak için kullanın.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_multiset_upper_bound.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("upper_bound(L'x')==end() = {0}",   
        c1.upper_bound(L'x') == c1.end());   
  
    System::Console::WriteLine("*upper_bound(L'a') = {0}",   
        *c1.upper_bound(L'a'));   
    System::Console::WriteLine("*upper_bound(L'b') = {0}",   
        *c1.upper_bound(L'b'));   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
upper_bound(L'x')==end() = True  
*upper_bound(L'a') = b  
*upper_bound(L'b') = c  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/kümesi >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [multiset (STL/CLR)](../dotnet/multiset-stl-clr.md)   
 [multiset::Count (STL/CLR)](../dotnet/multiset-count-stl-clr.md)   
 [multiset::equal_range (STL/CLR)](../dotnet/multiset-equal-range-stl-clr.md)   
 [multiset::Find (STL/CLR)](../dotnet/multiset-find-stl-clr.md)   
 [multiset::lower_bound (STL/CLR)](../dotnet/multiset-lower-bound-stl-clr.md)