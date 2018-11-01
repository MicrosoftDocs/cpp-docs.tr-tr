---
title: linear_congruential_engine Sınıfı
ms.date: 11/04/2016
f1_keywords:
- random/std::linear_congruential_engine
helpviewer_keywords:
- linear_congruential_engine class
ms.assetid: 30e00ca6-1933-4701-9561-54f3e810a5a1
ms.openlocfilehash: 83306e47995f652014682d6bcc94966aab75c062
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50568183"
---
# <a name="linearcongruentialengine-class"></a>linear_congruential_engine Sınıfı

Çizgisel eşleşik algoritmasını tarafından rastgele bir sıra üretir.

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

*UIntType*<br/>
İşeritsiz tamsayı sonuç türü. Olası türleri için bkz: [ \<rastgele >](../standard-library/random.md).

*A*<br/>
**Çarpan**. **Önkoşul**: bkz. Açıklamalar bölümü.

*C*<br/>
**Artırma**. **Önkoşul**: bkz. Açıklamalar bölümü.

*M*<br/>
**Modulus**. **Önkoşul**: açıklamalara bakın.

## <a name="members"></a>Üyeler

||||
|-|-|-|
|`linear_congruential_engine::linear_congruential_engine`|`linear_congruential_engine::min`|`linear_congruential_engine::discard`|
|`linear_congruential_engine::operator()`|`linear_congruential_engine::max`|`linear_congruential_engine::seed`|

`default_seed` üye sabit, olarak tanımlı `1u`için varsayılan parametre değeri olarak kullanılır `linear_congruential_engine::seed` ve tek değer Oluşturucusu.

Altyapısı üyeleri hakkında daha fazla bilgi için bkz. [ \<rastgele >](../standard-library/random.md).

## <a name="remarks"></a>Açıklamalar

`linear_congruential_engine` Şablon sınıfı, en basit Oluşturucu altyapısı, ancak hızlı veya yüksek kalite değil. Bu altyapı üzerinden bir iyileştirmedir [substract_with_carry_engine](../standard-library/subtract-with-carry-engine-class.md). Hızlı veya bu altyapılar hiçbiri değildir yüksek kaliteli sonuçlar olarak [mersenne_twister_engine](../standard-library/mersenne-twister-engine-class.md).

Bu altyapı yinelenme ilişkisini kullanarak bir kullanıcı tarafından belirtilen işeritsiz tamsayı türünü değerlerini üretir ( *süresi*) `x(i) = (A * x(i-1) + C) mod M`.

Varsa *M* sıfırsa, bu mod işlemi için kullanılan değer `numeric_limits<result_type>::max() + 1`. İçin hiçbir çağrı yapılır altyapının durumu son döndürülen değer veya çekirdek değeri ise `operator()`.

Varsa *M* sıfır olmayan şablon bağımsız değişkenlerinin değerleri olan *A* ve *C* olmalıdır küçüktür *M*.

Doğrudan bu altyapısından bir oluşturucuyu oluşturmak olsa da, önceden tanımlanmış bu tür tanımlarından birini de kullanabilirsiniz.

`minstd_rand0`: 1988 en az standart altyapısı (Gamze, Goodman ve Miller, 1969).

```cpp
typedef linear_congruential_engine<unsigned int, 16807, 0, 2147483647> minstd_rand0;
```

`minstd_rand`: Güncelleştirilmiş en az standart altyapısını `minstd_rand0` (Park, Miller ve Stockmeyer, 1993).

```cpp
typedef linear_congruential_engine<unsigned int, 48271, 0, 2147483647> minstd_rand;
```

Çizgisel eşleşik altyapısı algoritma hakkında ayrıntılı bilgi için bkz. Wikipedia makalesi [çizgisel eşleşik Oluşturucu](http://go.microsoft.com/fwlink/p/?linkid=402446).

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<rastgele >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[\<rastgele >](../standard-library/random.md)<br/>
