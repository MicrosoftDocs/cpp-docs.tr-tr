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
ms.openlocfilehash: 63cbbb3a1a508b41c1e0632eda3eeabe4fda6696
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72685827"
---
# <a name="subtract_with_carry_engine-class"></a>subtract_with_carry_engine Sınıfı

Birlikte tut (sırasında geride Fibonaccı) algoritması ile rastgele bir sıra üretir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class UIntType, size_t W, size_t S, size_t R>
class subtract_with_carry_engine;
```

### <a name="parameters"></a>Parametreler

*Uinttype* \
İşaretsiz tamsayı sonuç türü. Olası türler için bkz. [\<random >](../standard-library/random.md).

*W* \
**Sözcük boyutu**. Durum sırasının bit cinsinden her bir sözcüğün boyutu. **Önkoşul**: `0 < W ≤ numeric_limits<UIntType>::digits`

*S* \
**Kısa gecikme**. Tamsayı değerlerinin sayısı. **Önkoşul**: `0 < S < R`

*R* \
**Uzun gecikme**. Oluşturulan serideki yinelemeyi belirler.

## <a name="members"></a>Üyeler

||||
|-|-|-|
|`subtract_with_carry_engine::subtract_with_carry_engine`|`subtract_with_carry_engine::min`|`subtract_with_carry_engine::discard`|
|`subtract_with_carry_engine::operator()`|`subtract_with_carry_engine::max`|`subtract_with_carry_engine::seed`|
|`default_seed`, `subtract_with_carry_engine::seed` ve tek değer Oluşturucusu için varsayılan parametre değeri olarak kullanılan `19780503u` olarak tanımlanan bir üye sabitidir.|||

Altyapı üyeleri hakkında daha fazla bilgi için bkz. [\<random >](../standard-library/random.md).

## <a name="remarks"></a>Açıklamalar

@No__t_0 sınıf şablonu, [linear_congruential_engine](../standard-library/linear-congruential-engine-class.md)üzerinde bir iyileştirmedir. Bu altyapılar için ne kadar hızlı veya [mersenne_twister_engine](../standard-library/mersenne-twister-engine-class.md)olarak yüksek kaliteli sonuçlar vardır.

Bu altyapı, bir kullanıcı tarafından belirtilen işaretsiz integral türünün değerlerini, yineleme ilişkisi ( *period*) `x(i) = (x(i - R) - x(i - S) - cy(i - 1)) mod M` kullanarak üretir; burada `cy(i)` `1` `x(i - S) - x(i - R) - cy(i - 1) < 0`, aksi durumda `0` ve `M` `2`<sup>W</sup>değerine sahiptir. Altyapının durumu bir taşıma göstergesi artı *R* değerleridir. Bu değerler, `operator()` en az *r* kez çağrılmışsa döndürülen son *r* değerlerinden oluşur, aksi takdirde döndürülen `N` değerleri ve çekirdek değerinin son `R - N` değerleridir.

@No__t_0 şablon bağımsız değişkeni, değerleri `M - 1` tutulacak kadar büyük olmalıdır.

Bu altyapıdan doğrudan bir Oluşturucu oluşturabilseniz de, önceden tanımlanmış aşağıdaki Typedefs 'lerden birini de kullanabilirsiniz:

`ranlux24_base`: `ranlux24` için temel olarak kullanılır.
`typedef subtract_with_carry_engine<unsigned int, 24, 10, 24> ranlux24_base;`

`ranlux48_base`: `ranlux48` için temel olarak kullanılır.
`typedef subtract_with_carry_engine<unsigned long long, 48, 5, 12> ranlux48_base;`

Taşıma altyapısı algoritması ile ilgili ayrıntılı bilgi için bkz. [sırasında geride Fibonaccı Oluşturucu](https://en.wikipedia.org/wiki/Lagged_Fibonacci_generator).

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<random >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[\<random >](../standard-library/random.md)
