---
title: Range-based for Deyimi (C++)
ms.date: 11/04/2016
ms.assetid: 5750ba1d-ba48-4236-a923-e32de8345c2d
ms.openlocfilehash: af9811fd707d4dbc28158dba3b6b3fbfcc43e4fe
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80077179"
---
# <a name="range-based-for-statement-c"></a>Range-based for Deyimi (C++)

`statement` içindeki her öğe için `expression` öğesini tekrar tekrar ve sırayla yürütür.

## <a name="syntax"></a>Sözdizimi

```
for ( for-range-declaration : expression )
   statement
```

## <a name="remarks"></a>Açıklamalar

Aralık tabanlı **for** ifadesini kullanarak, tekrarlayabilmeniz gereken herhangi bir şey olarak tanımlanan bir "Aralık" aracılığıyla yürütülmesi gereken döngüler oluşturun — örneğin, `std::vector`veya aralığı bir `begin()` ve `end()`tarafından tanımlanan herhangi bir C++ standart kitaplık sırası. `for-range-declaration` bölümünde belirtilen ad, **for** deyimindeki yereldir ve `expression` veya `statement`içinde yeniden bildirilemez. [Otomatik](../cpp/auto-cpp.md) anahtar sözcüğünün deyimin `for-range-declaration` bölümünde tercih edildiğini unutmayın.

**Visual Studio 2017 ' de yeni:**  Aralık tabanlı for döngüleri artık Begin () ve End () öğesinin aynı türdeki nesneleri döndürmesini gerektirmez. Bu, End () ' in, Ranges-v3 teklifinde tanımlandığı şekilde aralıklar tarafından kullanılmak gibi bir Sentinel nesnesi döndürmesini sağlar. Daha fazla bilgi için bkz. [Aralık tabanlı for döngüsünü](https://wg21.link/p0184r0) ve [GitHub 'daki Range-v3 kitaplığını](https://github.com/ericniebler/range-v3)Genelleştirme.

Bu kod, bir dizi ve vektör aracılığıyla yinelemek **için Aralık tabanlı döngüleri nasıl** kullanacağınızı gösterir:

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

Aralık temelli bir **for** döngüsü `statement` yürütüldüğünde, bir Aralık tabanlı for döngüsü sona erer: Aralık tabanlı **for** döngüsü dışında etiketli bir ifadeye bir [Break](../cpp/break-statement-cpp.md), [Return](../cpp/return-statement-cpp.md)veya [goto](../cpp/goto-statement-cpp.md) . Aralık temelli bir **for** döngüsünde [Continue](../cpp/continue-statement-cpp.md) deyimleri yalnızca geçerli yinelemeyi sonlandırır.

Aralık tabanlı hakkında şu olguları göz önünde bulundurun **:**

- Dizileri otomatik olarak tanır.

- `.begin()` ve `.end()` öğelerine sahip kapsayıcıları tanır.

- Diğer her şey için `begin()` ve `end()` bağımsız değişkene bağımlı aramayı kullanır.

## <a name="see-also"></a>Ayrıca bkz.

[auto](../cpp/auto-cpp.md)<br/>
[Yineleme Deyimleri](../cpp/iteration-statements-cpp.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[while Deyimi (C++)](../cpp/while-statement-cpp.md)<br/>
[do-while Deyimi (C++)](../cpp/do-while-statement-cpp.md)<br/>
[for Deyimi (C++)](../cpp/for-statement-cpp.md)