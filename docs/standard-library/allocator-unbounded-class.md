---
title: allocator_unbounded Sınıfı
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::allocator_unbounded
- allocators/stdext::allocators::allocator_unbounded
helpviewer_keywords:
- allocator_unbounded class
ms.assetid: facbaea1-b320-4d99-96da-039b2642f352
ms.openlocfilehash: 38ecec3848808585ac0ed7cb1b076480a79f6d41
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448294"
---
# <a name="allocatorunbounded-class"></a>allocator_unbounded Sınıfı

[Max_unbounded](../standard-library/max-unbounded-class.md)tarafından yönetilen bir uzunluğa sahip [cache_freelist](../standard-library/cache-freelist-class.md) türünde bir *önbellek kullanarak tür* nesneleri için depolama ayırmayı ve boşaltmayı yöneten bir nesneyi tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type>
class allocator_unbounded;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Tür*|Ayırıcı tarafından ayrılan öğelerin türü.|

## <a name="remarks"></a>Açıklamalar

[ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) makrosu, bu sınıfı aşağıdaki deyimdeki *Name* parametresi olarak geçirir:`ALLOCATOR_DECL(CACHE_FREELIST(stdext::allocators::max_unbounded), SYNC_DEFAULT, allocator_unbounded);`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<ayrıcılar >

**Ad alanı:** stdext

## <a name="see-also"></a>Ayrıca bkz.

[\<ayrıcılar >](../standard-library/allocators-header.md)
