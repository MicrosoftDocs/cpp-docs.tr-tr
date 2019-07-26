---
title: subtract_with_carry_engine Sınıfı
ms.date: 11/04/2016
f1_keywords:
- random/std::subtract_with_carry_engine
- random/std::subtract_with_carry_engine::default_seed
- random/std::subtract_with_carry_engine::discard
- random/std::subtract_with_carry_engine::min
- random/std::subtract_with_carry_engine::max
- random/std::subtract_with_carry_engine::seed
helpviewer_keywords:
- std::subtract_with_carry_engine [C++]
- std::subtract_with_carry_engine [C++], default_seed
- std::subtract_with_carry_engine [C++], discard
- std::subtract_with_carry_engine [C++], min
- std::subtract_with_carry_engine [C++], max
- std::subtract_with_carry_engine [C++], seed
ms.assetid: 94a055f2-a620-4a22-ac34-c156924bab31
ms.openlocfilehash: 17091e33c504df60c0b6b8e346d2a6fd3893679c
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68447412"
---
# <a name="subtractwithcarryengine-class"></a>subtract_with_carry_engine Sınıfı

Birlikte tut (sırasında geride Fibonaccı) algoritması ile rastgele bir sıra üretir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class UIntType, size_t W, size_t S, size_t R>
class subtract_with_carry_engine;
```

### <a name="parameters"></a>Parametreler

*UIntType*\
İşaretsiz tamsayı sonuç türü. Olası türler için bkz [ \<. Random >](../standard-library/random.md).

*ANLATIMI*\
**Sözcük boyutu**. Durum sırasının bit cinsinden her bir sözcüğün boyutu. **Önkoşul**:`0 < W ≤ numeric_limits<UIntType>::digits`

*MALAR*\
**Kısa gecikme**. Tamsayı değerlerinin sayısı. **Önkoşul**:`0 < S < R`

*R*\
**Uzun gecikme**. Oluşturulan serideki yinelemeyi belirler.

## <a name="members"></a>Üyeler

||||
|-|-|-|
|`subtract_with_carry_engine::subtract_with_carry_engine`|`subtract_with_carry_engine::min`|`subtract_with_carry_engine::discard`|
|`subtract_with_carry_engine::operator()`|`subtract_with_carry_engine::max`|`subtract_with_carry_engine::seed`|
|`default_seed``19780503u`, için`subtract_with_carry_engine::seed` varsayılan parametre değeri olarak kullanılan, ve tek değer Oluşturucusu olarak tanımlanmış bir üye sabiti.|||

Altyapı üyeleri hakkında daha fazla bilgi için bkz [ \<. Random >](../standard-library/random.md).

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı linear_congruential_engine üzerinde bir iyileştirmedir. [](../standard-library/linear-congruential-engine-class.md) `substract_with_carry_engine` Bu altyapılar için ne kadar hızlı veya [mersenne_twister_engine](../standard-library/mersenne-twister-engine-class.md)olarak yüksek kaliteli sonuçlar vardır.

Bu altyapı, bir kullanıcı tarafından belirtilen işaretsiz integral türünün değerlerini, yineleme ilişkisini ( *period*) `x(i) = (x(i - R) - x(i - S) - cy(i - 1)) mod M`kullanarak üretir; `1` burada `cy(i)` `x(i - S) - x(i - R) - cy(i - 1) < 0`,, aksi durumda ve `M` `0` , <sup>W</sup>değerine `2`sahiptir. Altyapının durumu bir taşıma göstergesi artı *R* değerleridir. Bu değerler, en az `N` *R* kez çağrılırsa döndürülen `operator()` son *r* değerlerinden oluşur, aksi takdirde döndürülen değerler ve çekirdek değerinin son `R - N` değerleridir.

Şablon bağımsız değişkeni `UIntType` , değerleri `M - 1`en fazla tutmak için yeterince büyük olmalıdır.

Bu altyapıdan doğrudan bir Oluşturucu oluşturabilseniz de, önceden tanımlanmış aşağıdaki Typedefs 'lerden birini de kullanabilirsiniz:

`ranlux24_base`: İçin `ranlux24`temel olarak kullanılır.
`typedef subtract_with_carry_engine<unsigned int, 24, 10, 24> ranlux24_base;`

`ranlux48_base`: İçin `ranlux48`temel olarak kullanılır.
`typedef subtract_with_carry_engine<unsigned long long, 48, 5, 12> ranlux48_base;`

Taşıma altyapısı algoritması ile ilgili ayrıntılı bilgi için bkz. [sırasında geride Fibonaccı Oluşturucu](https://en.wikipedia.org/wiki/Lagged_Fibonacci_generator).

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<rastgele >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[\<Rastgele >](../standard-library/random.md)
