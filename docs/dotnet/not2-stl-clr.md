---
title: not2 (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- cliext::not2
dev_langs:
- C++
helpviewer_keywords:
- not2 function [STL/CLR]
ms.assetid: f8aedcca-e4d1-4430-93b4-83dd55579d04
caps.latest.revision: 15
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 183ddc8d55f6948901118ba47ee237127a632020
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="not2-stlclr"></a>not2 (STL/CLR)
Oluşturan bir `binary_negate` bir functor için.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Fun>  
    binary_negate<Fun> not2(Fun% functor);  
```  
  
## <a name="template-parameters"></a>Şablon Parametreleri  
 Fun  
 Functor türü.  
  
## <a name="function-parameters"></a>İşlev parametreleri  
 functor  
 Kaydırma functor.  
  
## <a name="remarks"></a>Açıklamalar  
 Şablon işlevi döndürür [binary_negate (STL/CLR)](../dotnet/binary-negate-stl-clr.md)`<Fun>(functor)`. Mantıksal NOT teslim eden bir functor iki bağımsız değişken functor sarmalamak için kolay bir yol olarak kullanın.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_not2.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(4);   
    c1.push_back(3);   
    Myvector c2;   
    c2.push_back(4);   
    c2.push_back(4);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 3" and " 4 4"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (int elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::less<int> less_op;   
  
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(),   
        cliext::binary_negate<cliext::less<int> >(less_op));   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display with function   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(), cliext::not2(less_op));   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
4 3  
4 4  
1 0  
1 0  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/işlevsel >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [binary_negate (STL/CLR)](../dotnet/binary-negate-stl-clr.md)