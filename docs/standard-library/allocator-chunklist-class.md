---
title: allocator_chunklist Sınıfı
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::allocator_chunklist
- allocators/stdext::allocators::allocator_chunklist
helpviewer_keywords:
- stdext::allocator_chunklist
- stdext::allocators [C++], allocator_chunklist
ms.assetid: ea72ed0a-dfdb-4c8b-8096-e4baf567b80f
ms.openlocfilehash: c2342d068293714871b3f79675dd0d0b9db83448
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84617538"
---
# <a name="allocator_chunklist-class"></a>allocator_chunklist Sınıfı

[Cache_chunklist](cache-chunklist-class.md)türünde bir önbellek kullanarak nesneler için depolama ayırmayı ve boşaltmayı yöneten bir nesneyi tanımlar.

## <a name="syntax"></a>Söz dizimi

```cpp
template <class Type>
class allocator_chunklist;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Tür*|Ayırıcı tarafından ayrılan öğelerin türü.|

## <a name="remarks"></a>Açıklamalar

[ALLOCATOR_DECL](allocators-functions.md#allocator_decl) makro bu sınıfı aşağıdaki deyimdeki *Name* parametresi olarak geçirir:`ALLOCATOR_DECL(CACHE_CHUNKLIST, SYNC_DEFAULT, allocator_chunklist);`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<allocators>

**Ad alanı:** stdext

## <a name="see-also"></a>Ayrıca bkz.

[\<allocators>](allocators-header.md)
