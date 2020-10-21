---
title: '&lt;Rastgele &gt; işlevler'
ms.date: 09/04/2019
f1_keywords:
- random/std::generate_canonical
ms.assetid: 2ac9ec59-619b-4b85-a425-f729277c1bc8
helpviewer_keywords:
- std::generate_canonical
ms.openlocfilehash: 3d94f607fc6b7bdf22d7f573f590b451dbaa718d
ms.sourcegitcommit: 19016630f9d35f365e9ba249e0f3617515d7ca33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2020
ms.locfileid: "92274604"
---
# <a name="ltrandomgt-functions"></a>&lt;Rastgele &gt; işlevler

## <a name="generate_canonical"></a><a name="generate_canonical"></a> generate_canonical

Rastgele bir dizideki kayan nokta değeri döndürür.

```cpp
template <class RealType, size_t Bits, class Generator>
RealType generate_canonical(Generator& Gen);
```

### <a name="parameters"></a>Parametreler

*RealType*\
Kayan nokta integral türü. Olası türler için bkz [\<random>](../standard-library/random.md) ..

*Bitlik*\
Kullanılacak rasgelelik bit sayısı.

*Generator*\
Rastgele bir sayı Oluşturucu sınıfı.

*Alanına*\
Tür *oluşturucusunun*rastgele sayı oluşturucusunun bir örneğine başvuru.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi, `operator()` arka arkaya *Gen* ve döndürülen değerleri, `x` içinde belirtilen sayıda mantis bitleri toplanana kadar *RealType* türünde bir kayan nokta değerine paketler `x` . Belirtilen sayı, *bitlerin* (sıfırdan farklı olması gerekir) ve *RealType*içindeki Mantis bitlerinin tam sayısı kadar küçüktür. İlk çağrı en düşük sıralı bitleri sağlar. İşlev döndürür `x` .
