---
title: Range-based for deyimi (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 5750ba1d-ba48-4236-a923-e32de8345c2d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0edf350289d04824dc2e06e4e11144a4f3141770
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39407039"
---
# <a name="range-based-for-statement-c"></a>Range-based for Deyimi (C++)
`statement` içindeki her öğe için `expression` öğesini tekrar tekrar ve sırayla yürütür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
for ( for-range-declaration : expression )  
   statement   
```  
  
## <a name="remarks"></a>Açıklamalar  
 Aralık tabanlı kullanın **için** "yinelemek herhangi bir şey olarak tanımlanan bir aralığı" ile yürütülmesi gereken döngüler oluşturmak için — örneğin, `std::vector`, tüm diğer C++ Standart Kitaplığı dizisi aralığı veya tarafından tanımlanan bir `begin()` ve `end()`. Bölümünde bildirilen ad `for-range-declaration` için yereldir **için** deyimi ve içinde yeniden bildirilemez `expression` veya `statement`. Unutmayın [otomatik](../cpp/auto-cpp.md) anahtar sözcüğünün tercih `for-range-declaration` deyiminin bölümü. 

 **Visual Studio 2017'te yeni eklendi:** aralık tabanlı const_iterator ve end() aynı türe ait nesneleri iade döngüler artık gereksinim için. Bu gibi aralıkları V3 teklife tanımlanan aralıkları tarafından kullanılan bir sentinel nesneyi döndürmek end() sağlar. Daha fazla bilgi için bkz [Genelleştiriliyor aralık tabanlı For döngüsü](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0184r0.html) ve [aralığı v3 kitaplığı github'da](https://github.com/ericniebler/range-v3).
  
 Bu kod aralık tabanlı nasıl kullanılacağını gösterir. **için** bir dizi ve vektör aracılığıyla yineleme yapmak için:  
  
```cpp  
// range-based-for.cpp  
// compile by using: cl /EHsc /nologo /W4  
#include <iostream>  
#include <vector>  
using namespace std;  
  
int main()   
{  
    // Basic 10-element integer array.  
    int x[10] = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };  
  
    // Range-based for loop to iterate through the array.  
    for( int y : x ) { // Access by value using a copy declared as a specific type.   
                       // Not preferred.  
        cout << y << " ";  
    }  
    cout << endl;  
  
    // The auto keyword causes type inference to be used. Preferred.  
  
    for( auto y : x ) { // Copy of 'x', almost always undesirable  
        cout << y << " ";  
    }  
    cout << endl;  
  
    for( auto &y : x ) { // Type inference by reference.  
        // Observes and/or modifies in-place. Preferred when modify is needed.  
        cout << y << " ";  
    }  
    cout << endl;  
  
    for( const auto &y : x ) { // Type inference by const reference.  
        // Observes in-place. Preferred when no modify is needed.  
        cout << y << " ";  
    }  
    cout << endl;  
    cout << "end of integer array test" << endl;  
    cout << endl;  
  
    // Create a vector object that contains 10 elements.  
    vector<double> v;  
    for (int i = 0; i < 10; ++i) {  
        v.push_back(i + 0.14159);  
    }  
  
    // Range-based for loop to iterate through the vector, observing in-place.  
    for( const auto &j : v ) {  
        cout << j << " ";  
    }  
    cout << endl;  
    cout << "end of vector test" << endl;  
}  
```  
  
 Çıktı bu şekildedir:  

```Output
 1 2 3 4 5 6 7 8 9 10  
  
 1 2 3 4 5 6 7 8 9 10  
  
 1 2 3 4 5 6 7 8 9 10  
  
 1 2 3 4 5 6 7 8 9 10  
  
 `end of integer array test`  
  
 `0.14159 1.14159 2.14159 3.14159 4.14159 5.14159 6.14159 7.14159 8.14159 9.14159`  
  
 `end of vector test`  
```

 Aralık tabanlı **için** döngüyü sonlandırır içinde bunlardan biri `statement` yürütülür: bir [sonu](../cpp/break-statement-cpp.md), [dönüş](../cpp/return-statement-cpp.md), veya [goto](../cpp/goto-statement-cpp.md) etiketli bir için Aralık tabanlı dışında'bir deyim **için** döngü. A [devam](../cpp/continue-statement-cpp.md) aralık tabanlı deyiminde **için** döngü yalnızca geçerli yinelemeyi sonlandırır.  
  
 Bu bilgiler hakkında aralık tabanlı aklınızda **için**:  
  
-   Dizileri otomatik olarak tanır.  
  
-   `.begin()` ve `.end()` öğelerine sahip kapsayıcıları tanır.  
  
-   Diğer her şey için `begin()` ve `end()` bağımsız değişkene bağımlı aramayı kullanır.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Otomatik](../cpp/auto-cpp.md)   
 [Yineleme deyimleri](../cpp/iteration-statements-cpp.md)   
 [anahtar sözcükler](../cpp/keywords-cpp.md)   
 [while deyimi (C++)](../cpp/while-statement-cpp.md)   
 [yapın-while deyimi (C++)](../cpp/do-while-statement-cpp.md)   
 [for Deyimi (C++)](../cpp/for-statement-cpp.md)