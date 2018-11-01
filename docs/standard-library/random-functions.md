---
title: '&lt;rastgele&gt; işlevleri'
ms.date: 11/04/2016
f1_keywords:
- random/std::generate_canonical
ms.assetid: 2ac9ec59-619b-4b85-a425-f729277c1bc8
helpviewer_keywords:
- std::generate_canonical
ms.openlocfilehash: 80bdb1ca83be5fb390035d7f3b005793a2f03715
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50520620"
---
# <a name="ltrandomgt-functions"></a>&lt;rastgele&gt; işlevleri

## <a name="generate_canonical"></a>  generate_canonical

Rastgele bir diziden bir kayan nokta değeri döndürür.

> [!NOTE]
> ISO C++ standardı bu işlev aralıktaki değerler döndürmesi gerektiğini belirten [ `0`, `1`). Visual Studio henüz Bu kısıtlamayla uyumlu değil. Bu aralıkta değerler oluşturmak için geçici bir çözüm olarak, [uniform_real_distribution](../standard-library/uniform-real-distribution-class.md).

```cpp
template <class RealType, size_t Bits, class Generator>
RealType generate_canonical(Generator& Gen);
```

### <a name="parameters"></a>Parametreler

*RealType*<br/>
Kayan nokta integral türü. Olası türleri için bkz: [ \<rastgele >](../standard-library/random.md).

*BITS*<br/>
Rasgele sayı üreteci.

*Genel*<br/>
Rasgele sayı üreteci.

### <a name="remarks"></a>Açıklamalar

Şablonu işlev çağrıları `operator()` , *Gen* sürekli ve döndürülen değerlerin bir kayan nokta değerine paketleri `x` türü *RealType* belirtilen sayı topladı kadar içinde Mantis bit `x`. Belirtilen sayı olan daha küçük olan *BITS* (olması gereken sıfır olmayan) ve tam Mantis bit sayısı *RealType*. İlk çağrı, en düşük sıralı BITS sağlar. İşlev döndürür `x`.

## <a name="see-also"></a>Ayrıca bkz.

[\<rastgele >](../standard-library/random.md)<br/>
