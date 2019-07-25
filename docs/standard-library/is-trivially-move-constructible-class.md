---
title: is_trivially_move_constructible sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_move_constructible
helpviewer_keywords:
- is_trivially_move_constructible
ms.assetid: 740bdec7-65e5-47b3-b94f-a2479ceac3ec
ms.openlocfilehash: 279da956eaff21c39c6e5ca563f26989105f7e74
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448368"
---
# <a name="istriviallymoveconstructible-class"></a>is_trivially_move_constructible sınıfı

Türün önemsiz taşıma Oluşturucusu varsa sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_trivially_move_constructible;
```

### <a name="parameters"></a>Parametreler

*Kalite*\
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Tür değeri, önemsiz bir taşıma oluşturucusuna sahip bir sınıfdaysa  , tür belirtiminin bir örneği true, aksi takdirde false değerini taşır.

Sınıf *Ty* için bir taşıma Oluşturucusu şu durumlarda önemsiz:

örtülü olarak bildirilmiştir

parametre türleri örtük bildirimdekilerle eşdeğerdir

sınıf *Ty* 'nin sanal işlevleri yok

sınıf *Ty* 'nin sanal tabanı yok

sınıfta geçici bir statik olmayan veri üyesi yok

sınıf *Ty* 'nin tüm doğrudan temellerine önemsiz taşıma oluşturucuları sahiptir

sınıf türündeki tüm statik olmayan veri üyelerinin sınıfları, önemsiz taşıma oluşturuculara sahiptir

Sınıf dizisi türündeki tüm statik olmayan veri üyelerinin sınıfları, önemsiz taşıma oluşturuculara sahiptir

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
