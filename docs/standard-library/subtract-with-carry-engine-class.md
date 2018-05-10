---
title: subtract_with_carry_engine sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- random/std::subtract_with_carry_engine
- random/std::subtract_with_carry_engine::default_seed
- random/std::subtract_with_carry_engine::discard
- random/std::subtract_with_carry_engine::min
- random/std::subtract_with_carry_engine::max
- random/std::subtract_with_carry_engine::seed
dev_langs:
- C++
helpviewer_keywords:
- std::subtract_with_carry_engine [C++]
- std::subtract_with_carry_engine [C++], default_seed
- std::subtract_with_carry_engine [C++], discard
- std::subtract_with_carry_engine [C++], min
- std::subtract_with_carry_engine [C++], max
- std::subtract_with_carry_engine [C++], seed
ms.assetid: 94a055f2-a620-4a22-ac34-c156924bab31
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3ccf17eb39d71d444db9154fb06991be42c34a70
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="subtractwithcarryengine-class"></a>subtract_with_carry_engine Sınıfı

Rastgele bir dizi çıkarma-ile-taşıyan (lagged Fibonacci) algoritması tarafından oluşturur.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class UIntType, size_t W, size_t S, size_t R>
class subtract_with_carry_engine;
```

### <a name="parameters"></a>Parametreler

`UIntType` İşaretsiz tamsayı sonuç türü. Olası türleri için bkz: [ \<rastgele >](../standard-library/random.md).

`W` **Word boyutu**. Her sözcüğün durumu dizisi bit cinsinden boyutu. **Önkoşul**: `0 < W ≤ numeric_limits<UIntType>::digits`

`S` **Kısa gecikme**. Tamsayı değerleri sayısı. **Önkoşul**: `0 < S < R`

`R` **Uzun öteleme**. Oluşturulan serideki yinelenme belirler.

## <a name="members"></a>Üyeler

||||
|-|-|-|
|`subtract_with_carry_engine::subtract_with_carry_engine`|`subtract_with_carry_engine::min`|`subtract_with_carry_engine::discard`|
|`subtract_with_carry_engine::operator()`|`subtract_with_carry_engine::max`|`subtract_with_carry_engine::seed`|
|`default_seed` üye sabit, tanımlanmış olarak `19780503u`, varsayılan parametre değeri olarak kullanılan `subtract_with_carry_engine::seed` ve tek değer Oluşturucusu.|||

Altyapısı üyeleri hakkında daha fazla bilgi için bkz: [ \<rastgele >](../standard-library/random.md).

## <a name="remarks"></a>Açıklamalar

`substract_with_carry_engine` Şablon sınıfıdır bir geliştirme üzerinden [linear_congruential_engine](../standard-library/linear-congruential-engine-class.md). Bu altyapılar için ne kadar hızlı mi yüksek kaliteli sonuçları [mersenne_twister_engine](../standard-library/mersenne-twister-engine-class.md).

Bu altyapı türünün değerlerini yinelenme ilişkisini kullanarak bir kullanıcı tarafından belirtilen imzasız tam sayı oluşturur ( *süresi*) `x(i) = (x(i - R) - x(i - S) - cy(i - 1)) mod M`, burada `cy(i)` değerine sahip `1` varsa `x(i - S) - x(i - R) - cy(i - 1) < 0`, aksi takdirde `0`, ve `M` değerine sahip `2` <sup>W</sup>. Bir taşıma altyapının durumudur göstergesi artı `R` değerleri. Bu değerleri son oluşur `R` değerleri döndürülen IF `operator()` en az adlı `R` zaman, aksi takdirde `N` verilinceye değerleri ve son `R - N` çekirdek değerleri.

Şablon bağımsız değişken `UIntType` değerleri kadar tutmaya yetecek büyüklükte olmalıdır `M - 1`.

Bu altyapısından bir oluşturucuyu doğrudan oluşturabileceğiniz karşın, bu önceden tanımlanmış tür tanımları birini de kullanabilirsiniz:

`ranlux24_base`: İçin temel olarak kullanılan `ranlux24`.
`typedef subtract_with_carry_engine<unsigned int, 24, 10, 24> ranlux24_base;`

`ranlux48_base`: İçin temel olarak kullanılan `ranlux48`.
`typedef subtract_with_carry_engine<unsigned long long, 48, 5, 12> ranlux48_base;`

Wikipedia makaleyi taşıyan altyapısı algoritmayla subract hakkında ayrıntılı bilgi için bkz: [Lagged Fibonacci Oluşturucu](http://go.microsoft.com/fwlink/p/?linkid=402445).

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<rastgele >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[\<rastgele >](../standard-library/random.md)<br/>
