---
description: 'Hakkında daha fazla bilgi edinin: is_trivially_default_constructible sınıfı'
title: is_trivially_default_constructible Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_default_constructible
helpviewer_keywords:
- is_trivially_default_constructible
ms.assetid: 653ecd73-909f-4dd8-b95a-d1164d1c2da4
ms.openlocfilehash: 3686dab86b8bf04fe7629b53651988d7ccef161e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118413"
---
# <a name="is_trivially_default_constructible-class"></a>is_trivially_default_constructible Sınıfı

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

*Tür değeri* önemsiz Oluşturucusu olan bir sınıfdaysa, tür koşulu true, aksi takdirde false barındırır.

Bir sınıf *Ty* için varsayılan Oluşturucu şu durumlarda önemsiz:

- örtülü olarak tanımlanmış bir varsayılan Oluşturucu

- sınıf *Ty* 'nin sanal işlevleri yok

- sınıf *Ty* 'nin sanal tabanı yok

- sınıf *Ty* 'nin tüm doğrudan temellerine önemsiz oluşturucular var

- sınıf türündeki tüm statik olmayan veri üyelerinin sınıfları, önemsiz oluşturuculara sahiptir

- Sınıf dizisi türündeki tüm statik olmayan veri üyelerinin sınıfları, önemsiz oluşturuculara sahiptir

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
