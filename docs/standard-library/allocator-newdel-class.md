---
title: allocator_newdel Sınıfı
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::allocators::allocator_newdel
- allocators/stdext::allocator_newdel
- stdext::allocators::allocator_newdel
helpviewer_keywords:
- stdext::allocators [C++], allocator_newdel
- stdext::allocator_newdel
ms.assetid: 62666cd2-3afe-49f7-9dd1-9bbbb154da98
ms.openlocfilehash: 30e0f7902a8af435b46aaedf0b38661b7a6604a8
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88562603"
---
# <a name="allocator_newdel-class"></a>allocator_newdel Sınıfı

Bellek bloğunu serbest bırakmak için **operator delete** kullanan bir ayırıcı uygular ve **Yeni işleci** bir bellek bloğu ayırır.

## <a name="syntax"></a>Söz dizimi

```cpp
template <class Type>
class allocator_newdel;
```

### <a name="parameters"></a>Parametreler

*Türüyle*\
Ayırıcı tarafından ayrılan öğelerin türü.

## <a name="remarks"></a>Açıklamalar

[ALLOCATOR_DECL](allocators-functions.md#allocator_decl) makro bu sınıfı aşağıdaki deyimdeki *Name* parametresi olarak geçirir:`ALLOCATOR_DECL(CACHE_FREELIST stdext::allocators::max_none), SYNC_DEFAULT, allocator_newdel);`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<allocators>

**Ad alanı:** stdext

## <a name="see-also"></a>Ayrıca bkz.

[\<allocators>](allocators-header.md)
