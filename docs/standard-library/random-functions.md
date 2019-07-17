---
title: '&lt;rastgele&gt; işlevleri'
ms.date: 11/04/2016
f1_keywords:
- random/std::generate_canonical
ms.assetid: 2ac9ec59-619b-4b85-a425-f729277c1bc8
helpviewer_keywords:
- std::generate_canonical
ms.openlocfilehash: 87b640d4f3aa3fbfa23ad5603d84102301e71ea4
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68240382"
---
# <a name="ltrandomgt-functions"></a>&lt;rastgele&gt; işlevleri

## <a name="generate_canonical"></a> generate_canonical

Rastgele bir diziden bir kayan nokta değeri döndürür.

> [!NOTE]
> ISO C++ standart, bu işlev aralığında değerlerini döndürmesi gereken durumları [ `0`, `1`). Visual Studio henüz Bu kısıtlamayla uyumlu değil. Bu aralıkta değerler oluşturmak için geçici bir çözüm olarak, [uniform_real_distribution](../standard-library/uniform-real-distribution-class.md).

```cpp
template <class RealType, size_t Bits, class Generator>
RealType generate_canonical(Generator& Gen);
```

### <a name="parameters"></a>Parametreler

*RealType*\
Kayan nokta integral türü. Olası türleri için bkz: [ \<rastgele >](../standard-library/random.md).

*BITS*\
Rasgele sayı üreteci.

*Genel*\
Rasgele sayı üreteci.

### <a name="remarks"></a>Açıklamalar

Şablonu işlev çağrıları `operator()` , *Gen* sürekli ve döndürülen değerlerin bir kayan nokta değerine paketleri `x` türü *RealType* belirtilen sayı topladı kadar içinde Mantis bit `x`. Belirtilen sayı olan daha küçük olan *BITS* (olması gereken sıfır olmayan) ve tam Mantis bit sayısı *RealType*. İlk çağrı, en düşük sıralı BITS sağlar. İşlev döndürür `x`.
