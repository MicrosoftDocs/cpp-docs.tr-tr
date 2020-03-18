---
title: '&lt;rastgele&gt; işlevleri'
ms.date: 09/04/2019
f1_keywords:
- random/std::generate_canonical
ms.assetid: 2ac9ec59-619b-4b85-a425-f729277c1bc8
helpviewer_keywords:
- std::generate_canonical
ms.openlocfilehash: 3d94f607fc6b7bdf22d7f573f590b451dbaa718d
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79419646"
---
# <a name="ltrandomgt-functions"></a>&lt;rastgele&gt; işlevleri

## <a name="generate_canonical"></a>generate_canonical

Rastgele bir dizideki kayan nokta değeri döndürür.

```cpp
template <class RealType, size_t Bits, class Generator>
RealType generate_canonical(Generator& Gen);
```

### <a name="parameters"></a>Parametreler

*RealType*\
Kayan nokta integral türü. Olası türler için bkz. [\<rastgele >](../standard-library/random.md).

*Bıts*\
Kullanılacak rasgelelik bit sayısı.

*Oluşturucu*\
Rastgele bir sayı Oluşturucu sınıfı.

*Gen*\
Tür *oluşturucusunun*rastgele sayı oluşturucusunun bir örneğine başvuru.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi *, sürekli olarak* `operator()` çağırır ve döndürülen değerleri, `x`belirtilen sayıda mantis bitleri toplanana kadar *RealType* türünde bir kayan nokta değerine `x`. Belirtilen sayı, *bitlerin* (sıfırdan farklı olması gerekir) ve *RealType*içindeki Mantis bitlerinin tam sayısı kadar küçüktür. İlk çağrı en düşük sıralı bitleri sağlar. İşlev `x`döndürür.
