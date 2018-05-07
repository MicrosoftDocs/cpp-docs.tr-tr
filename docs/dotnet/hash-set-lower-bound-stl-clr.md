---
title: hash_set::lower_bound (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_set::lower_bound
dev_langs:
- C++
helpviewer_keywords:
- lower_bound member [STL/CLR]
ms.assetid: 54fe8ee5-1977-4192-9cc6-b51e84b03a16
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f36f90a7585002610fa6d000130d14a616db7382
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="hashsetlowerbound-stlclr"></a>hash_set::lower_bound (STL/CLR)
Belirtilen anahtarla eşleşen aralığının başlangıcını bulur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
iterator lower_bound(key_type key);  
```  
  
#### <a name="parameters"></a>Parametreler  
 anahtar  
 Aranacak anahtar değeri.  
  
## <a name="remarks"></a>Açıklamalar  
 Üye fonksiyonu ilk öğe belirler `X` aynı kova olarak karmaları denetlenen sıradaki `key` ve için eşdeğer sıralama sahip `key`. Böyle bir öğe var olup olmadığını döndürür [hash_set::end (STL/CLR)](../dotnet/hash-set-end-stl-clr.md)`()`; Aksi takdirde, atayan yineleyici döndürür `X`. Öğe dizisi başına şu anda belirtilen bir anahtar ile denetlenen sırayla bulmak için kullanın.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_hash_set_lower_bound.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_set<wchar_t> Myhash_set;   
int main()   
    {   
    Myhash_set c1;   
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
 **Başlık:** \<cliext/hash_set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)   
 [hash_set::Count (STL/CLR)](../dotnet/hash-set-count-stl-clr.md)   
 [hash_set::equal_range (STL/CLR)](../dotnet/hash-set-equal-range-stl-clr.md)   
 [hash_set::Find (STL/CLR)](../dotnet/hash-set-find-stl-clr.md)   
 [hash_set::upper_bound (STL/CLR)](../dotnet/hash-set-upper-bound-stl-clr.md)