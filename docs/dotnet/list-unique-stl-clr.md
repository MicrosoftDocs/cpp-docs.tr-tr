---
title: List::Unique (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::list::unique
dev_langs: C++
helpviewer_keywords: unique member [STL/CLR]
ms.assetid: c3a29e4e-0ec1-4472-b050-7a9511037132
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ca78fcc1de8b579a647dd9080dc64db0fde54e9b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="listunique-stlclr"></a>list::unique (STL/CLR)
Belirtilen bir sınamadan bitişik öğeleri kaldırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void unique();  
template<typename Pred2>  
    void unique(Pred2 pred);  
```  
  
#### <a name="parameters"></a>Parametreler  
 Pred  
 Karşılaştırıcı öğesi çiftleri için.  
  
## <a name="remarks"></a>Açıklamalar  
 İlk üye işlevi (siler) denetimli sırasından kaldırır karşılaştırır her öğe varsa, önceki öğesine--eşit öğesi `X` öğesi önündeki `Y` ve `X == Y`, üye fonksiyonu kaldırır `Y`. Bitişik öğelerinin her değişkene biri hariç tüm kopyasını kaldırmak için bu karşılaştırma eşittir kullanırsınız. Unutmayın denetimli dizisi sipariş edilen, gibi çağırarak gibi [list::sort (STL/CLR)](../dotnet/list-sort-stl-clr.md)`()`, üye işlevi yalnızca öğeler benzersiz değerlerle bırakır. (Bu nedenle adı).  
  
 Her öğeyi kaldırır ancak bu ikinci üye işlevi, birinci ile aynı şekilde davranır `Y` öğenin aşağıdaki `X` kendisi için `pred(X, Y)`. Koşul işlevi veya belirttiğiniz temsilci bitişik öğelerinin her değişkene biri hariç tüm kopyasını kaldırmak için kullanın. Unutmayın denetimli dizisi sipariş edilen, gibi çağırarak gibi `sort(pred)`, eşdeğer diğer öğelerle sıralama olmayan öğeler üye fonksiyonu bırakır.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_list_unique.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display contents after unique   
    cliext::list<wchar_t> c2(c1);   
    c2.unique();   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display contents after unique(not_equal_to)   
    c2 = c1;   
    c2.unique(cliext::not_equal_to<wchar_t>());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a a b c  
a b c  
a a  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/listesi >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Liste (STL/CLR)](../dotnet/list-stl-clr.md)   
 [List::Remove (STL/CLR)](../dotnet/list-remove-stl-clr.md)   
 [List::remove_if (STL/CLR)](../dotnet/list-remove-if-stl-clr.md)   
 [List::sort (STL/CLR)](../dotnet/list-sort-stl-clr.md)