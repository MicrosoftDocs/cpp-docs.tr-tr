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
ms.openlocfilehash: bfb0c3c0544a9c58801f98567825e7e97e48b13c
ms.sourcegitcommit: fb9448eb96c6351a77df04af16ec5c0fb9457d9e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2018
ms.locfileid: "43687993"
---
# <a name="subtractwithcarryengine-class"></a>subtract_with_carry_engine Sınıfı

Rastgele bir sıra çıkarma-ile-taşıma (geciktirmiştir Fibonacci) algoritması tarafından üretir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class UIntType, size_t W, size_t S, size_t R>
class subtract_with_carry_engine;
```

### <a name="parameters"></a>Parametreler

*UIntType*  
 İşeritsiz tamsayı sonuç türü. Olası türleri için bkz: [ \<rastgele >](../standard-library/random.md).

*W*  
 **Word boyutu**. Her sözcüğün bitlerini durum sırası boyutu. **Önkoşul**: `0 < W ≤ numeric_limits<UIntType>::digits`

*S*  
 **Kısa bir gecikme**. Tamsayı değerleri sayısı. **Önkoşul**: `0 < S < R`

*R*  
 **Uzun lag**. Yinelenme oluşturulan serisindeki belirler.

## <a name="members"></a>Üyeler

||||
|-|-|-|
|`subtract_with_carry_engine::subtract_with_carry_engine`|`subtract_with_carry_engine::min`|`subtract_with_carry_engine::discard`|
|`subtract_with_carry_engine::operator()`|`subtract_with_carry_engine::max`|`subtract_with_carry_engine::seed`|
|`default_seed` üye sabit, olarak tanımlı `19780503u`için varsayılan parametre değeri olarak kullanılır `subtract_with_carry_engine::seed` ve tek değer Oluşturucusu.|||

Altyapısı üyeleri hakkında daha fazla bilgi için bkz. [ \<rastgele >](../standard-library/random.md).

## <a name="remarks"></a>Açıklamalar

`substract_with_carry_engine` Şablon sınıfı, bir geliştirme üzerinden [linear_congruential_engine](../standard-library/linear-congruential-engine-class.md). Bu altyapılar için ne kadar hızlı mi yüksek kaliteli sonuçlar olarak [mersenne_twister_engine](../standard-library/mersenne-twister-engine-class.md).

Yinelenme ilişkisini kullanarak bir kullanıcı tarafından belirtilen işaretsiz tamsayı türü değerleri bu altyapısı üretir ( *süresi*) `x(i) = (x(i - R) - x(i - S) - cy(i - 1)) mod M`burada `cy(i)` değerine sahip `1` varsa `x(i - S) - x(i - R) - cy(i - 1) < 0`, aksi takdirde `0`, ve `M` değerine sahip `2` <sup>W</sup>. Altyapının durumu olan bir taşıma göstergesi artı *R* değerleri. Bu değerler son oluşur *R* değerleri döndürülen if `operator()` en az adlı *R* zaman, aksi takdirde `N` geri dönmüş olan değerleri ve son `R - N` Çekirdek değerleri.

Şablon bağımsız değişkeni `UIntType` değerleri içerebilecek kadar büyük olmalıdır `M - 1`.

Doğrudan bu altyapısından bir oluşturucuyu oluşturmak olsa da, önceden tanımlanmış bu tür tanımlarından birini de kullanabilirsiniz:

`ranlux24_base`: Bir temeli olarak kullanılan `ranlux24`.
`typedef subtract_with_carry_engine<unsigned int, 24, 10, 24> ranlux24_base;`

`ranlux48_base`: Bir temeli olarak kullanılan `ranlux48`.
`typedef subtract_with_carry_engine<unsigned long long, 48, 5, 12> ranlux48_base;`

Wikipedia makalesinin carry altyapısı algoritmayla subract hakkında ayrıntılı bilgi için bkz. [Geciktirmiştir Fibonacci Oluşturucu](https://en.wikipedia.org/wiki/Lagged_Fibonacci_generator).

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<rastgele >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[\<rastgele >](../standard-library/random.md)<br/>
