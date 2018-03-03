---
title: deque::Assign (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::deque::assign
dev_langs:
- C++
helpviewer_keywords:
- assign member [STL/CLR]
ms.assetid: 03fafdbb-6b10-4464-b3dc-0cc5cb8ac980
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 1ae8bb7a21a336987d30cb41a7a1ff9d586db830
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="dequeassign-stlclr"></a>deque::assign (STL/CLR)
Tüm öğeleri değiştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void assign(size_type count, value_type val);  
template<typename InIt>  
    void assign(InIt first, InIt last);  
void assign(System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `count`  
 Eklenecek öğe sayısı.  
  
 `first`  
 Eklenecek Aralık başlangıcı.  
  
 `last`  
 Eklenecek aralık sonu.  
  
 `right`  
 Eklenecek numaralandırması.  
  
 `val`  
 Eklenecek öğenin değeri.  
  
## <a name="remarks"></a>Açıklamalar  
 İlk üye işlevi denetimli dizisi ile yinelenmesinin değiştirir `count` değerinin öğeleri `val`. Kapsayıcı öğeler ile doldurmak için tüm aynı değere sahip kullanırsınız.  
  
 Varsa `InIt` bir tamsayı türünde ikinci üye işlevi aynı şekilde davranır `assign((size_type)first, (value_type)last)`. Aksi takdirde, denetlenen dizisi dizisiyle yerini [`first`, `last`). Denetimli bir kopyasını sıra yapmak için başka bir sıra kullanırsınız.  
  
 Numaralandırıcı tarafından belirtilen sıra ile denetlenen dizisi üçüncü üye işlevi değiştirir `right`. Denetimli sırası bir numaralandırıcı tarafından tanımlanan bir dizi bir kopya yapmak için kullanın.  
  
## <a name="example"></a>Örnek  
  
```cpp  
// cliext_deque_assign.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// assign a repetition of values   
    cliext::deque<wchar_t> c2;   
    c2.assign(6, L'x');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign an iterator range   
    c2.assign(c1.begin(), c1.end() - 1);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign an enumeration   
    c2.assign(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
x x x x x x  
a b  
a b c  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/deque >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [operator= (deque) (STL/CLR)](../dotnet/operator-assign-deque-stl-clr.md)