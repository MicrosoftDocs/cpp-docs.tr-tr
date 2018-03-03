---
title: Range-based for deyimi (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 5750ba1d-ba48-4236-a923-e32de8345c2d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 43ded324227878b44f997e6539e060145ad0fb66
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="range-based-for-statement-c"></a>Range-based for Deyimi (C++)
`statement` içindeki her öğe için `expression` öğesini tekrar tekrar ve sırayla yürütür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      for ( for-range-declaration : expression )  
   statement   
```  
  
## <a name="remarks"></a>Açıklamalar  
 Aralık tabanlı kullanmak `for` "aracılığıyla yineleyebilirsiniz herhangi bir şey olarak tanımlanan bir aralığı" aracılığıyla yürütülmelidir döngüler oluşturmak için deyimi — Örneğin, `std::vector`, ya da, aralık tarafındantanımlanandiğerC++StandartKitaplığısırası`begin()` ve `end()`. `for-range-declaration` bölümünde bildirilen ad, `for` deyimi için yereldir ve `expression` veya `statement` içinde yeniden bildirilemez. Unutmayın [otomatik](../cpp/auto-cpp.md) anahtar sözcüğü tercih `for-range-declaration` deyim bölümü. 

 **Yeni Visual Studio 2017:** aralık tabanlı için begin() ve end() aynı türde nesneler döndürmeye döngüler artık gerek yoktur. Bu gibi aralıkları V3 teklifinde tanımlanan aralıkları tarafından kullanılan bir sentinel nesnesi döndürmek end() sağlar. Daha fazla bilgi için bkz: [Range-Based genelleme döngü için](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0184r0.html) ve [aralığı v3 kitaplığı github'da](https://github.com/ericniebler/range-v3).
  
 Bu kod aralık esaslı nasıl kullanılacağını gösterir. `for` bir dizi ve vektör aracılığıyla yinelemek için döngüler:  
  
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
  
 `1 2 3 4 5 6 7 8 9 10`  
  
 `1 2 3 4 5 6 7 8 9 10`  
  
 `1 2 3 4 5 6 7 8 9 10`  
  
 `1 2 3 4 5 6 7 8 9 10`  
  
 `end of integer array test`  
  
 `0.14159 1.14159 2.14159 3.14159 4.14159 5.14159 6.14159 7.14159 8.14159 9.14159`  
  
 `end of vector test`  
  
 Aralık tabanlı `for` döngü sonlandırır bunlardan biri ile `statement` yürütülür: bir [sonu](../cpp/break-statement-cpp.md), [dönmek](../cpp/return-statement-cpp.md), veya [goto](../cpp/goto-statement-cpp.md) dışında etiketli deyimi Aralık tabanlı **için** döngü. A [devam](../cpp/continue-statement-cpp.md) aralık tabanlı deyiminde `for` döngü yalnızca geçerli yinelemeye sonlandırır.  
  
 Aralık tabanlı `for` ile ilgili bu bilgileri unutmayın:  
  
-   Dizileri otomatik olarak tanır.  
  
-   `.begin()` ve `.end()` öğelerine sahip kapsayıcıları tanır.  
  
-   Diğer her şey için `begin()` ve `end()` bağımsız değişkene bağımlı aramayı kullanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Otomatik](../cpp/auto-cpp.md)   
 [Yineleme deyimleri](../cpp/iteration-statements-cpp.md)   
 [Anahtar sözcükler](../cpp/keywords-cpp.md)   
 [while deyimi (C++)](../cpp/while-statement-cpp.md)   
 [yapın-while deyimi (C++)](../cpp/do-while-statement-cpp.md)   
 [for Deyimi (C++)](../cpp/for-statement-cpp.md)