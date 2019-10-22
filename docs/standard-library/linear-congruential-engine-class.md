---
title: linear_congruential_engine Sınıfı
ms.date: 11/04/2016
f1_keywords:
- random/std::linear_congruential_engine
helpviewer_keywords:
- linear_congruential_engine class
ms.assetid: 30e00ca6-1933-4701-9561-54f3e810a5a1
ms.openlocfilehash: 3c1824eb22ed97e65e0556bc63b374f705f5c591
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689444"
---
# <a name="linear_congruential_engine-class"></a>linear_congruential_engine Sınıfı

Doğrusal uyumlu algoritmayla rastgele bir sıra üretir.

## <a name="syntax"></a>Sözdizimi

```cpp
class linear_congruential_engine{
   public:  // types
   typedef UIntType result_type;
   // engine characteristics
   static constexpr result_type multiplier = a;
   static constexpr result_type increment = c;
   static constexpr result_type modulus = m;
   static constexpr result_type min() { return c == 0u  1u: 0u; }
   static constexpr result_type max() { return m - 1u; }
   static constexpr result_type default_seed = 1u;
   // constructors and seeding functions
   explicit linear_congruential_engine(result_type s = default_seed);
   template <class Sseq>
   explicit linear_congruential_engine(Sseq& q);
   void seed(result_type s = default_seed);
   template <class Sseq>
   void seed(Sseq& q);
   // generating functions
   result_type operator()();
   void discard(unsigned long long z);
   };
```

### <a name="parameters"></a>Parametreler

*Uinttype* \
İşaretsiz tamsayı sonuç türü. Olası türler için bkz. [\<random >](../standard-library/random.md).

*Bir* \
**Çarpan**. **Önkoşul**: açıklamalar bölümüne bakın.

*C* \
**Artış**. **Önkoşul**: açıklamalar bölümüne bakın.

*A* \
**Mod**. Ön **koşul**: bkz. açıklamalar.

## <a name="members"></a>Üyeler

||||
|-|-|-|
|`linear_congruential_engine::linear_congruential_engine`|`linear_congruential_engine::min`|`linear_congruential_engine::discard`|
|`linear_congruential_engine::operator()`|`linear_congruential_engine::max`|`linear_congruential_engine::seed`|

`default_seed`, `linear_congruential_engine::seed` ve tek değer Oluşturucusu için varsayılan parametre değeri olarak kullanılan `1u` olarak tanımlanan bir üye sabitidir.

Altyapı üyeleri hakkında daha fazla bilgi için bkz. [\<random >](../standard-library/random.md).

## <a name="remarks"></a>Açıklamalar

@No__t_0 sınıfı şablonu en hızlı veya en yüksek kaliteyi değil, en basit Oluşturucu altyapısıdır. Bu altyapıya yönelik bir geliştirme [substract_with_carry_engine](../standard-library/subtract-with-carry-engine-class.md). Bu altyapılardan hiçbiri hızlı veya [mersenne_twister_engine](../standard-library/mersenne-twister-engine-class.md)olarak yüksek kaliteli sonuçlar olarak değildir.

Bu altyapı, yineleme ilişkisini ( *period*) `x(i) = (A * x(i-1) + C) mod M` kullanarak, Kullanıcı tarafından belirtilen işaretsiz integral türünün değerlerini üretir.

*D* sıfırsa, bu mod işlemi için kullanılan değer `numeric_limits<result_type>::max() + 1`. Altyapının durumu döndürülen son değer veya `operator()` hiçbir çağrı yapılmediğinde çekirdek değeri.

*M* sıfır değilse, *a* ve *C* şablon bağımsız değişkenlerinin değerleri *M*'den küçük olmalıdır.

Bu altyapıdan doğrudan bir Oluşturucu oluşturabilseniz de, bu önceden tanımlanmış Typedefs değerlerinden birini de kullanabilirsiniz.

`minstd_rand0`:1988 minimal standart altyapı (Liwis, Goodman ve Miller, 1969).

```cpp
typedef linear_congruential_engine<unsigned int, 16807, 0, 2147483647> minstd_rand0;
```

`minstd_rand`: minimum standart motor `minstd_rand0` (Park, Miller ve Stockmeyer, 1993) güncelleştirildi.

```cpp
typedef linear_congruential_engine<unsigned int, 48271, 0, 2147483647> minstd_rand;
```

Doğrusal bir eş altyapı algoritması hakkında ayrıntılı bilgi için bkz. Vikipedi makalesi [Doğrusal congruize Oluşturucu](https://go.microsoft.com/fwlink/p/?linkid=402446).

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<random >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[\<random >](../standard-library/random.md)
