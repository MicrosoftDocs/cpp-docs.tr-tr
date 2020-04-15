---
title: CComAllocator Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComAllocator
- ATLBASE/ATL::CComAllocator
- ATLBASE/ATL::CComAllocator::Allocate
- ATLBASE/ATL::CComAllocator::Free
- ATLBASE/ATL::CComAllocator::Reallocate
helpviewer_keywords:
- CComAllocator class
ms.assetid: 0cd706fd-0c7b-42d3-9054-febe2966fc8e
ms.openlocfilehash: 165cdb8b0b16a4872214f4556c26ee141e6a4d89
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321146"
---
# <a name="ccomallocator-class"></a>CComAllocator Sınıfı

Bu sınıf, COM bellek yordamlarını kullanarak belleği yönetmek için yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CComAllocator
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CComAllocator::Ayırma](#allocate)|Bellek ayırmak için bu statik yöntemi çağırın.|
|[CComAllocator::Ücretsiz](#free)|Ayrılan belleği serbest yapmak için bu statik yöntemi çağırın.|
|[CComAllocator::Yer tahsisi](#reallocate)|Belleği yeniden tahsis etmek için bu statik yöntemi arayın.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, Com bellek ayırma yordamları sağlamak için [CComHeapPtr](../../atl/reference/ccomheapptr-class.md) tarafından kullanılır. Muadili sınıf, [CCRTAllocator](../../atl/reference/ccrtallocator-class.md), CRT yordamları kullanarak aynı yöntemleri sağlar.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase.h

## <a name="ccomallocatorallocate"></a><a name="allocate"></a>CComAllocator::Ayırma

Belleği ayırmak için bu statik işlevi çağırın.

```
static void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>Parametreler

*nBayt*<br/>
Tahsis edilebilen bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Boş bir işaretçiyi ayrılan alana döndürür veya boş bellek varsa NULL.

### <a name="remarks"></a>Açıklamalar

Belleği ayırır. Daha fazla bilgi için [CoTaskMemAlloc'a](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemalloc) bakın.

## <a name="ccomallocatorfree"></a><a name="free"></a>CComAllocator::Ücretsiz

Bu statik işlevi serbest ayrılmış belleğe çağırın.

```
static void Free(void* p) throw();
```

### <a name="parameters"></a>Parametreler

*P*<br/>
Ayrılan belleğe işaretçi.

### <a name="remarks"></a>Açıklamalar

Ayrılan belleği serbest eder. Daha fazla bilgi için [CoTaskMemFree](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemfree) bakın.

## <a name="ccomallocatorreallocate"></a><a name="reallocate"></a>CComAllocator::Yer tahsisi

Belleği yeniden tahsis etmek için bu statik işlevi çağırın.

```
static void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>Parametreler

*P*<br/>
Ayrılan belleğe işaretçi.

*nBayt*<br/>
Tahsis etmek için bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Boş bir işaretçiyi ayrılan alana döndürür veya yetersiz bellek varsa NULL

### <a name="remarks"></a>Açıklamalar

Ayrılan bellek miktarını yeniden boyutlandırır. Daha fazla bilgi için [CoTaskMemRealloc'a](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemrealloc) bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CComHeapPtr Sınıfı](../../atl/reference/ccomheapptr-class.md)<br/>
[CCRTAllocator Sınıfı](../../atl/reference/ccrtallocator-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
