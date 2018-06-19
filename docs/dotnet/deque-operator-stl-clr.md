---
title: deque::operator(stl/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::deque::operator[]
dev_langs:
- C++
helpviewer_keywords:
- operatormember [] [STL/CLR]
ms.assetid: d7653bb5-db48-4637-a25c-e7303e5d28da
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b7b07f9206e5794b3bcbe219b35cf4d90fd4d8bc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33110565"
---
# <a name="dequeoperatorstlclr"></a>deque::operator(stl/CLR)
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
// cliext_deque_operator_sub.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
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
 **Başlık:** \<cliext/deque >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [deque::at (STL/CLR)](../dotnet/deque-at-stl-clr.md)