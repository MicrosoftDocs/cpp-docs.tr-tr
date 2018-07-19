---
title: '&lt;rastgele&gt; işlevleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- random/std::generate_canonical
ms.assetid: 2ac9ec59-619b-4b85-a425-f729277c1bc8
helpviewer_keywords:
- std::generate_canonical
ms.openlocfilehash: 5b0cd634dad099669d803d4a2717fc9198151781
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38954164"
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

*RealType* kayan nokta integral türü. Olası türleri için bkz: [ \<rastgele >](../standard-library/random.md).

*BITS* rasgele sayı üreteci.

*Gen* rasgele sayı üreteci.

### <a name="remarks"></a>Açıklamalar

Şablonu işlev çağrıları `operator()` , *Gen* sürekli ve döndürülen değerlerin bir kayan nokta değerine paketleri `x` türü *RealType* belirtilen sayı topladı kadar içinde Mantis bit `x`. Belirtilen sayı olan daha küçük olan *BITS* (olması gereken sıfır olmayan) ve tam Mantis bit sayısı *RealType*. İlk çağrı, en düşük sıralı BITS sağlar. İşlev döndürür `x`.

## <a name="see-also"></a>Ayrıca bkz.

[\<rastgele >](../standard-library/random.md)<br/>
