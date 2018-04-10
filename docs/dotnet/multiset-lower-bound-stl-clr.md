---
title: multiset::lower_bound (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- cliext::multiset::lower_bound
dev_langs:
- C++
helpviewer_keywords:
- lower_bound member [STL/CLR]
ms.assetid: 5e3d1ba0-8b03-436e-b502-dbdb764f452b
caps.latest.revision: 14
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 79d7c0d73d311e6d5f56811655aab04009b1f33f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="multisetlowerbound-stlclr"></a>multiset::lower_bound (STL/CLR)
Belirtilen anahtarla eşleşen aralığının başlangıcını bulur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
iterator lower_bound(key_type key);  
```  
  
#### <a name="parameters"></a>Parametreler  
 anahtar  
 Aranacak anahtar değeri.  
  
## <a name="remarks"></a>Açıklamalar  
 Üye fonksiyonu ilk öğe belirler `X` için eşdeğer sıralama sahip denetlenen sıradaki `key`. Böyle bir öğe var olup olmadığını döndürür [multiset::end (STL/CLR)](../dotnet/multiset-end-stl-clr.md)`()`; Aksi takdirde, atayan yineleyici döndürür `X`. Öğe dizisi başına şu anda belirtilen bir anahtar ile denetlenen sırayla bulmak için kullanın.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_multiset_lower_bound.cpp   
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
  
    System::Console::WriteLine("lower_bound(L'x')==end() = {0}",   
        c1.lower_bound(L'x') == c1.end());   
  
    System::Console::WriteLine("*lower_bound(L'a') = {0}",   
        *c1.lower_bound(L'a'));   
    System::Console::WriteLine("*lower_bound(L'b') = {0}",   
        *c1.lower_bound(L'b'));   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
lower_bound(L'x')==end() = True  
*lower_bound(L'a') = a  
*lower_bound(L'b') = b  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/kümesi >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [multiset (STL/CLR)](../dotnet/multiset-stl-clr.md)   
 [multiset::Count (STL/CLR)](../dotnet/multiset-count-stl-clr.md)   
 [multiset::equal_range (STL/CLR)](../dotnet/multiset-equal-range-stl-clr.md)   
 [multiset::Find (STL/CLR)](../dotnet/multiset-find-stl-clr.md)   
 [multiset::upper_bound (STL/CLR)](../dotnet/multiset-upper-bound-stl-clr.md)