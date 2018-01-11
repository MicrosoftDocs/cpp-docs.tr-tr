---
title: operator! = (listesi) (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::list::operator!=
dev_langs: C++
helpviewer_keywords: operator!= member [STL/CLR]
ms.assetid: aa4e1461-8137-43df-a99c-fbec8dd3269f
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9411ff9e6e4a6f96059c89893eb4770442be7671
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="operator-list-stlclr"></a>operator!= (list) (STL/CLR)
Eşit değildir karşılaştırma listeleyin.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Value>  
    bool operator!=(list<Value>% left,  
        list<Value>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 left  
 Karşılaştırılacak sol kapsayıcı.  
  
 sağ  
 Karşılaştırılacak sağ kapsayıcı.  
  
## <a name="remarks"></a>Açıklamalar  
 İşleç işlevi döndürür `!(left == right)`. Test etmek için kullandığınız olup olmadığını `left` aynı sıralı değil `right` listelerini öğe tarafından karşılaştırılan öğe olduğunda.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_list_operator_ne.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::list<wchar_t> c2;   
    c2.push_back(L'a');   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] != [a b c] is {0}",   
        c1 != c1);   
    System::Console::WriteLine("[a b c] != [a b d] is {0}",   
        c1 != c2);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
 a b d  
[a b c] != [a b c] is False  
[a b c] != [a b d] is True  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/listesi >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Liste (STL/CLR)](../dotnet/list-stl-clr.md)   
 [operator == (liste) (STL/CLR)](../dotnet/operator-equality-list-stl-clr.md)   
 [İşleç\< (liste) (STL/CLR)](../dotnet/operator-less-than-list-stl-clr.md)   
 [operator > = (listesi) (STL/CLR)](../dotnet/operator-greater-or-equal-list-stl-clr.md)   
 [operator > (liste) (STL/CLR)](../dotnet/operator-greater-than-list-stl-clr.md)   
 [operator<= (list) (STL/CLR)](../dotnet/operator-less-or-equal-list-stl-clr.md)