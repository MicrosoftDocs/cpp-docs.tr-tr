---
title: Stack::to_array (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::stack::to_array
dev_langs:
- C++
helpviewer_keywords:
- to_array member [STL/CLR]
ms.assetid: e83bd7c4-ffdb-4151-bd2b-c36ca828e12f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: fd743ca10097de45027dc48ea01020eaafcb41ee
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="stacktoarray-stlclr"></a>stack::to_array (STL/CLR)
Denetimli sırası yeni bir diziye kopyalar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
cli::array<Value>^ to_array();  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Üye işlevi denetimli sırası içeren bir dizi döndürür. Dizi formunda denetimli sırasının bir kopyasını almak için kullanın.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_stack_to_array.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// copy the container and modify it   
    cli::array<wchar_t>^ a1 = c1.to_array();   
  
    c1.push(L'd');   
    for each (wchar_t elem in c1.get_container())   
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
 **Başlık:** \<cliext/stack >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [stack (STL/CLR)](../dotnet/stack-stl-clr.md)