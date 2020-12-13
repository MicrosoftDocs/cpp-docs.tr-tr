---
description: 'Daha fazla bilgi edinin: CCRTAllocator sınıfı'
title: CCRTAllocator sınıfı
ms.date: 11/04/2016
f1_keywords:
- CCRTAllocator
- ATLCORE/ATL::CCRTAllocator
- ATLCORE/ATL::CCRTAllocator::Allocate
- ATLCORE/ATL::CCRTAllocator::Free
- ATLCORE/ATL::CCRTAllocator::Reallocate
helpviewer_keywords:
- CCRTAllocator class
ms.assetid: 3e1b8cb0-859a-41ab-8e93-6f0b5ceca49d
ms.openlocfilehash: 378a1c27a6c2dde9fbcb24eb9b51b64c3af7e8aa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142070"
---
# <a name="ccrtallocator-class"></a>CCRTAllocator sınıfı

Bu sınıf, CRT bellek yordamlarını kullanarak belleği yönetmek için yöntemler sağlar.

## <a name="syntax"></a>Syntax

```
class ATL::CCRTAllocator
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CCRTAllocator:: ayır](#allocate)|Se Bellek ayırmak için bu yöntemi çağırın.|
|[CCRTAllocator:: ücretsiz](#free)|Se Belleği boşaltmak için bu yöntemi çağırın.|
|[CCRTAllocator:: yeniden tahsis](#reallocate)|Se Belleği yeniden ayırmak için bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, bir, CRT bellek ayırma yordamlarını sağlamak için [CHeapPtr](../../atl/reference/cheapptr-class.md) tarafından kullanılır. Karşılık gelen sınıf olan [Ccomayırıcısı](../../atl/reference/ccomallocator-class.md), com yordamlarını kullanarak aynı yöntemleri sağlar.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcore. h

## <a name="ccrtallocatorallocate"></a><a name="allocate"></a> CCRTAllocator:: ayır

Bellek ayırmak için bu statik işlevi çağırın.

```
static __declspec(allocator) void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>Parametreler

*nBytes*<br/>
Ayrılacak bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Ayrılan alana void bir işaretçi döndürür ya da kullanılabilir bellek yetersizse boş değer yok.

### <a name="remarks"></a>Açıklamalar

Belleği ayırır. Daha fazla ayrıntı için bkz. [malloc](../../c-runtime-library/reference/malloc.md) .

## <a name="ccrtallocatorfree"></a><a name="free"></a> CCRTAllocator:: ücretsiz

Belleği boşaltmak için bu statik işlevi çağırın.

```
static void Free(void* p) throw();
```

### <a name="parameters"></a>Parametreler

*Lama*<br/>
Ayrılan belleğe yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Ayrılan belleği serbest bırakır. Daha ayrıntılı bilgi için bkz. [ücretsiz](../../c-runtime-library/reference/free.md) .

## <a name="ccrtallocatorreallocate"></a><a name="reallocate"></a> CCRTAllocator:: yeniden tahsis

Belleği yeniden ayırmak için bu statik işlevi çağırın.

```
static __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>Parametreler

*Lama*<br/>
Ayrılan belleğe yönelik işaretçi.

*nBytes*<br/>
Yeniden ayrılacak bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Ayrılan alana void bir işaretçi döndürür veya yetersiz bellek varsa NULL değeri döndürür.

### <a name="remarks"></a>Açıklamalar

Ayrılan bellek miktarını yeniden boyutlandırır. Daha fazla ayrıntı için bkz. [realloc](../../c-runtime-library/reference/realloc.md) .

## <a name="see-also"></a>Ayrıca bkz.

[CHeapPtr sınıfı](../../atl/reference/cheapptr-class.md)<br/>
[Ccomayırıcı sınıfı](../../atl/reference/ccomallocator-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
