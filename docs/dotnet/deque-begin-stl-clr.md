---
title: deque::Begin (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::deque::begin
dev_langs: C++
helpviewer_keywords: begin member [STL/CLR]
ms.assetid: e99d20d2-bb33-415f-9bd6-fe331d8c2ba2
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4943971a82d1a87515a6e2ebc96963adeb49c6d9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="dequebegin-stlclr"></a>deque::begin (STL/CLR)
Denetlenen dizinin başlangıcını belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
iterator begin();  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Üye işlevi ilk öğe denetimli dizisi ya da yalnızca boş bir dizi ötesinde atar rasgele erişim yineleyici döndürür. Atayan bir yineleyici almak için kullandığınız `current` denetimli dizisi ancak durumunu başında denetimli sırası uzunluğu değişirse değiştirebilirsiniz.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_deque_begin.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items   
    cliext::deque<wchar_t>::iterator it = c1.begin();   
    System::Console::WriteLine("*begin() = {0}", *it);   
    System::Console::WriteLine("*++begin() = {0}", *++it);   
  
// alter first two items and reinspect   
    *--it = L'x';   
    *++it = L'y';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
*begin() = a  
*++begin() = b  
 x y c  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/deque >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [deque::End (STL/CLR)](../dotnet/deque-end-stl-clr.md)   
 [deque::Front (STL/CLR)](../dotnet/deque-front-stl-clr.md)   
 [deque::front_item (STL/CLR)](../dotnet/deque-front-item-stl-clr.md)