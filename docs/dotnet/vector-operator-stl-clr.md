---
title: Vector::operator(stl/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::vector::operator[]
dev_langs:
- C++
helpviewer_keywords:
- operatormember [] [STL/CLR]
ms.assetid: 379a7029-460d-4de8-918b-c79e3e13b9d4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 516b999fd6cc9c38304faf09beb354d846b6ab09
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="vectoroperatorstlclr"></a>Vector::operator(stl/CLR)
Belirtilen konumda bir öğe erişir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
reference operator[](size_type pos);  
```  
  
#### <a name="parameters"></a>Parametreler  
 POS  
 Erişim öğesinin konumu.  
  
## <a name="remarks"></a>Açıklamalar  
 Üye işleci konumunda öğesine bir referene döndürür `pos`. Konum bildiğiniz bir öğe erişmek için kullanın.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_vector_operator_sub.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" using subscripting   
    for (int i = 0; i < c1.size(); ++i)   
        System::Console::Write(" {0}", c1[i]);   
    System::Console::WriteLine();   
  
// change an entry and redisplay   
    c1[1] = L'x';   
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
 **Başlık:** \<cliext/vektör >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [vektör (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [vector::at (STL/CLR)](../dotnet/vector-at-stl-clr.md)