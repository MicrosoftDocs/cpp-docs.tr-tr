---
title: linear_congruential_engine sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- random/std::linear_congruential_engine
dev_langs:
- C++
helpviewer_keywords:
- linear_congruential_engine class
ms.assetid: 30e00ca6-1933-4701-9561-54f3e810a5a1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6f902e7a1a3ae4bcb35a4822228425747476d5bc
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="linearcongruentialengine-class"></a>linear_congruential_engine Sınıfı

Rastgele bir dizisi doğrusal congruential algoritması tarafından oluşturur.

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

`UIntType` İşaretsiz tamsayı sonuç türü. Olası türleri için bkz: [ \<rastgele >](../standard-library/random.md).

`A` **Çarpan**. **Önkoşul**: bkz Açıklamalar bölümüne.

`C` **Artırma**. **Önkoşul**: bkz Açıklamalar bölümüne.

`M` **Modulus**. **Önkoşul**: Açıklamalar bakın.

## <a name="members"></a>Üyeler

||||
|-|-|-|
|`linear_congruential_engine::linear_congruential_engine`|`linear_congruential_engine::min`|`linear_congruential_engine::discard`|
|`linear_congruential_engine::operator()`|`linear_congruential_engine::max`|`linear_congruential_engine::seed`|

`default_seed` üye sabit, tanımlanmış olarak `1u`, varsayılan parametre değeri olarak kullanılan `linear_congruential_engine::seed` ve tek değer Oluşturucusu.

Altyapısı üyeleri hakkında daha fazla bilgi için bkz: [ \<rastgele >](../standard-library/random.md).

## <a name="remarks"></a>Açıklamalar

`linear_congruential_engine` Şablon sınıfıdır basit Oluşturucu altyapısı ancak değil hızlı veya en yüksek kaliteli. Bu altyapı üzerinden bir iyileştirme [substract_with_carry_engine](../standard-library/subtract-with-carry-engine-class.md). Bu altyapılar ne kadar hızlı mi yüksek kaliteli sonuçları [mersenne_twister_engine](../standard-library/mersenne-twister-engine-class.md).

Bu altyapı yinelenme ilişkisini kullanarak bir kullanıcı tarafından belirtilen imzasız tam sayı türü değerleri üretir ( *süresi*) `x(i) = (A * x(i-1) + C) mod M`.

Varsa `M` sıfırsa, bu modül işlemi için kullanılan değer `numeric_limits<result_type>::max() + 1`. İçin bir çağrı yapılır altyapının durum döndürülen son değer veya çekirdek değeri ise `operator()`.

Varsa `M` sıfır olmayan şablon bağımsız değişkenlerin değerleri olan `A` ve `C` olmalıdır değerinden `M`.

Bu altyapısından bir oluşturucuyu doğrudan oluşturabileceğiniz karşın, bu önceden tanımlanmış tür tanımları birini de kullanabilirsiniz.

`minstd_rand0`: 1988 en az standart altyapısı (Gamze, Goodman ve Mert, 1969).

```cpp
typedef linear_congruential_engine<unsigned int, 16807, 0, 2147483647> minstd_rand0;
```

`minstd_rand`: En az güncelleştirilmiş standart altyapısını `minstd_rand0` (Park, Mert ve Stockmeyer, 1993).

```cpp
typedef linear_congruential_engine<unsigned int, 48271, 0, 2147483647> minstd_rand;
```

Wikipedia makaleyi doğrusal congruential altyapısı algoritması hakkında ayrıntılı bilgi için bkz: [doğrusal congruential Oluşturucu](http://go.microsoft.com/fwlink/p/?linkid=402446).

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<rastgele >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[\<rastgele >](../standard-library/random.md)<br/>
