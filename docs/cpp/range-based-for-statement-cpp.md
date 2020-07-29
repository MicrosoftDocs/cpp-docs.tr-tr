---
title: Range-based for Deyimi (C++)
ms.date: 11/04/2016
ms.assetid: 5750ba1d-ba48-4236-a923-e32de8345c2d
ms.openlocfilehash: 1197080e2e96e0e5c51bc06e93026567a33c7842
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223622"
---
# <a name="range-based-for-statement-c"></a>Range-based for Deyimi (C++)

`statement` içindeki her öğe için `expression` öğesini tekrar tekrar ve sırayla yürütür.

## <a name="syntax"></a>Sözdizimi

> **`for (`***for-Range-bildirimi* **`:`** *ifade***`)`**\
&emsp;*ifade*

## <a name="remarks"></a>Açıklamalar

Aralık tabanlı ifadeyi kullanarak, **`for`** tekrarlayabilmeniz gereken herhangi bir şey olarak tanımlanmış bir *Aralık*aracılığıyla yürütülmesi gereken döngüler oluşturun — örneğin, `std::vector` veya aralığı bir ve Ile tanımlanmış herhangi bir C++ standart kitaplık sırası `begin()` `end()` . Bölümünde bildirildiği ad, `for-range-declaration` deyimin yereldir **`for`** ve veya içinde yeniden bildirilemez `expression` `statement` . [`auto`](../cpp/auto-cpp.md)Anahtar sözcüğünün deyimin bölümünde tercih edildiğini unutmayın `for-range-declaration` .

**Visual Studio 2017 ' de yeni:**  Aralık tabanlı **`for`** döngüler artık bunu gerektirmez `begin()` ve `end()` aynı türdeki nesneleri döndürebilir. Bu `end()` , Ranges-v3 teklifinde tanımlandığı şekilde aralıklar tarafından kullanılan bir Sentinel nesnesi döndürmesini sağlar. Daha fazla bilgi için bkz. [Aralık tabanlı `For` döngüyü](https://wg21.link/p0184r0) ve [GitHub 'daki Range-v3 kitaplığını](https://github.com/ericniebler/range-v3)Genelleştirme.

Bu kod **`for`** , bir dizi ve vektör aracılığıyla yinelemek için Aralık tabanlı döngülerin nasıl kullanılacağını gösterir:

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

Çıktı şöyledir:

```Output
1 2 3 4 5 6 7 8 9 10
1 2 3 4 5 6 7 8 9 10
1 2 3 4 5 6 7 8 9 10
1 2 3 4 5 6 7 8 9 10
end of integer array test

0.14159 1.14159 2.14159 3.14159 4.14159 5.14159 6.14159 7.14159 8.14159 9.14159
end of vector test
```

Aralık temelli bir **`for`** döngü, bunlardan biri `statement` çalıştırıldığında sonlanır:,, [`break`](../cpp/break-statement-cpp.md) [`return`](../cpp/return-statement-cpp.md) veya [`goto`](../cpp/goto-statement-cpp.md) Aralık tabanlı döngü dışındaki etiketli bir ifadeye **`for`** . [`continue`](../cpp/continue-statement-cpp.md)Aralık tabanlı bir döngüdeki bir ifade **`for`** yalnızca geçerli yinelemeyi sonlandırır.

Aralık tabanlı hakkında bu olguları göz önünde bulundurun **`for`** :

- Dizileri otomatik olarak tanır.

- `.begin()` ve `.end()` öğelerine sahip kapsayıcıları tanır.

- Diğer her şey için `begin()` ve `end()` bağımsız değişkene bağımlı aramayı kullanır.

## <a name="see-also"></a>Ayrıca bkz.

[`auto`](../cpp/auto-cpp.md)<br/>
[Yineleme Deyimleri](../cpp/iteration-statements-cpp.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)<br/>
[`while`İfade (C++)](../cpp/while-statement-cpp.md)<br/>
[`do-while`İfade (C++)](../cpp/do-while-statement-cpp.md)<br/>
[`for`İfade (C++)](../cpp/for-statement-cpp.md)
