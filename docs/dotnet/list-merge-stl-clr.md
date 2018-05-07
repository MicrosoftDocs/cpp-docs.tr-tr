---
title: List::Merge (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::list::merge
dev_langs:
- C++
helpviewer_keywords:
- merge member [STL/CLR]
ms.assetid: f8e93cd3-bd08-4086-859b-08a2899cc9a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: ff5ba18dea3b33d1cf3a50dedfc5e90055e69c3e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="listmerge-stlclr"></a>list::merge (STL/CLR)
İki denetimli sıraları sıralı birleştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void merge(list<Value>% right);  
template<typename Pred2>  
    void merge(list<Value>% right, Pred2 pred);  
```  
  
#### <a name="parameters"></a>Parametreler  
 Pred  
 Karşılaştırıcı öğesi çiftleri için.  
  
 sağ  
 Birleştirmeye kapsayıcı.  
  
## <a name="remarks"></a>Açıklamalar  
 İlk üye fonksiyonu tarafından denetlenen dizisi tüm öğeleri kaldırır `right` ve denetlenen sırayla ekleyin. Her iki dizileri tarafından daha önce sıralanmalıdır `operator<` --öğeleri gerekir azaltamazsınız değerinde ya da dizisi ilerledikçe. Sonuçta elde edilen dizisi de göre sıralanmış `operator<`. Bu üye işlevi de değerinde artırır dizisi içine değerindeki artış iki sıraları birleştirmek için kullanın.  
  
 Dizileri göre sıralanmış dışında ikinci üye işlevi aynı ilk olarak davranır `pred`  --  `pred(X, Y)` herhangi bir öğe için false olarak `X` öğesi izleyen `Y` dizisindeki. Bir koşul işlevi veya belirttiğiniz temsilci göre sıralanmış iki sıraları birleştirmek için kullanın.  
  
 Hem işlevleri kararlı bir birleştirme--birini kullanarak özgün denetimli sıraları hiçbir çiftlerini elde edilen denetimli sırayla tersine. Ayrıca, çiftlerini varsa `X` ve `Y` eşdeğer sıralama--elde edilen denetimli sırayla sahip `!(X < Y) && !(X < Y)` --öğenin özgün denetimli serisinden tarafındandenetlenensırasındanöncebiröğegörünür`right`.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_list_merge.cpp   
// compile with: /clr   
#include <cliext/list>   
  
typedef cliext::list<wchar_t> Mylist;   
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'c');   
    c1.push_back(L'e');   
  
// display initial contents " a c e"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    cliext::list<wchar_t> c2;   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
    c2.push_back(L'f');   
  
// display initial contents " b d f"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// merge and display   
    cliext::list<wchar_t> c3(c1);   
    c3.merge(c2);   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("c2.size() = {0}", c2.size());   
  
// sort descending, merge descending, and redisplay   
    c1.sort(cliext::greater<wchar_t>());   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    c3.sort(cliext::greater<wchar_t>());   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    c3.merge(c1, cliext::greater<wchar_t>());   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("c1.size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 a c e  
 b d f  
 a b c d e f  
c2.size() = 0  
 e c a  
 f e d c b a  
 f e e d c c b a a  
c1.size() = 0  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/listesi >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Liste (STL/CLR)](../dotnet/list-stl-clr.md)   
 [List::sort (STL/CLR)](../dotnet/list-sort-stl-clr.md)   
 [list::splice (STL/CLR)](../dotnet/list-splice-stl-clr.md)