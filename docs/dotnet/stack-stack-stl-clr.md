---
title: Stack::Stack (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::stack::stack
dev_langs: C++
helpviewer_keywords: stack member [STL/CLR]
ms.assetid: f1cfb3fe-4d22-41e5-906b-e8faa0bcde9b
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a59b353bb6ca1dc55933234c68f39f4b76dd16a2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="stackstack-stlclr"></a>stack::stack (STL/CLR)
Bir kapsayıcı bağdaştırıcısı nesnesi oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
stack();  
stack(stack<Value, Container>% right);  
stack(stack<Value, Container>^ right);  
explicit stack(container_type% wrapped);  
```  
  
#### <a name="parameters"></a>Parametreler  
 sağ  
 Kopyalamak için nesne.  
  
 Sarmalanan  
 Kullanılacak Sarmalanan kapsayıcı.  
  
## <a name="remarks"></a>Açıklamalar  
 Oluşturucusu:  
  
 `stack();`  
  
 boş bir Sarmalanan kapsayıcı oluşturur. Boş bir başlangıç denetimli dizisini belirtmek için kullanın.  
  
 Oluşturucusu:  
  
 `stack(stack<Value, Container>% right);`  
  
 bir kopyası Sarmalanan bir kapsayıcı oluşturur `right.get_container()`. Yığın nesnesi tarafından denetlenen sırasının bir kopyasını bir ilk denetlenen sırası belirtmek için kullandığınız `right`.  
  
 Oluşturucusu:  
  
 `stack(stack<Value, Container>^ right);`  
  
 bir kopyası Sarmalanan bir kapsayıcı oluşturur `right->get_container()`. Yığın nesnesi tarafından denetlenen sırasının bir kopyasını bir ilk denetlenen sırası belirtmek için kullandığınız `*right`.  
  
 Oluşturucusu:  
  
 `explicit stack(container_type% wrapped);`  
  
 var olan bir kapsayıcı kullanan `wrapped` Sarmalanan kapsayıcı olarak. Var olan bir kapsayıcı yığınından oluşturmak için kullanın.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_stack_construct.cpp   
// compile with: /clr   
#include <cliext/stack>   
#include <cliext/vector>   
  
typedef cliext::stack<wchar_t> Mystack;   
typedef cliext::vector<wchar_t> Myvector;   
typedef cliext::stack<wchar_t, Myvector> Mystack_vec;   
int main()   
    {   
// construct an empty container   
    Mystack c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// construct from an underlying container   
    Myvector v2(5, L'x');   
    Mystack_vec c2(v2);       
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Mystack_vec c3(c2);   
    for each (wchar_t elem in c3.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container through handle   
    Mystack_vec c4(%c2);   
    for each (wchar_t elem in c4.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
size() = 0  
 x x x x x  
 x x x x x  
 x x x x x  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/stack >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yığın (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [Stack::Assign (STL/CLR)](../dotnet/stack-assign-stl-clr.md)   
 [Stack::generic_container (STL/CLR)](../dotnet/stack-generic-container-stl-clr.md)   
 [stack::operator= (STL/CLR)](../dotnet/stack-operator-assign-stl-clr.md)