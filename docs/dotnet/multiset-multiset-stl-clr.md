---
title: multiset::multiset (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::multiset::multiset
dev_langs:
- C++
helpviewer_keywords:
- multiset member [STL/CLR]
ms.assetid: a6ddb2df-d7cd-4b12-aee7-81da1f67f57f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f890a7051d6764f2168c5d90859219fb3513031e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="multisetmultiset-stlclr"></a>multiset::multiset (STL/CLR)
Bir kapsayıcı nesnesi oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
multiset();  
explicit multiset(key_compare^ pred);  
multiset(multiset<Key>% right);  
multiset(multiset<Key>^ right);  
template<typename InIter>  
    multisetmultiset(InIter first, InIter last);  
template<typename InIter>  
    multiset(InIter first, InIter last,  
        key_compare^ pred);  
multiset(System::Collections::Generic::IEnumerable<GValue>^ right);  
multiset(System::Collections::Generic::IEnumerable<GValue>^ right,  
    key_compare^ pred);  
```  
  
#### <a name="parameters"></a>Parametreler  
 ilk  
 Eklenecek Aralık başlangıcı.  
  
 Son  
 Eklenecek aralık sonu.  
  
 Pred  
 Denetimli sırası için koşulu sıralaması.  
  
 sağ  
 Nesne veya eklemek için aralık.  
  
## <a name="remarks"></a>Açıklamalar  
 Oluşturucusu:  
  
 `multiset();`  
  
 hiçbir öğe ile denetlenen dizisi koşulu sıralama varsayılan başlatır `key_compare()`. Bir boş ilk denetlenen dizisi koşulu sıralama varsayılan belirtmek için kullanın.  
  
 Oluşturucusu:  
  
 `explicit multiset(key_compare^ pred);`  
  
 sıralama koşulu ile hiçbir öğe ile denetlenen dizisi başlatır `pred`. Bir boş ilk denetlenen sıra ile belirtilen sıralama koşulu belirtmek için kullanın.  
  
 Oluşturucusu:  
  
 `multiset(multiset<Key>% right);`  
  
 denetimli dizisi dizisiyle başlatır [`right.begin()`, `right.end()`), koşulu sıralama varsayılan. Çok kümeli nesne tarafından denetlenen sırasının bir kopyasını bir ilk denetlenen sırası belirtmek için kullandığınız `right`, koşulu sıralama varsayılan.  
  
 Oluşturucusu:  
  
 `multiset(multiset<Key>^ right);`  
  
 denetimli dizisi dizisiyle başlatır [`right->begin()`, `right->end()`), koşulu sıralama varsayılan. Çok kümeli nesne tarafından denetlenen sırasının bir kopyasını bir ilk denetlenen sırası belirtmek için kullandığınız `right`, koşulu sıralama varsayılan.  
  
 Oluşturucusu:  
  
 `template<typename InIter> multiset(InIter first, InIter last);`  
  
 denetimli dizisi dizisiyle başlatır [`first`, `last`), koşulu sıralama varsayılan. Denetimli sırası başka bir dizi koşul sıralama varsayılan kopyası için kullanın.  
  
 Oluşturucusu:  
  
 `template<typename InIter> multiset(InIter first, InIter last, key_compare^ pred);`  
  
 denetimli dizisi dizisiyle başlatır [`first`, `last`), sıralama koşulu ile `pred`. Denetimli sırası belirtilen sıralama koşulu ile başka bir dizi bir kopya yapmak için kullanın.  
  
 Oluşturucusu:  
  
 `multiset(System::Collections::Generic::IEnumerable<Key>^ right);`  
  
 Numaralandırıcı tarafından belirtilen sıra ile denetlenen dizisi başlatır `right`, koşulu sıralama varsayılan. Denetimli sırası başka bir dizi koşul sıralama varsayılan bir numaralandırıcı tarafından açıklanan bir kopya yapmak için kullanın.  
  
 Oluşturucusu:  
  
 `multiset(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred);`  
  
 Numaralandırıcı tarafından belirtilen sıra ile denetlenen dizisi başlatır `right`, sıralama koşulu ile `pred`. Denetimli sırası belirtilen sıralama koşulu ile bir numaralandırıcı tarafından açıklanan başka bir dizi bir kopya yapmak için kullanın.  
  
## <a name="example"></a>Örnek  
  
```cpp  
// cliext_multiset_construct.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
// construct an empty container   
    Mymultiset c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule   
    Mymultiset c2 = cliext::greater_equal<wchar_t>();   
    System::Console::WriteLine("size() = {0}", c2.size());   
  
    c2.insert(c1.begin(), c1.end());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    Mymultiset c3(c1.begin(), c1.end());   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule   
    Mymultiset c4(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>());   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    Mymultiset c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule   
    Mymultiset c6(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3,   
            cliext::greater_equal<wchar_t>());   
    for each (wchar_t elem in c6)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct from a generic container   
    Mymultiset c7(c4);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Mymultiset c8(%c3);   
    for each (wchar_t elem in c8)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
size() = 0  
 a b c  
size() = 0  
 c b a  
 a b c  
 c b a  
 a b c  
 c b a  
 c b a  
 a b c  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/kümesi >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [multiset (STL/CLR)](../dotnet/multiset-stl-clr.md)   
 [multiset::generic_container (STL/CLR)](../dotnet/multiset-generic-container-stl-clr.md)   
 [multiset::operator= (STL/CLR)](../dotnet/multiset-operator-assign-stl-clr.md)