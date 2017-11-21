---
title: priority_queue::priority_queue (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::priority_queue::priority_queue
dev_langs: C++
helpviewer_keywords: priority_queue member [STL/CLR]
ms.assetid: aab423d7-959e-48fd-9028-e9f45f43cb8a
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 77486fdadaafe9b98e93998b73a4f5eb42f7865b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="priorityqueuepriorityqueue-stlclr"></a>priority_queue::priority_queue (STL/CLR)
Bir kapsayıcı bağdaştırıcısı nesnesi oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
priority_queue();  
priority_queue(priority_queue<Value, Container> right);  
priority_queue(priority_queue<Value, Container> right);  
explicit priority_queue(value_compare^ pred);  
priority_queue(value_compare^ pred, container_type% cont);  
template<typename InIt>  
    priority_queue(InIt first, InIt last);  
template<typename InIt>  
    priority_queue(InIt first, InIt last,  
        value_compare^ pred);  
template<typename InIt>  
    priority_queue(InIt first, InIt last,  
        value_compare^ pred, container_type% cont);  
```  
  
#### <a name="parameters"></a>Parametreler  
 devamı  
 Kopyalamak için kapsayıcı.  
  
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
  
 `priority_queue();`  
  
 boş bir Sarmalanan kapsayıcı koşulu sıralama varsayılan oluşturur. Bir boş ilk denetlenen dizisi koşulu sıralama varsayılan belirtmek için kullanın.  
  
 Oluşturucusu:  
  
 `priority_queue(priority_queue<Value, Container>% right);`  
  
 bir kopyası Sarmalanan bir kapsayıcı oluşturur `right.get_container()`, sıralama koşulu ile `right.value_comp()`. Sıra nesnesi tarafından denetlenen sırasının bir kopyasını bir ilk denetlenen sırası belirtmek için kullandığınız `right`, aynı sıralama koşulu ile.  
  
 Oluşturucusu:  
  
 `priority_queue(priority_queue<Value, Container>^ right);`  
  
 bir kopyası Sarmalanan bir kapsayıcı oluşturur `right->get_container()`, sıralama koşulu ile `right->value_comp()`. Sıra nesnesi tarafından denetlenen sırasının bir kopyasını bir ilk denetlenen sırası belirtmek için kullandığınız `*right`, aynı sıralama koşulu ile.  
  
 Oluşturucusu:  
  
 `explicit priority_queue(value_compare^ pred);`  
  
 boş bir Sarmalanan kapsayıcı sıralama koşulu ile oluşturur `pred`. Bir boş ilk denetlenen sıra ile belirtilen sıralama koşulu belirtmek için kullanın.  
  
 Oluşturucusu:  
  
 `priority_queue(value_compare^ pred, container_type cont);`  
  
 boş bir Sarmalanan kapsayıcı sıralama koşulu ile oluşturur `pred`, tüm öğeleri iter `cont` var olan bir kapsayıcıyı ilk denetlenen dizisinden ile belirtilen sıralama koşulu belirtmek için kullanın.  
  
 Oluşturucusu:  
  
 `template<typename InIt> priority_queue(InIt first, InIt last);`  
  
 boş bir Sarmalanan kapsayıcı varsayılan sıralama koşulu ile oluşturur, ardından dizisi iter [`first`, `last`). Belirtilen sıralama koşulu ile denetlenen dizisinden ilk belirtilen eqeuence belirtmek için kullanın.  
  
 Oluşturucusu:  
  
 `template<typename InIt> priority_queue(InIt first, InIt last, value_compare^ pred);`  
  
 boş bir Sarmalanan kapsayıcı sıralama koşulu ile oluşturur `pred`, dizisi iter [`first`, `last`). Belirtilen sıralama koşulu ile denetlenen dizisinden ilk belirtilen seqeuence belirtmek için kullanın.  
  
 Oluşturucusu:  
  
 `template<typename InIt> priority_queue(InIt first, InIt last, value_compare^ pred, container_type% cont);`  
  
 boş bir Sarmalanan kapsayıcı sıralama koşulu ile oluşturur `pred`, tüm öğeleri iter `cont` dizisi artı [`first`, `last`). Belirtilen sıralama koşulu ile ilk denetlenen dizisi var olan bir kapsayıcı ve belirtilen seqeuence belirtmek için kullanın.  
  
## <a name="example"></a>Örnek  
  
```cpp  
// cliext_priority_queue_construct.cpp   
// compile with: /clr   
#include <cliext/queue>   
#include <cliext/deque>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
typedef cliext::deque<wchar_t> Mydeque;   
int main()   
    {   
// construct an empty container   
    Mypriority_queue c1;   
    Mypriority_queue::container_type^ wc1 = c1.get_container();   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
    for each (wchar_t elem in wc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule   
    Mypriority_queue c2 = cliext::greater<wchar_t>();   
    System::Console::WriteLine("size() = {0}", c2.size());   
  
    for each (wchar_t elem in wc1)   
        c2.push(elem);   
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule by copying an underlying container   
    Mypriority_queue c2x =   
        gcnew Mypriority_queue(cliext::greater<wchar_t>(), *wc1);   
   for each (wchar_t elem in c2x.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    Mypriority_queue c3(wc1->begin(), wc1->end());   
    for each (wchar_t elem in c3.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule   
    Mypriority_queue c4(wc1->begin(), wc1->end(),   
        cliext::greater<wchar_t>());   
    for each (wchar_t elem in c4.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range, another container, and an ordering rule   
    Mypriority_queue c5(wc1->begin(), wc1->end(),   
        cliext::greater<wchar_t>(), *wc1);   
    for each (wchar_t elem in c5.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct from a generic container   
    Mypriority_queue c6(c3);   
    for each (wchar_t elem in c6.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Mypriority_queue c7(%c3);   
    for each (wchar_t elem in c7.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule, by copying an underlying container   
    Mypriority_queue c8 =   
        gcnew Mypriority_queue(cliext::greater<wchar_t>(), *wc1);   
    for each (wchar_t elem in c8.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
```Output  
size() = 0  
 c a b  
size() = 0  
 a c b  
 a c b  
 c a b  
 a c b  
 a a b c c b  
 c a b  
 c a b  
 a c b  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/kuyruk >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [priority_queue::Assign (STL/CLR)](../dotnet/priority-queue-assign-stl-clr.md)   
 [priority_queue::generic_container (STL/CLR)](../dotnet/priority-queue-generic-container-stl-clr.md)   
 [priority_queue::operator (STL/CLR) =](../dotnet/priority-queue-operator-assign-stl-clr.md)