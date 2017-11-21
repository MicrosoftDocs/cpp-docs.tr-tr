---
title: Vector::to_array (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::vector::to_array
dev_langs: C++
helpviewer_keywords: to_array member [STL/CLR]
ms.assetid: 00e1f1c6-6ef5-4238-b95a-411059e0b69b
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 47904e1845d4f2d9abb8e289bfe5337bd25892aa
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="vectortoarray-stlclr"></a>vector::to_array (STL/CLR)
Denetimli sırası yeni bir diziye kopyalar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
cli::array<Value>^ to_array();  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Üye işlevi denetimli sırası içeren bir dizi döndürür. Dizi formunda denetimli sırasının bir kopyasını almak için kullanın.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_vector_to_array.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// copy the container and modify it   
    cli::array<wchar_t>^ a1 = c1.to_array();   
  
    c1.push_back(L'd');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display the earlier array copy   
    for each (wchar_t elem in a1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c d  
a b c  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/vektör >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [vektör (STL/CLR)](../dotnet/vector-stl-clr.md)