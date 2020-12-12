---
description: 'Hakkında daha fazla bilgi edinin: allocator_suballoc sınıfı'
title: allocator_suballoc Sınıfı
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::allocators::allocator_suballoc
- allocators/stdext::allocator_suballoc
helpviewer_keywords:
- allocator_suballoc class
ms.assetid: 50c6a5c0-d00d-4276-9285-d908fd4f6483
ms.openlocfilehash: 7e542b4b8f419f1ac219c63b113aced7e0bd7cda
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163593"
---
# <a name="allocator_suballoc-class"></a>allocator_suballoc Sınıfı

[Cache_suballoc](cache-suballoc-class.md) *türünde bir önbellek kullanarak tür* nesneleri için depolama ayırmayı ve boşaltmayı yöneten bir nesneyi tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type>
class allocator_suballoc;
```

### <a name="parameters"></a>Parametreler

*Türüyle*\
Ayırıcı tarafından ayrılan öğelerin türü.

## <a name="remarks"></a>Açıklamalar

[ALLOCATOR_DECL](allocators-functions.md#allocator_decl) makro bu sınıfı aşağıdaki deyimdeki *Name* parametresi olarak geçirir:`ALLOCATOR_DECL(CACHE_SUBALLOC, SYNC_DEFAULT, allocator_suballoc);`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<allocators>

**Ad alanı:** stdext

## <a name="see-also"></a>Ayrıca bkz.

[\<allocators>](allocators-header.md)
