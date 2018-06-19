---
title: Stack::Stack (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::stack::stack
dev_langs:
- C++
helpviewer_keywords:
- stack member [STL/CLR]
ms.assetid: f1cfb3fe-4d22-41e5-906b-e8faa0bcde9b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e1ed49049a04f41e5a82ba7d25a52ce19c9a4898
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33169484"
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