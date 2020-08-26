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
ms.openlocfilehash: cf82c4ca3ce995fa9a53dbea21293dc8515ff491
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88840914"
---
# <a name="subtract_with_carry_engine-class"></a>subtract_with_carry_engine Sınıfı

Birlikte tut (sırasında geride Fibonaccı) algoritması ile rastgele bir sıra üretir.

## <a name="syntax"></a>Söz dizimi

```cpp
template <class UIntType, size_t W, size_t S, size_t R>
class subtract_with_carry_engine;
```

### <a name="parameters"></a>Parametreler

*UIntType*\
İşaretsiz tamsayı sonuç türü. Olası türler için bkz [\<random>](../standard-library/random.md) ..

*Anlatımı*\
**Sözcük boyutu**. Durum sırasının bit cinsinden her bir sözcüğün boyutu. **Önkoşul**: `0 < W ≤ numeric_limits<UIntType>::digits`

*Malar*\
**Kısa gecikme**. Tamsayı değerlerinin sayısı. **Önkoşul**: `0 < S < R`

*Sağ*\
**Uzun gecikme**. Oluşturulan serideki yinelemeyi belirler.

## <a name="members"></a>Üyeler

`subtract_with_carry_engine::subtract_with_carry_engine`
`subtract_with_carry_engine::max`\
`subtract_with_carry_engine::min`\
`subtract_with_carry_engine::discard`\
`subtract_with_carry_engine::operator()`\
`subtract_with_carry_engine::seed`

`default_seed``19780503u`, için varsayılan parametre değeri olarak kullanılan, `subtract_with_carry_engine::seed` ve tek değer Oluşturucusu olarak tanımlanmış bir üye sabiti.

Altyapı üyeleri hakkında daha fazla bilgi için bkz [\<random>](../standard-library/random.md) ..

## <a name="remarks"></a>Açıklamalar

`substract_with_carry_engine`Sınıf şablonu, [linear_congruential_engine](../standard-library/linear-congruential-engine-class.md)bir iyileştirmedir. Bu altyapılar için ne kadar hızlı veya [mersenne_twister_engine](../standard-library/mersenne-twister-engine-class.md)olarak yüksek kaliteli sonuçlar olarak olur.

Bu altyapı, bir kullanıcı tarafından belirtilen işaretsiz integral türünün değerlerini, yineleme ilişkisini ( *period*) kullanarak üretir; burada,, `x(i) = (x(i - R) - x(i - S) - cy(i - 1)) mod M` `cy(i)` `1` `x(i - S) - x(i - R) - cy(i - 1) < 0` Aksi durumda `0` ve `M` değeri `2` <sup>W</sup>değerine sahiptir. Altyapının durumu bir taşıma göstergesi artı *R* değerleridir. Bu değerler, en az R kez çağrılırsa döndürülen son *r* değerlerinden oluşur `operator()` , aksi *R* takdirde `N` döndürülen değerler ve `R - N` çekirdek değerinin son değerleridir.

Şablon bağımsız değişkeni, `UIntType` değerleri en fazla tutmak için yeterince büyük olmalıdır `M - 1` .

Bu altyapıdan doğrudan bir Oluşturucu oluşturabilseniz de, önceden tanımlanmış aşağıdaki Typedefs 'lerden birini de kullanabilirsiniz:

`ranlux24_base`: İçin temel olarak kullanılır `ranlux24` .
`typedef subtract_with_carry_engine<unsigned int, 24, 10, 24> ranlux24_base;`

`ranlux48_base`: İçin temel olarak kullanılır `ranlux48` .
`typedef subtract_with_carry_engine<unsigned long long, 48, 5, 12> ranlux48_base;`

Taşıma altyapısı algoritması ile ilgili ayrıntılı bilgi için bkz. [sırasında geride Fibonaccı Oluşturucu](https://en.wikipedia.org/wiki/Lagged_Fibonacci_generator).

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<random>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[\<random>](../standard-library/random.md)
