---
title: Vector::Reference (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::vector::reference
dev_langs: C++
helpviewer_keywords: reference member [STL/CLR]
ms.assetid: 6ea0d3b0-d2e6-42c3-856c-a10f5ef7620c
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6a810b63676a7f4b15d01496f4137699d9dc1791
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="vectorreference-stlclr"></a>vector::reference (STL/CLR)
Bir öğe için bir başvuru türü.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef value_type% reference;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bir öğe için bir başvuru türü açıklanmaktadır.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_vector_reference.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    cliext::vector<wchar_t>::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        {   // get a reference to an element   
        cliext::vector<wchar_t>::reference ref = *it;   
        System::Console::Write(" {0}", ref);   
        }   
    System::Console::WriteLine();   
  
// modify contents " a b c"   
    for (it = c1.begin(); it != c1.end(); ++it)   
        {   // get a reference to an element   
        cliext::vector<wchar_t>::reference ref = *it;   
  
        ref += (wchar_t)(L'A' - L'a');   
        System::Console::Write(" {0}", ref);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
A B C  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/vektör >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [vektör (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [Vector::const_reference (STL/CLR)](../dotnet/vector-const-reference-stl-clr.md)   
 [Vector::value_type (STL/CLR)](../dotnet/vector-value-type-stl-clr.md)