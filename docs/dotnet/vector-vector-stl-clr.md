---
title: Vector::Vector (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::vector::vector
dev_langs: C++
helpviewer_keywords: vector member [STL/CLR]
ms.assetid: a0b5e807-1ef2-422b-b772-1f96cd62fb51
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a321e18c9fc921e1d88961b4f282c29917fa7962
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="vectorvector-stlclr"></a>vector::vector (STL/CLR)
Bir kapsayıcı nesnesi oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
vector();  
vector(vector<Value>% right);  
vector(vector<Value>^ right);  
explicit vector(size_type count);  
vector(size_type count, value_type val);  
template<typename InIt>  
    vector(InIt first, InIt last);  
vector(System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 count  
 Eklenecek öğe sayısı.  
  
 ilk  
 Eklenecek Aralık başlangıcı.  
  
 Son  
 Eklenecek aralık sonu.  
  
 sağ  
 Nesne veya eklemek için aralık.  
  
 VAL  
 Eklenecek öğenin değeri.  
  
## <a name="remarks"></a>Açıklamalar  
 Oluşturucusu:  
  
 `vector();`  
  
 denetimli sıralı öğe ile başlatır. Boş bir başlangıç denetimli dizisini belirtmek için kullanın.  
  
 Oluşturucusu:  
  
 `vector(vector<Value>% right);`  
  
 denetimli dizisi dizisiyle başlatır [`right.begin()`, `right.end()`). Vektör nesnesi tarafından denetlenen sırasının bir kopyasını bir ilk denetlenen sırası belirtmek için kullandığınız `right`.  
  
 Oluşturucusu:  
  
 `vector(vector<Value>^ right);`  
  
 denetimli dizisi dizisiyle başlatır [`right->begin()`, `right->end()`). Bir kopyasını, tanıtıcısı vektör nesnesi tarafından denetlenen sırası olan ilk denetimli bir sıra belirtmek için kullandığınız `right`.  
  
 Oluşturucusu:  
  
 `explicit vector(size_type count);`  
  
 denetimli dizisiyle başlatır `count` öğeleriyle her değer `value_type()`. Kapsayıcı öğeler ile doldurmak için varsayılan değer tüm sahip kullanırsınız.  
  
 Oluşturucusu:  
  
 `vector(size_type count, value_type val);`  
  
 denetimli dizisiyle başlatır `count` öğeleriyle her değer `val`. Kapsayıcı öğeler ile doldurmak için tüm aynı değere sahip kullanırsınız.  
  
 Oluşturucusu:  
  
 `template<typename InIt>`  
  
 `vector(InIt first, InIt last);`  
  
 denetimli dizisi dizisiyle başlatır [`first`, `last`). Denetimli sırası başka bir dizi bir kopya yapmak için kullanın.  
  
 Oluşturucusu:  
  
 `vector(System::Collections::Generic::IEnumerable<Value>^ right);`  
  
 Numaralandırıcı tarafından belirtilen sıra ile denetlenen dizisi başlatır `right`. Denetimli sırası bir numaralandırıcı tarafından açıklanan başka bir dizi bir kopya yapmak için kullanın.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_vector_construct.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
// construct an empty container   
    cliext::vector<wchar_t> c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// construct with a repetition of default values   
    cliext::vector<wchar_t> c2(3);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", (int)elem);   
    System::Console::WriteLine();   
  
// construct with a repetition of values   
    cliext::vector<wchar_t> c3(6, L'x');   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    cliext::vector<wchar_t>::iterator it = c3.end();   
    cliext::vector<wchar_t> c4(c3.begin(), --it);   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    cliext::vector<wchar_t> c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    cliext::vector<wchar_t> c7(c3);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    cliext::vector<wchar_t> c8(%c3);   
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
 **Başlık:** \<cliext/vektör >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [vektör (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [Vector::Assign (STL/CLR)](../dotnet/vector-assign-stl-clr.md)   
 [Vector::generic_container (STL/CLR)](../dotnet/vector-generic-container-stl-clr.md)   
 [vector::operator= (STL/CLR)](../dotnet/vector-operator-assign-stl-clr.md)