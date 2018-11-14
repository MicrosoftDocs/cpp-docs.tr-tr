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
ms.openlocfilehash: 163729b401fa917d7df0002c621998f5021757f6
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51521498"
---
# <a name="checked-iterators"></a>Denetlenmiş Yineleyiciler

İşaretli yineleyiciler, kapsayıcınızın sınırlarının geçersiz kılınmamasını sağlar. İşaretli yineleyiciler, hem yayın derlemeleri ve hata ayıklama yapıları için geçerlidir. Hata ayıklama modunda derleme yaptığınızda, hata ayıklama yineleyicileri kullanma hakkında daha fazla bilgi için bkz. [Debug Iterator Support](../standard-library/debug-iterator-support.md).

## <a name="remarks"></a>Açıklamalar

İşaretli yineleyiciler tarafından oluşturulan uyarıları devre dışı bırakma hakkında daha fazla bilgi için bkz: [_scl_secure_no_warnıngs](../standard-library/scl-secure-no-warnings.md).

Kullanabileceğiniz [ \_YİNELEYİCİ\_hata ayıklama\_düzeyi](../standard-library/iterator-debug-level.md) etkinleştirme veya devre dışı işaretli yineleyiciler özellik önişlemci makrosu. _Iterator_debug_level 1 veya 2 tanımlanırsa, Yineleyicilerin güvensiz kullanımı bir çalışma zamanı hatasına neden olur ve program sonlandırılır. 0 olarak tanımlanmışsa, işaretli yineleyiciler devre dışı bırakılır. Hata ayıklama yapıları için varsayılan olarak, _ıterator_debug_level için sürüm yapıları için 0. ve 2 değerdir.

> [!IMPORTANT]
> Eski belgelere ve kaynak kodu başvurabilir [_SECURE_SCL](../standard-library/secure-scl.md) makrosu. _Iterator_debug_level _SECURE_SCL denetlemek için kullanın. Daha fazla bilgi için [_ıterator_debug_level](../standard-library/iterator-debug-level.md).

_Iterator_debug_level 1 veya 2 tanımlandığında, bu yineleyici denetimleri gerçekleştirilir:

- Tüm standart yineleyiciler (örneğin, [vector::iterator](../standard-library/vector-class.md#iterator)) denetlenir.

- Denetlenmiş yineleyici bir çıkış yineleyici ise standart kitaplık işlevleri için gibi çağıran [std::copy](../standard-library/algorithm-functions.md#copy) işaretli davranış alın.

- Çıkış yineleyici işaretlenmemiş bir yineleyiciyse, standart kitaplık işlevleri için çağrılar Derleyici uyarılarını neden.

- Kapsayıcının sınırları dışında bir erişim varsa aşağıdaki işlevleri bir çalışma zamanı hatası oluşturur:

|||||
|-|-|-|-|
|[basic_string::operator\[\]](../standard-library/basic-string-class.md#op_at)|[bitset::operator\[\]](../standard-library/bitset-class.md#op_at)|[Geri](../standard-library/deque-class.md#back)|[Ön](../standard-library/deque-class.md#front)|
|[deque::operator\[\]](../standard-library/deque-class.md#op_at)|[Geri](../standard-library/list-class.md#back)|[Ön](../standard-library/list-class.md#front)|[Geri](../standard-library/queue-class.md#back)|
|[Ön](../standard-library/queue-class.md#front)|[Vector::operator\[\]](../standard-library/vector-class.md#op_at)|[Geri](../standard-library/vector-class.md#back)|[Ön](../standard-library/vector-class.md#front)|

Ne zaman _ıterator_debug_level 0 tanımlanır:

- Tüm standart yineleyiciler işaretlenmemiş. Yineleyicileri, tanımsız davranışa yol kapsayıcı sınırlarının ötesine taşıyabilirsiniz.

- Denetlenmiş yineleyici bir çıkış yineleyici ise standart kitaplık işlevleri için gibi çağıran `std::copy` işaretli davranış alın.

- Çıkış yineleyici işaretlenmemiş bir yineleyiciyse, standart kitaplık işlevleri için çağrıları işaretsiz davranış alın.

Denetlenen bir yineleyiciye çağıran bir yineleyiciye başvurur `invalid_parameter_handler` kapsayıcının sınırlarını taşımayı denerseniz. Hakkında daha fazla bilgi için `invalid_parameter_handler`, bkz: [Parameter Validation](../c-runtime-library/parameter-validation.md).

İşaretli yineleyicileri destekleyen yineleyici başvurularıdır [checked_array_iterator sınıfı](../standard-library/checked-array-iterator-class.md) ve [unchecked_array_iterator sınıfı](../standard-library/unchecked-array-iterator-class.md).

## <a name="example"></a>Örnek

1 veya 2'ye ayarlayın _ıterator_debug_level kullanarak derleme yaptığınızda, belirli sınıfların dizinleme işlecini kullanarak kapsayıcının sınırları dışında olan bir öğeye erişmeyi denerseniz bir çalışma zamanı hatası oluşur.

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

Bu program "67" yazdırır, ardından hata hakkında ek bilgi içeren bir onaylama işlemi hatası iletişim kutusu görüntüler.

## <a name="example"></a>Örnek

1 veya 2'ye ayarlayın _ıterator_debug_level kullanarak derlediğinizde, kullanarak bir öğeye erişmeyi denerseniz, benzer şekilde, bir çalışma zamanı hatası oluşur `front` veya `back` kapsayıcı boşsa, kapsayıcı sınıflardaki.

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

Bu program hata hakkında ek bilgi içeren bir onaylama işlemi hatası iletişim kutusu görüntüler.

## <a name="example"></a>Örnek

Aşağıdaki kod, her biriyle ilgili yorumlar içeren çeşitli yineleyici kullanım örneği senaryolarını gösterir. Varsayılan olarak, _ıterator_debug_level 2 hata ayıklama yapılarında ve perakende yapılarında 0 olarak ayarlanır.

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

Derleme yaptığınızda bu kodu kullanarak `cl.exe /EHsc /W4 /MTd checked_iterators_3.cpp` derleyici bir uyarı yaydığına ancak yürütülebilir bir dosyaya hatasız derlenir:

```Output
algorithm(1026) : warning C4996: 'std::_Transform1': Function call with parameters
that may be unsafe - this call relies on the caller to check that the passed values
are correct. To disable this warning, use -D_SCL_SECURE_NO_WARNINGS. See documentation
on how to use Visual C++ 'Checked Iterators'
```

Yürütülebilir dosya, komut satırında çalıştırdığınızda, aşağıdaki çıkışı üretir:

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

[C++ Standart Kitaplığına Genel Bakış](../standard-library/cpp-standard-library-overview.md)<br/>
[Hata Ayıklama Yineleyici Desteği](../standard-library/debug-iterator-support.md)<br/>
