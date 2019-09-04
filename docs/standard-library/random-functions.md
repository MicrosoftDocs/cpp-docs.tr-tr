---
title: '&lt;Rastgele&gt; işlevler'
ms.date: 09/04/2019
f1_keywords:
- random/std::generate_canonical
ms.assetid: 2ac9ec59-619b-4b85-a425-f729277c1bc8
helpviewer_keywords:
- std::generate_canonical
ms.openlocfilehash: 3d94f607fc6b7bdf22d7f573f590b451dbaa718d
ms.sourcegitcommit: fd0f8839da5c6a3663798a47c6b0bb6e63b518bd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70273832"
---
# <a name="ltrandomgt-functions"></a>&lt;Rastgele&gt; işlevler

## <a name="generate_canonical"></a>generate_canonical

Rastgele bir dizideki kayan nokta değeri döndürür.

```cpp
template <class RealType, size_t Bits, class Generator>
RealType generate_canonical(Generator& Gen);
```

### <a name="parameters"></a>Parametreler

*RealType*\
Kayan nokta integral türü. Olası türler için bkz [ \<. Random >](../standard-library/random.md).

*Bitlik*\
Kullanılacak rasgelelik bit sayısı.

*Generator*\
Rastgele bir sayı Oluşturucu sınıfı.

*Alanına*\
Tür *oluşturucusunun*rastgele sayı oluşturucusunun bir örneğine başvuru.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi `operator()` *, arka arkaya* ve döndürülen değerleri, içinde `x` `x`belirtilen sayıda mantis bitleri toplanana kadar *RealType* türünde bir kayan nokta değerine paketler. Belirtilen sayı, *bitlerin* (sıfırdan farklı olması gerekir) ve *RealType*içindeki Mantis bitlerinin tam sayısı kadar küçüktür. İlk çağrı en düşük sıralı bitleri sağlar. İşlev döndürür `x`.
