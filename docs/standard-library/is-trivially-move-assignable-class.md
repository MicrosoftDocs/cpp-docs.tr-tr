---
description: 'Hakkında daha fazla bilgi edinin: is_trivially_move_assignable sınıfı'
title: is_trivially_move_assignable sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_move_assignable
helpviewer_keywords:
- is_trivially_move_assignable
ms.assetid: 374f7322-0706-4bc1-a1a5-4191d0315e28
ms.openlocfilehash: 3f852bd2b1ccf3647a4aa05bb5996f015341b342
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154337"
---
# <a name="is_trivially_move_assignable-class"></a>is_trivially_move_assignable sınıfı

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

*Tür değeri* , önemsiz taşıma atama operatörü olan bir sınıfdaysa, tür koşulu true, aksi takdirde false barındırır.

Sınıf *Ty* için bir taşıma atama işleci şu durumlarda önemsiz:

- örtülü olarak sağlanır
- sınıf *Ty* 'nin sanal işlevleri yok
- sınıf *Ty* 'nin sanal tabanı yok
- sınıf türündeki tüm statik olmayan veri üyelerinin sınıfları, önemsiz taşıma atama işleçlerine sahiptir
- Sınıf dizisi türündeki tüm statik olmayan veri üyelerinin sınıfları, önemsiz taşıma atama işleçlerine sahiptir

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
