---
title: Map::insert (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::map::insert
dev_langs:
- C++
helpviewer_keywords:
- insert member [STL/CLR]
ms.assetid: 599c702e-7db0-45b8-8247-4ff041a3639c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a06fa94e9752d72e8743d3a360ffd81bc9322db1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="mapinsert-stlclr"></a>map::insert (STL/CLR)
Öğeleri ekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
cliext::pair<iterator, bool> insert(value_type val);  
iterator insert(iterator where, value_type val);  
template<typename InIter>  
    void insert(InIter first, InIter last);  
void insert(System::Collections::Generic::IEnumerable<value_type>^ right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 ilk  
 Eklenecek Aralık başlangıcı.  
  
 Son  
 Eklenecek aralık sonu.  
  
 sağ  
 Eklenecek numaralandırması.  
  
 VAL  
 Eklenecek anahtar değeri.  
  
 Burada  
 WHERE (yalnızca ipucu) eklemek için kapsayıcı.  
  
## <a name="remarks"></a>Açıklamalar  
 Her üye işlevleri kalan işlenen tarafından belirtilen sıra ekler.  
  
 İlk üye işlevi endeavors değeri olan bir öğe eklemek `val`ve bir değer çifti döndürür `X`. Varsa `X.second` doğrudur `X.first` yeni eklenen öğesi belirler; Aksi takdirde `X.first` eşdeğer bir öğesiyle atar sıralama zaten var ve yeni bir öğesi eklenir. Tek bir öğe eklemek için kullanın.  
  
 İkinci üye işlevi değeri olan bir öğe ekler `val`kullanarak `where` (performansını artırmak için) bağlı olarak, bir ipucu olarak ve yeni eklenen öğesi atayan bir yineleyici döndürür. Bildiğiniz bir öğeye bitişik olabilecek tek bir öğe eklemek için kullanın.  
  
 Üçüncü üye işlevi dizisi ekler [`first`, `last`). Başka bir sırasından kopyalanan sıfır veya daha fazla öğe eklemek için kullanın.  
  
 Dördüncü üye fonksiyonu tarafından belirlenen dizisi ekler `right`. Bir numaralandırıcı tarafından tanımlanan bir dizi eklemek için kullanın.  
  
 Her öğe ekleme zaman öğe sayısını logaritmasını orantılı denetimli sırasını alır. Ekleme, bir öğe ekleme noktasını bitişik atayan bir ipucu verilen amortized sabit zamanında bir ancak ortaya çıkabilir.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_map_insert.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
typedef Mymap::pair_iter_bool Pairib;   
int main()   
    {   
    Mymap c1;   
    c1.insert(Mymap::make_value(L'a', 1));   
    c1.insert(Mymap::make_value(L'b', 2));   
    c1.insert(Mymap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert a single value, unique and duplicate   
// insert a single value, success and failure   
    Pairib pair1 = c1.insert(Mymap::make_value(L'x', 24));   
    System::Console::WriteLine("insert([L'x' 24]) = [[{0} {1}] {2}]",   
        pair1.first->first, pair1.first->second, pair1.second);   
  
    pair1 = c1.insert(Mymap::make_value(L'b', 2));   
    System::Console::WriteLine("insert([L'b' 2]) = [[{0} {1}] {2}]",   
        pair1.first->first, pair1.first->second, pair1.second);   
  
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert a single value with hint   
    Mymap::iterator it =   
        c1.insert(c1.begin(), Mymap::make_value(L'y', 25));   
    System::Console::WriteLine("insert(begin(), [L'y' 25]) = [{0} {1}]",   
        it->first, it->second);   
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert an iterator range   
    Mymap c2;   
    it = c1.end();   
    c2.insert(c1.begin(), --it);   
    for each (Mymap::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert an enumeration   
    Mymap c3;   
    c3.insert(   // NOTE: cast is not needed   
        (System::Collections::Generic::   
            IEnumerable<Mymap::value_type>^)%c1);   
    for each (Mymap::value_type elem in c3)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
insert([L'x' 24]) = [[x 24] True]  
insert([L'b' 2]) = [[b 2] False]  
 [a 1] [b 2] [c 3] [x 24]  
insert(begin(), [L'y' 25]) = [y 25]  
 [a 1] [b 2] [c 3] [x 24] [y 25]  
 [a 1] [b 2] [c 3] [x 24]  
 [a 1] [b 2] [c 3] [x 24] [y 25]  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/map >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [map (STL/CLR)](../dotnet/map-stl-clr.md)