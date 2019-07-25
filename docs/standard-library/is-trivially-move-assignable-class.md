---
title: is_trivially_move_assignable sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_move_assignable
helpviewer_keywords:
- is_trivially_move_assignable
ms.assetid: 374f7322-0706-4bc1-a1a5-4191d0315e28
ms.openlocfilehash: 324e4a1f1bd3528f09f21c5e485ac814038b7517
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448376"
---
# <a name="istriviallymoveassignable-class"></a>is_trivially_move_assignable sınıfı

Türün bir önemsiz taşıma atama işlecine sahip olup olmadığını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_trivially_move_assignable;
```

### <a name="parameters"></a>Parametreler

*Kalite*\
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Tür değeri, önemsiz taşıma atama operatörü olan bir sınıfdaysa  , tür koşulu true, aksi takdirde false barındırır.

Sınıf *Ty* için bir taşıma atama işleci şu durumlarda önemsiz:

örtülü olarak sağlanır

sınıf *Ty* 'nin sanal işlevleri yok

sınıf *Ty* 'nin sanal tabanı yok

sınıf türündeki tüm statik olmayan veri üyelerinin sınıfları, önemsiz taşıma atama işleçlerine sahiptir

Sınıf dizisi türündeki tüm statik olmayan veri üyelerinin sınıfları, önemsiz taşıma atama işleçlerine sahiptir

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
