---
title: allocator_unbounded Sınıfı
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::allocator_unbounded
- allocators/stdext::allocators::allocator_unbounded
helpviewer_keywords:
- allocator_unbounded class
ms.assetid: facbaea1-b320-4d99-96da-039b2642f352
ms.openlocfilehash: d9d82dd29ab86654020e13b39a8c9588ee0732e8
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88561550"
---
# <a name="allocator_unbounded-class"></a>allocator_unbounded Sınıfı

[Max_unbounded](max-unbounded-class.md)tarafından yönetilen uzunluğa sahip [cache_freelist](cache-freelist-class.md) *türünde bir önbellek kullanarak türünde* nesneler için depolama ayırmayı ve boşaltmayı yöneten bir nesneyi tanımlar.

## <a name="syntax"></a>Söz dizimi

```cpp
template <class Type>
class allocator_unbounded;
```

### <a name="parameters"></a>Parametreler

*Türüyle*\
Ayırıcı tarafından ayrılan öğelerin türü.

## <a name="remarks"></a>Açıklamalar

[ALLOCATOR_DECL](allocators-functions.md#allocator_decl) makro bu sınıfı aşağıdaki deyimdeki *Name* parametresi olarak geçirir:`ALLOCATOR_DECL(CACHE_FREELIST(stdext::allocators::max_unbounded), SYNC_DEFAULT, allocator_unbounded);`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<allocators>

**Ad alanı:** stdext

## <a name="see-also"></a>Ayrıca bkz.

[\<allocators>](allocators-header.md)
