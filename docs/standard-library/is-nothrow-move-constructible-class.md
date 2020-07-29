---
title: is_nothrow_move_constructible Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_move_constructible
helpviewer_keywords:
- is_nothrow_move_constructible
ms.assetid: d186d97b-7b89-470a-8d30-993046a83379
ms.openlocfilehash: 115a1b6c2157a139786c0b8762a9a614bbcd6deb
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217733"
---
# <a name="is_nothrow_move_constructible-class"></a>is_nothrow_move_constructible Sınıfı

Türün bir taşıma oluşturucusuna sahip olup olmadığını sınar **`nothrow`** .

## <a name="syntax"></a>Söz dizimi

```cpp
template <class Ty>
struct is_nothrow_move_constructible;
```

### <a name="parameters"></a>Parametreler

*Kalite*\
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Tür kümesi bir nothrow taşıma *oluşturucusuna sahipse,* tür koşulunun bir örneği true, aksi takdirde false değerini taşır.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
