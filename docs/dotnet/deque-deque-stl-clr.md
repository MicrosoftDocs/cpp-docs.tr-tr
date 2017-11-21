---
title: deque::deque (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::deque::deque
dev_langs: C++
helpviewer_keywords: deque member [STL/CLR]
ms.assetid: e5bc9511-619e-469c-b50a-e06858e7fce7
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: fc08403d0d8cf7875700ca539a3e68a0ed788104
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="dequedeque-stlclr"></a>deque::deque (STL/CLR)
Bir kapsayıcı nesnesi oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
deque();  
deque(deque<Value>% right);  
deque(deque<Value>^ right);  
explicit deque(size_type count);  
deque(size_type count, value_type val);  
template<typename InIt>  
    deque(InIt first, InIt last);  
deque(System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `count`  
 Eklenecek öğe sayısı.  
  
 `first`  
 Eklenecek Aralık başlangıcı.  
  
 `last`  
 Eklenecek aralık sonu.  
  
 `right`  
 Nesne veya eklemek için aralık.  
  
 `val`  
 Eklenecek öğenin değeri.  
  
## <a name="remarks"></a>Açıklamalar  
 Oluşturucusu:  
  
 `deque();`  
  
 denetimli sıralı öğe ile başlatır. Boş bir başlangıç denetimli dizisini belirtmek için kullanın.  
  
 Oluşturucusu:  
  
 `deque(deque<Value>% right);`  
  
 denetimli dizisi dizisiyle başlatır [`right.begin()`, `right.end()`). Deque nesne tarafından denetlenen sırasının bir kopyasını bir ilk denetlenen sırası belirtmek için kullandığınız `right`. Yineleyiciler hakkında daha fazla bilgi için bkz: [deque::begin (STL/CLR)](../dotnet/deque-begin-stl-clr.md) ve [deque::end (STL/CLR)](../dotnet/deque-end-stl-clr.md).  
  
 Oluşturucusu:  
  
 `deque(deque<Value>^ right);`  
  
 denetimli dizisi dizisiyle başlatır [`right->begin()`, `right->end()`). Bir kopyasını, tanıtıcısı deque nesnesi tarafından denetlenen sırası olan ilk denetimli bir sıra belirtmek için kullandığınız `right`.  
  
 Oluşturucusu:  
  
 `explicit deque(size_type count);`  
  
 denetimli dizisiyle başlatır `count` öğeleriyle her değer `value_type()`. Kapsayıcı öğeler ile doldurmak için varsayılan değer tüm sahip kullanırsınız.  
  
 Oluşturucusu:  
  
 `deque(size_type count, value_type val);`  
  
 denetimli dizisiyle başlatır `count` öğeleriyle her değer `val`. Kapsayıcı öğeler ile doldurmak için tüm aynı değere sahip kullanırsınız.  
  
 Oluşturucusu:  
  
 `template<typename InIt>`  
  
 `deque(InIt first, InIt last);`  
  
 denetimli dizisi dizisiyle başlatır [`first`, `last`). Denetimli sırası başka bir dizi bir kopya yapmak için kullanın.  
  
 Oluşturucusu:  
  
 `deque(System::Collections::Generic::IEnumerable<Value>^ right);`  
  
 Numaralandırıcı tarafından belirtilen sıra ile denetlenen dizisi başlatır `right`. Denetimli sırası bir numaralandırıcı tarafından açıklanan başka bir dizi bir kopya yapmak için kullanın.  
  
## <a name="example"></a>Örnek  
  
```cpp  
// cliext_deque_construct.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
// construct an empty container   
    cliext::deque<wchar_t> c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// construct with a repetition of default values   
    cliext::deque<wchar_t> c2(3);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", (int)elem);   
    System::Console::WriteLine();   
  
// construct with a repetition of values   
    cliext::deque<wchar_t> c3(6, L'x');   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    cliext::deque<wchar_t>::iterator it = c3.end();   
    cliext::deque<wchar_t> c4(c3.begin(), --it);   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    cliext::deque<wchar_t> c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    cliext::deque<wchar_t> c7(c3);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    cliext::deque<wchar_t> c8(%c3);   
    for each (wchar_t elem in c8)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
```Output  
size() = 0  
 0 0 0  
 x x x x x x  
 x x x x x  
 x x x x x x  
 x x x x x x  
 x x x x x x  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/deque >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [deque::Assign (STL/CLR)](../dotnet/deque-assign-stl-clr.md)   
 [deque::generic_container (STL/CLR)](../dotnet/deque-generic-container-stl-clr.md)   
 [işleç = (deque) (STL/CLR)](../dotnet/operator-assign-deque-stl-clr.md)