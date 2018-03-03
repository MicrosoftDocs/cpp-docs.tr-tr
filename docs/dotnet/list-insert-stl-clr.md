---
title: List::insert (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::list::insert
dev_langs:
- C++
helpviewer_keywords:
- insert member [STL/CLR]
ms.assetid: 399ed30f-6b76-41a8-b180-6070e3ca1c68
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: ca57eb33999754dc44df0f49cf1089e137fd2d1d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="listinsert-stlclr"></a>list::insert (STL/CLR)
Öğeleri belirtilen bir konumda ekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
iterator insert(iterator where, value_type val);  
void insert(iterator where, size_type count, value_type val);  
template<typename InIt>  
    void insert(iterator where, InIt first, InIt last);  
void insert(iterator where,  
    System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 count  
 Eklenecek öğe sayısı.  
  
 ilk  
 Eklenecek Aralık başlangıcı.  
  
 Son  
 Eklenecek aralık sonu.  
  
 sağ  
 Eklenecek numaralandırması.  
  
 VAL  
 Eklenecek öğenin değeri.  
  
 Burada  
 Önce eklemek için kapsayıcı WHERE.  
  
## <a name="remarks"></a>Açıklamalar  
 Her üyesinin gösterdiği öğesinden önce ekler işlevleri `where` denetimli sırayla bir dizi belirtilen tarafından kalan işlenen.  
  
 İlk üye işlevi değeri olan bir öğe ekler `val` ve yeni eklenen öğesi atayan bir yineleyici döndürür. Yineleyici tarafından atanan bir yerde önce tek bir öğe eklemek için kullanın.  
  
 İkinci üye işlevi bir yinelenmesinin ekler `count` değerinin öğeleri `val`. Tüm kopyalarını aynı değeri olan sıfır veya daha fazla bitişik öğe eklemek için kullanın.  
  
 Varsa `InIt` bir tamsayı türü üçüncü üye işlevi aynı şekilde davranır `insert(where, (size_type)first, (value_type)last)`. Aksi takdirde dizisi ekler [`first`, `last`). Başka bir sırasından kopyalanan sıfır veya daha fazla bitişik öğe eklemek için kullanın.  
  
 Dördüncü üye fonksiyonu tarafından belirlenen dizisi ekler `right`. Bir numaralandırıcı tarafından tanımlanan bir dizi eklemek için kullanın.  
  
 Tek bir öğe ekleme yaparken öğesi kopya ekleme noktasını bitişinde yakın arasındaki öğelerin sayısı doğrusal sayısıdır. (Bir veya daha fazla öğe sırası ya da sonunda eklerken, hiçbir öğe kopya gerçekleşir.) Varsa `InIt` giriş yineleyici olan üçüncü üye işlevi dizideki her öğe için tek bir ekleme etkili bir şekilde gerçekleştirir. Aksi takdirde eklerken `N` öğeleri öğesi kopya sayısı doğrusal olarak `N` ekleme noktasını bitişinde yakın arasındaki öğelerin sayısı artı.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_list_insert.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value using iterator   
    cliext::list<wchar_t>::iterator it = c1.begin();   
    System::Console::WriteLine("insert(begin()+1, L'x') = {0}",   
        *c1.insert(++it, L'x'));   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a repetition of values   
    cliext::list<wchar_t> c2;   
    c2.insert(c2.begin(), 2, L'y');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an iterator range   
    it = c1.end();   
    c2.insert(c2.end(), c1.begin(), --it);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an enumeration   
    c2.insert(c2.begin(),   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value using index   
    it = c2.begin();   
    ++it, ++it, ++it;   
    c2.insert(it, L'z');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
insert(begin()+1, L'x') = x  
 a x b c  
 y y  
 y y a x b  
 a x b c y y a x b  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/listesi >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Liste (STL/CLR)](../dotnet/list-stl-clr.md)   
 [list::assign (STL/CLR)](../dotnet/list-assign-stl-clr.md)