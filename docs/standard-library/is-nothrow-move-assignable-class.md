---
title: is_nothrow_move_assignable sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_move_assignable
helpviewer_keywords:
- is_nothrow_move_assignable
ms.assetid: 000baa02-cbba-49de-9870-af730033348e
ms.openlocfilehash: 92e3364843b5614c9fa108d33605b35962726aa2
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217746"
---
# <a name="is_nothrow_move_assignable-class"></a>is_nothrow_move_assignable sınıfı

Türün bir **`nothrow`** taşıma ataması operatörüne sahip olup olmadığını sınar.

## <a name="syntax"></a>Söz dizimi

```cpp
template <class Ty>
struct is_nothrow_move_assignable;
```

### <a name="parameters"></a>Parametreler

*Kalite*\
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

*Tür olarak* bir nothrow taşıma atama işleci varsa, tür koşulunda bir örnek true, aksi takdirde false barındırır.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
