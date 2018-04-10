---
title: İşleç&gt; (deque) (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- cliext::deque::operator>
dev_langs:
- C++
helpviewer_keywords:
- operator> member [STL/CLR]
ms.assetid: b207be0a-c6d8-4d70-8b8d-beb48e859441
caps.latest.revision: 17
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0a3d60a1b2f54ceb336e70f93c359793cd7cd082
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="operatorgt-deque-stlclr"></a>İşleç&gt; (deque) (STL/CLR)
Deque karşılaştırma büyük.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Value>  
    bool operator>(deque<Value>% left,  
        deque<Value>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 left  
 Karşılaştırılacak sol kapsayıcı.  
  
 sağ  
 Karşılaştırılacak sağ kapsayıcı.  
  
## <a name="remarks"></a>Açıklamalar  
 İşleç işlevi döndürür `right` `<` `left`. Test etmek için kullandığınız olup olmadığını `left` sonra sıralanmış `right` iki deques öğe tarafından karşılaştırılan öğe olduğunda.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_deque_operator_gt.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::deque<wchar_t> c2;   
    c2.push_back(L'a');   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] > [a b c] is {0}",   
        c1 > c1);   
    System::Console::WriteLine("[a b d] > [a b c] is {0}",   
        c2 > c1);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
 a b d  
[a b c] > [a b c] is False  
[a b d] > [a b c] is True  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/deque >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [operator == (deque) (STL/CLR)](../dotnet/operator-equality-deque-stl-clr.md)   
 [deque::operator! = (STL/CLR)](../dotnet/deque-operator-inequality-stl-clr.md)   
 [İşleç\< (deque) (STL/CLR)](../dotnet/operator-less-than-deque-stl-clr.md)   
 [operator > = (deque) (STL/CLR)](../dotnet/operator-greater-or-equal-deque-stl-clr.md)   
 [operator<= (deque) (STL/CLR)](../dotnet/operator-less-or-equal-deque-stl-clr.md)