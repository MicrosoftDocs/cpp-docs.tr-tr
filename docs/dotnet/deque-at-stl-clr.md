---
title: deque::AT (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::deque::at
dev_langs:
- C++
helpviewer_keywords:
- at member [STL/CLR]
ms.assetid: 9af83d8a-c519-4b2a-a25f-d3dc8bbb87fb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 703a24917ffdc42ef5668032bc21e166ba451d61
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="dequeat-stlclr"></a>deque::at (STL/CLR)
Belirtilen konumda bir öğe erişir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
reference at(size_type pos);  
```  
  
#### <a name="parameters"></a>Parametreler  
 POS  
 Erişim öğesinin konumu.  
  
## <a name="remarks"></a>Açıklamalar  
 Üye işlevi konumunda denetimli dizisi öğesine bir başvuru döndürür `pos`. Okumak veya bir öğe, konumu yazmak için kullandığınız biliyor.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_deque_at.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" using at   
    for (int i = 0; i < c1.size(); ++i)   
        System::Console::Write(" {0}", c1.at(i));   
    System::Console::WriteLine();   
  
// change an entry and redisplay   
    c1.at(1) = L'x';   
    for (int i = 0; i < c1.size(); ++i)   
        System::Console::Write(" {0}", c1[i]);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a x c  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/deque >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [deque::operator(STL/CLR)](../dotnet/deque-operator-stl-clr.md)