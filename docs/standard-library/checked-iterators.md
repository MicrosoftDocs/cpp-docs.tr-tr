---
title: Denetlenmiş Yineleyiciler
ms.date: 11/04/2016
f1_keywords:
- _SECURE_SCL_THROWS
helpviewer_keywords:
- Safe Libraries
- Safe Libraries, C++ Standard Library
- Safe C++ Standard Library
- iterators, checked
- checked iterators
ms.assetid: cfc87df8-e3d9-403b-ab78-e9483247d940
ms.openlocfilehash: 2327638208f30908cd3429ae656ce569f5821195
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2020
ms.locfileid: "90684909"
---
# <a name="checked-iterators"></a>Denetlenmiş Yineleyiciler

İşaretli yineleyiciler, kapsayıcınızın sınırlarının geçersiz kılınmamasını sağlar. Denetlenen yineleyiciler hem yayın yapıları hem de hata ayıklama yapıları için geçerlidir. Hata ayıklama modunda derlerken hata ayıklama yineleyiciler kullanma hakkında daha fazla bilgi için bkz. [hata ayıklama Yineleyici desteği](../standard-library/debug-iterator-support.md).

## <a name="remarks"></a>Açıklamalar

Denetlenen yineleyiciler tarafından oluşturulan uyarıların nasıl devre dışı bırakılacağı hakkında bilgi için bkz. [_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md).

Denetlenen yineleyiciler özelliğini etkinleştirmek veya devre dışı bırakmak için [ \_ Yineleyici \_ hata ayıklama \_ düzeyi](../standard-library/iterator-debug-level.md) önişlemci makrosunu kullanabilirsiniz. _ITERATOR_DEBUG_LEVEL 1 veya 2 olarak tanımlanırsa, yineleyicilerin güvenli olmayan kullanımı bir çalışma zamanı hatasına neden olur ve program sonlandırılır. 0 olarak tanımlanmışsa, işaretli yineleyiciler devre dışı bırakılır. Varsayılan olarak, _ITERATOR_DEBUG_LEVEL değeri yayın yapıları için 0 ve hata ayıklama yapıları için 2 ' dir.

> [!IMPORTANT]
> Daha eski belgeler ve kaynak kodu [_SECURE_SCL](../standard-library/secure-scl.md) makroya başvurabilir. _SECURE_SCL denetlemek için _ITERATOR_DEBUG_LEVEL kullanın. Daha fazla bilgi için bkz. [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md).

_ITERATOR_DEBUG_LEVEL 1 veya 2 olarak tanımlandığında, bu yineleyici denetimleri gerçekleştirilir:

- Tüm standart yineleyiciler (örneğin, [vector:: Yineleyici](../standard-library/vector-class.md#iterator)) denetlenir.

- Çıkış Yineleyici, denetlenen bir yineleyici ise, [std:: Copy](../standard-library/algorithm-functions.md#copy) işaretli davranış gibi standart kitaplık işlevlerine çağrı yapılır.

- Çıkış yineleyici işaretsiz bir yineleyiciyse, standart kitaplık işlevlerine yapılan çağrılar derleyici uyarılarına neden olur.

- Aşağıdaki işlevler, kapsayıcının sınırları dışında bir erişim varsa bir çalışma zamanı hatası oluşturur:

:::row:::
   :::column span="":::
      &emsp;&emsp;[`basic_string::operator[]`](../standard-library/basic-string-class.md#op_at)\
      &emsp;&emsp;[`bitset::operator[]`](../standard-library/bitset-class.md#op_at)\
      &emsp;&emsp;[`deque::back`](../standard-library/deque-class.md#back)\
      &emsp;&emsp;[`deque::front`](../standard-library/deque-class.md#front)
   :::column-end:::
   :::column span="":::
      [`deque::operator[]`](../standard-library/deque-class.md#op_at)\
      [`list::back`](../standard-library/list-class.md#back)\
      [`list::front`](../standard-library/list-class.md#front)\
      [`queue::back`](../standard-library/queue-class.md#back)
   :::column-end:::
   :::column span="":::
      [`queue::front`](../standard-library/queue-class.md#front)\
      [`vector::back`](../standard-library/vector-class.md#back)\
      [`vector::front`](../standard-library/vector-class.md#front)\
      [`vector::operator[]`](../standard-library/vector-class.md#op_at)
   :::column-end:::
:::row-end:::

_ITERATOR_DEBUG_LEVEL 0 olarak tanımlandığında:

- Tüm standart yineleyiciler işaretlenmemiştir. Yineleyiciler kapsayıcı sınırlarının ötesine geçebilir, bu da tanımsız davranışa yol açar.

- Çıkış Yineleyici, denetlenen bir yineleyici ise, işaretli davranış gibi standart kitaplık işlevlerine çağrı yapılır `std::copy` .

- Çıkış yineleyici işaretsiz bir yineleyiciyse, standart kitaplık işlevlerine yapılan çağrılar Denetlenmemiş davranışı alır.

Denetlenen bir yineleyici, kapsayıcının sınırları dışına taşımaya çalışırsanız çağıran bir yineleyici anlamına gelir `invalid_parameter_handler` . Hakkında daha fazla bilgi için `invalid_parameter_handler` bkz. [parametre doğrulama](../c-runtime-library/parameter-validation.md).

Denetlenen yineleyiciler destekleyen Yineleyici bağdaştırıcılar [Checked_array_iterator sınıfı](../standard-library/checked-array-iterator-class.md) ve [unchecked_array_iterator sınıfıdır](../standard-library/unchecked-array-iterator-class.md).

## <a name="examples"></a>Örnekler

' I 1 veya 2 ' ye ayarlanmış _ITERATOR_DEBUG_LEVEL kullanarak derlerken, belirli sınıfların dizin oluşturma işlecini kullanarak kapsayıcının sınırları dışında bir öğeye erişmeyi denerseniz bir çalışma zamanı hatası oluşur.

```cpp
// checked_iterators_1.cpp
// cl.exe /Zi /MDd /EHsc /W4

#define _ITERATOR_DEBUG_LEVEL 1

#include <vector>
#include <iostream>

using namespace std;

int main()
{
   vector<int> v;
   v.push_back(67);

   int i = v[0];
   cout << i << endl;

   i = v[1]; //triggers invalid parameter handler
}
```

Bu program "67" yazdırır ve hata hakkında ek bilgi içeren bir onaylama işlemi hatası iletişim kutusu açılır.

Benzer şekilde, 1 veya 2 ' ye ayarlanmış _ITERATOR_DEBUG_LEVEL kullanarak derlerken, `front` `back` kapsayıcı boş olduğunda kapsayıcı sınıflarında veya kullanarak bir öğeye erişmeyi denerseniz bir çalışma zamanı hatası oluşur.

```cpp
// checked_iterators_2.cpp
// cl.exe /Zi /MDd /EHsc /W4
#define _ITERATOR_DEBUG_LEVEL 1

#include <vector>
#include <iostream>

using namespace std;

int main()
{
   vector<int> v;

   int& i = v.front(); // triggers invalid parameter handler
}
```

Bu program hata hakkında ek bilgi içeren bir onaylama işlemi hatası iletişim kutusu açılır.

Aşağıdaki kod, her biriyle ilgili yorumlar içeren çeşitli yineleyici kullanım örneği senaryolarını gösterir. Varsayılan olarak, _ITERATOR_DEBUG_LEVEL hata ayıklama yapılarında 2 ' ye ve perakende yapılarda 0 ' a ayarlanır.

```cpp
// checked_iterators_3.cpp
// cl.exe /MTd /EHsc /W4

#include <algorithm>
#include <array>
#include <iostream>
#include <iterator>
#include <numeric>
#include <string>
#include <vector>

using namespace std;

template <typename C>
void print(const string& s, const C& c)
{
    cout << s;

    for (const auto& e : c) {
        cout << e << " ";
    }

    cout << endl;
}

int main()
{
    vector<int> v(16);
    iota(v.begin(), v.end(), 0);
    print("v: ", v);

    // OK: vector::iterator is checked in debug mode
    // (i.e. an overrun causes a debug assertion)
    vector<int> v2(16);
    transform(v.begin(), v.end(), v2.begin(), [](int n) { return n * 2; });
    print("v2: ", v2);

    // OK: back_insert_iterator is marked as checked in debug mode
    // (i.e. an overrun is impossible)
    vector<int> v3;
    transform(v.begin(), v.end(), back_inserter(v3), [](int n) { return n * 3; });
    print("v3: ", v3);

    // OK: array::iterator is checked in debug mode
    // (i.e. an overrun causes a debug assertion)
    array<int, 16> a4;
    transform(v.begin(), v.end(), a4.begin(), [](int n) { return n * 4; });
    print("a4: ", a4);

    // OK: Raw arrays are checked in debug mode
    // (an overrun causes a debug assertion)
    // NOTE: This applies only when raw arrays are given to C++ Standard Library algorithms!
    int a5[16];
    transform(v.begin(), v.end(), a5, [](int n) { return n * 5; });
    print("a5: ", a5);

    // WARNING C4996: Pointers cannot be checked in debug mode
    // (an overrun causes undefined behavior)
    int a6[16];
    int * p6 = a6;
    transform(v.begin(), v.end(), p6, [](int n) { return n * 6; });
    print("a6: ", a6);

    // OK: stdext::checked_array_iterator is checked in debug mode
    // (an overrun causes a debug assertion)
    int a7[16];
    int * p7 = a7;
    transform(v.begin(), v.end(), stdext::make_checked_array_iterator(p7, 16), [](int n) { return n * 7; });
    print("a7: ", a7);

    // WARNING SILENCED: stdext::unchecked_array_iterator is marked as checked in debug mode
    // (it performs no checking, so an overrun causes undefined behavior)
    int a8[16];
    int * p8 = a8;
    transform(v.begin(), v.end(), stdext::make_unchecked_array_iterator(p8), [](int n) { return n * 8; });
    print("a8: ", a8);
}
```

Derleyici kullanarak bu kodu derlerken `cl.exe /EHsc /W4 /MTd checked_iterators_3.cpp` bir uyarı yayar, ancak bir çalıştırılabilire hata olmadan derlenir:

```Output
algorithm(1026) : warning C4996: 'std::_Transform1': Function call with parameters
that may be unsafe - this call relies on the caller to check that the passed values
are correct. To disable this warning, use -D_SCL_SECURE_NO_WARNINGS. See documentation
on how to use Visual C++ 'Checked Iterators'
```

Komut satırında çalıştırıldığında, yürütülebilir bu çıktıyı oluşturur:

```Output
v: 0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15
v2: 0 2 4 6 8 10 12 14 16 18 20 22 24 26 28 30
v3: 0 3 6 9 12 15 18 21 24 27 30 33 36 39 42 45
a4: 0 4 8 12 16 20 24 28 32 36 40 44 48 52 56 60
a5: 0 5 10 15 20 25 30 35 40 45 50 55 60 65 70 75
a6: 0 6 12 18 24 30 36 42 48 54 60 66 72 78 84 90
a7: 0 7 14 21 28 35 42 49 56 63 70 77 84 91 98 105
a8: 0 8 16 24 32 40 48 56 64 72 80 88 96 104 112 120
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığına genel bakış](../standard-library/cpp-standard-library-overview.md)\
[Hata ayıklama Yineleyici desteği](../standard-library/debug-iterator-support.md)
