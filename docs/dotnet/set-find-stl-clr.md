---
title: set::Find (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::set::find
dev_langs: C++
helpviewer_keywords: find member [STL/CLR]
ms.assetid: 916e581c-2815-4c07-a51a-6c5ddfa730c1
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 82296d6da1a2b995026d75a2e2973335cd00ef5c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="setfind-stlclr"></a>set::find (STL/CLR)
Belirtilen bir anahtarla eşleşen bir öğeyi bulur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
iterator find(key_type key);  
```  
  
#### <a name="parameters"></a>Parametreler  
 anahtar  
 Aranacak anahtar değeri.  
  
## <a name="remarks"></a>Açıklamalar  
 Denetlenen sıradaki en az bir öğe ile eşdeğer sıralama varsa `key`, bu öğelerden birine belirleme yineleyici üyesi fonksiyonunu döndürür; Aksi halde döner [set::end (STL/CLR)](../dotnet/set-end-stl-clr.md)`()`. Bir öğe şu anda belirtilen anahtarla eşleşen denetimli sırayla bulmak için kullanın.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_set_find.cpp   
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
  
    System::Console::WriteLine("find {0} = {1}",   
        L'A', c1.find(L'A') != c1.end());   
    System::Console::WriteLine("find {0} = {1}",   
        L'b', *c1.find(L'b'));   
    System::Console::WriteLine("find {0} = {1}",   
        L'C', c1.find(L'C') != c1.end());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
find A = False  
find b = b  
find C = False  
```  
  
## <a name="description"></a>Açıklama  
 Unutmayın `find` , bulduğu birkaç öğenin garanti etmez.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/kümesi >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [set (STL/CLR)](../dotnet/set-stl-clr.md)   
 [set::equal_range (STL/CLR)](../dotnet/set-equal-range-stl-clr.md)   
 [set::lower_bound (STL/CLR)](../dotnet/set-lower-bound-stl-clr.md)   
 [set::upper_bound (STL/CLR)](../dotnet/set-upper-bound-stl-clr.md)