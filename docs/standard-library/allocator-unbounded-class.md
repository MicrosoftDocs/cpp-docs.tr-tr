---
description: 'Hakkında daha fazla bilgi edinin: allocator_unbounded sınıfı'
title: allocator_unbounded Sınıfı
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::allocator_unbounded
- allocators/stdext::allocators::allocator_unbounded
helpviewer_keywords:
- allocator_unbounded class
ms.assetid: facbaea1-b320-4d99-96da-039b2642f352
ms.openlocfilehash: 6d046aa08ddd366c7e7009d1d93c36a365d98170
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163554"
---
# <a name="allocator_unbounded-class"></a>allocator_unbounded Sınıfı

[Max_unbounded](max-unbounded-class.md)tarafından yönetilen uzunluğa sahip [cache_freelist](cache-freelist-class.md) *türünde bir önbellek kullanarak türünde* nesneler için depolama ayırmayı ve boşaltmayı yöneten bir nesneyi tanımlar.

## <a name="syntax"></a>Sözdizimi

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
