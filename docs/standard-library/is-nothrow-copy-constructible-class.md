---
description: 'Hakkında daha fazla bilgi edinin: is_nothrow_copy_constructible sınıfı'
title: is_nothrow_copy_constructible Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_copy_constructible
helpviewer_keywords:
- is_nothrow_copy_constructible
ms.assetid: f13a0bea-63b1-492a-9a45-d445df35c282
ms.openlocfilehash: b238b86a5780d12dd6c1e62e0b2d79b9fbc139dd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323611"
---
# <a name="is_nothrow_copy_constructible-class"></a>is_nothrow_copy_constructible Sınıfı

Türün bir kopya oluşturucusuna sahip olup olmadığını sınar **`nothrow`** .

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_nothrow_copy_constructible;
```

### <a name="parameters"></a>Parametreler

*Kalite*\
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

*Tür olarak* bir nothrow kopya Oluşturucusu varsa tür koşulunun bir örneği true, aksi takdirde false değerini taşır.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
