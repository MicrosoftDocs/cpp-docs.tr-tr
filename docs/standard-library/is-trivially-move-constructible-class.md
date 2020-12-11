---
description: 'Hakkında daha fazla bilgi edinin: is_trivially_move_constructible sınıfı'
title: is_trivially_move_constructible sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_move_constructible
helpviewer_keywords:
- is_trivially_move_constructible
ms.assetid: 740bdec7-65e5-47b3-b94f-a2479ceac3ec
ms.openlocfilehash: 30e8be25e74aeed1eafc8fcafbece5c62e4ad999
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154324"
---
# <a name="is_trivially_move_constructible-class"></a>is_trivially_move_constructible sınıfı

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

*Tür değeri* , önemsiz bir taşıma oluşturucusuna sahip bir sınıfdaysa, tür belirtiminin bir örneği true, aksi takdirde false değerini taşır.

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

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
