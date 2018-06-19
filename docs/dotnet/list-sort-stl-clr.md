---
title: List::sort (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::list::sort
dev_langs:
- C++
helpviewer_keywords:
- sort member [STL/CLR]
ms.assetid: f811d5f4-a19e-4194-8765-1e68097c52f0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 670b18e5901ef264474256a1a1e57cde7a28ef01
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33138350"
---
# <a name="listsort-stlclr"></a>list::sort (STL/CLR)
Denetimli dizisi sıralar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void sort();  
template<typename Pred2>  
    void sort(Pred2 pred);  
```  
  
#### <a name="parameters"></a>Parametreler  
 Pred  
 Karşılaştırıcı öğesi çiftleri için.  
  
## <a name="remarks"></a>Açıklamalar  
 Böylece göre sıralanmış ilk üye işlevi denetlenen sıradaki öğeleri yeniden düzenler `operator<` --öğeleri azaltamazsınız değerinde dizisi ilerledikçe. Artan düzende dizisi sıralamak için bu üye işlevini kullanın.  
  
 Dizisi göre sıralanmış dışında ikinci üye işlevi, birinci ile aynı şekilde davranır `pred`  --  `pred(X, Y)` herhangi bir öğe için yanlış `X` öğesi izleyen `Y` sonuç dizisindeki. Sıralı bir koşul işlevi veya temsilci belirttiğiniz bir sırada sıralamak için kullanın.  
  
 Hem tutarlı bir sıralama işlevleri gerçekleştirmek--özgün denetlenen sıradaki hiçbir çiftlerini elde edilen denetimli sırayla tersine çevrildi.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_list_sort.cpp   
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
  
// sort descending and redisplay   
    c1.sort(cliext::greater<wchar_t>());   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// sort ascending and redisplay   
    c1.sort();   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
c b a  
a b c  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/listesi >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Liste (STL/CLR)](../dotnet/list-stl-clr.md)   
 [List::Merge (STL/CLR)](../dotnet/list-merge-stl-clr.md)   
 [List::reverse (STL/CLR)](../dotnet/list-reverse-stl-clr.md)   
 [List::splice (STL/CLR)](../dotnet/list-splice-stl-clr.md)   
 [list::unique (STL/CLR)](../dotnet/list-unique-stl-clr.md)