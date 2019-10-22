---
title: is_trivially_move_assignable sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_move_assignable
helpviewer_keywords:
- is_trivially_move_assignable
ms.assetid: 374f7322-0706-4bc1-a1a5-4191d0315e28
ms.openlocfilehash: 4b349d328da995105a6217f4ab597da5d7eafc38
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689498"
---
# <a name="is_trivially_move_assignable-class"></a>is_trivially_move_assignable sınıfı

Türün bir önemsiz taşıma atama işlecine sahip olup olmadığını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_trivially_move_assignable;
```

### <a name="parameters"></a>Parametreler

*Ty* \
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

*Tür değeri* , önemsiz taşıma atama operatörü olan bir sınıfdaysa, tür koşulu true, aksi takdirde false barındırır.

Sınıf *Ty* için bir taşıma atama işleci şu durumlarda önemsiz:

- örtülü olarak sağlanır
- sınıf *Ty* 'nin sanal işlevleri yok
- sınıf *Ty* 'nin sanal tabanı yok
- sınıf türündeki tüm statik olmayan veri üyelerinin sınıfları, önemsiz taşıma atama işleçlerine sahiptir
- Sınıf dizisi türündeki tüm statik olmayan veri üyelerinin sınıfları, önemsiz taşıma atama işleçlerine sahiptir

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
