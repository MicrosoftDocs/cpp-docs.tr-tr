---
title: "İşleç&lt; (yığın) (STL/CLR) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::stack::operator<
dev_langs: C++
helpviewer_keywords: operator< member [STL/CLR]
ms.assetid: 77f8dd42-89d1-4ce1-a7ec-04c3a45dd3ee
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5b0d2c7ef3da417c85cd7c4ec69714b8b635e46c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="operatorlt-stack-stlclr"></a>İşleç&lt; (yığın) (STL/CLR)
Yığın değerinden karşılaştırma.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Value,  
    typename Container>  
    bool operator<(stack<Value, Container>% left,  
        stack<Value, Container>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 left  
 Karşılaştırılacak sol kapsayıcı.  
  
 sağ  
 Karşılaştırılacak sağ kapsayıcı.  
  
## <a name="remarks"></a>Açıklamalar  
 İşleci işlevi döndürür true ise, en düşük konumunun `i` kendisi için `!(right[i] < left[i])` Ayrıca, true olan `left[i] < right[i]`. Aksi takdirde, döndürür `left->` [stack::size (STL/CLR)](../dotnet/stack-size-stl-clr.md) `() <` `right->size()` test etmek için kullandığınız olup olmadığını `left` önce sıralanır `right` iki yığınları öğe tarafından karşılaştırılan öğe olduğunda.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_stack_operator_lt.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mystack c2;   
    c2.push(L'a');   
    c2.push(L'b');   
    c2.push(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] < [a b c] is {0}",   
        c1 < c1);   
    System::Console::WriteLine("[a b c] < [a b d] is {0}",   
        c1 < c2);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
 a b d  
[a b c] < [a b c] is False  
[a b c] < [a b d] is True  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/stack >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yığın (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [operator == (yığın) (STL/CLR)](../dotnet/operator-equality-stack-stl-clr.md)   
 [operator! = (yığın) (STL/CLR)](../dotnet/operator-inequality-stack-stl-clr.md)   
 [operator > = (yığın) (STL/CLR)](../dotnet/operator-greater-or-equal-stack-stl-clr.md)   
 [operator > (yığın) (STL/CLR)](../dotnet/operator-greater-than-stack-stl-clr.md)   
 [operator < = (yığın) (STL/CLR)](../dotnet/operator-less-or-equal-stack-stl-clr.md)