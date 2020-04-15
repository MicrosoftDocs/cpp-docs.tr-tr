---
title: CCRTAllocator Sınıfı
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
ms.openlocfilehash: 2f6bae3818fa0f1639e0e3cee4e09121580da768
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327175"
---
# <a name="ccrtallocator-class"></a>CCRTAllocator Sınıfı

Bu sınıf, CRT bellek yordamlarını kullanarak bellek yönetmek için yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
class ATL::CCRTAllocator
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CCRTAllocator::Ayırma](#allocate)|(Statik) Bellek ayırmak için bu yöntemi arayın.|
|[CCRTAllocator::Ücretsiz](#free)|(Statik) Bu yöntemi boş bellek için arayın.|
|[CCRTAllocator::Yeniden tahsis](#reallocate)|(Statik) Belleği yeniden tahsis etmek için bu yöntemi arayın.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, CRT bellek ayırma yordamları sağlamak için [CHeapPtr](../../atl/reference/cheapptr-class.md) tarafından kullanılır. Muhatap sınıf, [CComAllocator](../../atl/reference/ccomallocator-class.md), COM yordamları kullanarak aynı yöntemleri sağlar.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcore.h

## <a name="ccrtallocatorallocate"></a><a name="allocate"></a>CCRTAllocator::Ayırma

Belleği ayırmak için bu statik işlevi çağırın.

```
static __declspec(allocator) void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>Parametreler

*nBayt*<br/>
Tahsis edilebilen bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Boş bir işaretçiyi ayrılan alana döndürür veya boş bellek varsa NULL.

### <a name="remarks"></a>Açıklamalar

Belleği ayırır. Daha fazla bilgi için [malloc](../../c-runtime-library/reference/malloc.md) bakın.

## <a name="ccrtallocatorfree"></a><a name="free"></a>CCRTAllocator::Ücretsiz

Bu statik işlevi boş bellek için çağırın.

```
static void Free(void* p) throw();
```

### <a name="parameters"></a>Parametreler

*P*<br/>
Ayrılan belleğe işaretçi.

### <a name="remarks"></a>Açıklamalar

Ayrılan belleği serbest eder. Daha fazla bilgi için [ücretsiz](../../c-runtime-library/reference/free.md) bakın.

## <a name="ccrtallocatorreallocate"></a><a name="reallocate"></a>CCRTAllocator::Yeniden tahsis

Belleği yeniden tahsis etmek için bu statik işlevi çağırın.

```
static __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>Parametreler

*P*<br/>
Ayrılan belleğe işaretçi.

*nBayt*<br/>
Tahsis etmek için bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Boş bir işaretçiyi ayrılan alana veya yetersiz bellek varsa NULL'a döndürür.

### <a name="remarks"></a>Açıklamalar

Ayrılan bellek miktarını yeniden boyutlandırır. Daha fazla bilgi için [realloc](../../c-runtime-library/reference/realloc.md) bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CHeapPtr Sınıfı](../../atl/reference/cheapptr-class.md)<br/>
[CComAllocator Sınıfı](../../atl/reference/ccomallocator-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
