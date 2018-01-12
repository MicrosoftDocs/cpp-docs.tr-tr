---
title: set::rbegin (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::set::rbegin
dev_langs: C++
helpviewer_keywords: rbegin member [STL/CLR]
ms.assetid: b9da72dc-0b75-489e-b179-74c27a4bcfb7
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e7ee4e2be7058bdb6ed83264de1425da8003c274
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="setrbegin-stlclr"></a>set::rbegin (STL/CLR)
Ters denetimli dizisi başlangıcını belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
reverse_iterator rbegin();  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Üye işlevini denetimli dizisi ya da boş bir dizi başına ötesinde yalnızca son öğesi atar ters bir yineleyici döndürür. Bu nedenle, atar `beginning` ters dizisi. Atayan bir yineleyici almak için kullandığınız `current` ters sırada görülen denetimli dizisi ancak durumunu başında denetimli sırası uzunluğu değişirse değiştirebilirsiniz.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_set_rbegin.cpp   
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
  
// inspect first two items in reversed sequence   
    Myset::reverse_iterator rit = c1.rbegin();   
    System::Console::WriteLine("*rbegin() = {0}", *rit);   
    System::Console::WriteLine("*++rbegin() = {0}", *++rit);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
*rbegin() = c  
*++rbegin() = b  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/kümesi >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [set (STL/CLR)](../dotnet/set-stl-clr.md)   
 [set::Begin (STL/CLR)](../dotnet/set-begin-stl-clr.md)   
 [set::End (STL/CLR)](../dotnet/set-end-stl-clr.md)   
 [set::rend (STL/CLR)](../dotnet/set-rend-stl-clr.md)