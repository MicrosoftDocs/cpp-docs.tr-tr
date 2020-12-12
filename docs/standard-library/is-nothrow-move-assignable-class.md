---
description: 'Hakkında daha fazla bilgi edinin: is_nothrow_move_assignable sınıfı'
title: is_nothrow_move_assignable sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_move_assignable
helpviewer_keywords:
- is_nothrow_move_assignable
ms.assetid: 000baa02-cbba-49de-9870-af730033348e
ms.openlocfilehash: 77d61ff79d56ff1caee2d856ac4d947821c16946
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230763"
---
# <a name="is_nothrow_move_assignable-class"></a>is_nothrow_move_assignable sınıfı

Türün bir **`nothrow`** taşıma ataması operatörüne sahip olup olmadığını sınar.

## <a name="syntax"></a>Sözdizimi

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
