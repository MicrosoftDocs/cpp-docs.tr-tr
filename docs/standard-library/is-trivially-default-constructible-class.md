---
title: is_trivially_default_constructible Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_default_constructible
helpviewer_keywords:
- is_trivially_default_constructible
ms.assetid: 653ecd73-909f-4dd8-b95a-d1164d1c2da4
ms.openlocfilehash: 19a5e8afedf3e59d5dafa937af4f7d35343eb7d9
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459649"
---
# <a name="istriviallydefaultconstructible-class"></a>is_trivially_default_constructible Sınıfı

Türün önemsiz varsayılan Oluşturucusu varsa sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_trivially_default_constructible;
```

### <a name="parameters"></a>Parametreler

*Kalite*\
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Tür değeri önemsiz Oluşturucusu olan bir sınıfdaysa, tür koşulu  true, aksi takdirde false barındırır.

Bir sınıf *Ty* için varsayılan Oluşturucu şu durumlarda önemsiz:

- örtülü olarak tanımlanmış bir varsayılan Oluşturucu

- sınıf *Ty* 'nin sanal işlevleri yok

- sınıf *Ty* 'nin sanal tabanı yok

- sınıf *Ty* 'nin tüm doğrudan temellerine önemsiz oluşturucular var

- sınıf türündeki tüm statik olmayan veri üyelerinin sınıfları, önemsiz oluşturuculara sahiptir

- Sınıf dizisi türündeki tüm statik olmayan veri üyelerinin sınıfları, önemsiz oluşturuculara sahiptir

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
