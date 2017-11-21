---
title: set::lower_bound (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::set::lower_bound
dev_langs: C++
helpviewer_keywords: lower_bound member [STL/CLR]
ms.assetid: d4da5b8b-ddf2-4d36-8092-f1be81b42348
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d671ae501663c4875d8b4ff8507cf8e8942b34ed
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="setlowerbound-stlclr"></a>set::lower_bound (STL/CLR)
Belirtilen anahtarla eşleşen aralığının başlangıcını bulur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
iterator lower_bound(key_type key);  
```  
  
#### <a name="parameters"></a>Parametreler  
 anahtar  
 Aranacak anahtar değeri.  
  
## <a name="remarks"></a>Açıklamalar  
 Üye fonksiyonu ilk öğe belirler `X` için eşdeğer sıralama sahip denetlenen sıradaki `key`. Böyle bir öğe var olup olmadığını döndürür [set::end (STL/CLR)](../dotnet/set-end-stl-clr.md)`()`; Aksi takdirde, atayan yineleyici döndürür `X`. Öğe dizisi başına şu anda belirtilen bir anahtar ile denetlenen sırayla bulmak için kullanın.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_set_lower_bound.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::set<wchar_t> Myset;   
int main()   
    {   
    Myset c1;   
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
 [set (STL/CLR)](../dotnet/set-stl-clr.md)   
 [set::Count (STL/CLR)](../dotnet/set-count-stl-clr.md)   
 [set::equal_range (STL/CLR)](../dotnet/set-equal-range-stl-clr.md)   
 [set::Find (STL/CLR)](../dotnet/set-find-stl-clr.md)   
 [set::upper_bound (STL/CLR)](../dotnet/set-upper-bound-stl-clr.md)