---
title: linear_congruential_engine Sınıfı
ms.date: 11/04/2016
f1_keywords:
- random/std::linear_congruential_engine
helpviewer_keywords:
- linear_congruential_engine class
ms.assetid: 30e00ca6-1933-4701-9561-54f3e810a5a1
ms.openlocfilehash: f5b448fbf158cf9e9cfb8331c6ec7a228859fffc
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68447581"
---
# <a name="linearcongruentialengine-class"></a>linear_congruential_engine Sınıfı

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

*UIntType*\
İşaretsiz tamsayı sonuç türü. Olası türler için bkz [ \<. Random >](../standard-library/random.md).

*A*\
**Çarpan**. **Önkoşul**: Bkz. açıklamalar bölümü.

*,* \
**Artış**. **Önkoşul**: Bkz. açıklamalar bölümü.

*M*\
**Mod**. **Önkoşul**: Bkz. açıklamalar.

## <a name="members"></a>Üyeler

||||
|-|-|-|
|`linear_congruential_engine::linear_congruential_engine`|`linear_congruential_engine::min`|`linear_congruential_engine::discard`|
|`linear_congruential_engine::operator()`|`linear_congruential_engine::max`|`linear_congruential_engine::seed`|

`default_seed``1u`, için`linear_congruential_engine::seed` varsayılan parametre değeri olarak kullanılan, ve tek değer Oluşturucusu olarak tanımlanmış bir üye sabiti.

Altyapı üyeleri hakkında daha fazla bilgi için bkz [ \<. Random >](../standard-library/random.md).

## <a name="remarks"></a>Açıklamalar

`linear_congruential_engine` Şablon sınıfı en hızlı veya en yüksek kaliteyi değil, en basit Oluşturucu altyapısıdır. Bu altyapıya yönelik bir geliştirme [substract_with_carry_engine](../standard-library/subtract-with-carry-engine-class.md). Bu altyapılardan hiçbiri hızlı veya [mersenne_twister_engine](../standard-library/mersenne-twister-engine-class.md)olarak yüksek kaliteli sonuçlar olarak değildir.

Bu altyapı, bir kullanıcı tarafından belirtilen işaretsiz integral türünün değerlerini yineleme ilişkisini ( *period*) `x(i) = (A * x(i-1) + C) mod M`kullanarak üretir.

*D* sıfırsa, bu mod işlemi `numeric_limits<result_type>::max() + 1`için kullanılan değer. Altyapının durumu döndürülen son değer ya da hiçbir çağrı yapılmediğinde `operator()`çekirdek değeri.

*M* sıfır değilse, *a* ve *C* şablon bağımsız değişkenlerinin değerleri *M*'den küçük olmalıdır.

Bu altyapıdan doğrudan bir Oluşturucu oluşturabilseniz de, bu önceden tanımlanmış Typedefs değerlerinden birini de kullanabilirsiniz.

`minstd_rand0`: 1988 en düşük standart altyapı (Liwis, Goodman ve Miller, 1969).

```cpp
typedef linear_congruential_engine<unsigned int, 16807, 0, 2147483647> minstd_rand0;
```

`minstd_rand`: Minimum standart motor `minstd_rand0` (Park, Miller ve Stockmeyer, 1993) güncelleştirildi.

```cpp
typedef linear_congruential_engine<unsigned int, 48271, 0, 2147483647> minstd_rand;
```

Doğrusal bir eş altyapı algoritması hakkında ayrıntılı bilgi için bkz. Vikipedi makalesi [Doğrusal congruize Oluşturucu](https://go.microsoft.com/fwlink/p/?linkid=402446).

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<rastgele >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[\<Rastgele >](../standard-library/random.md)
