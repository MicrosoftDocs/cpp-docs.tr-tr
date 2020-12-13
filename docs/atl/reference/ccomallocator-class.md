---
description: 'Daha fazla bilgi edinin: Ccomayırıcı sınıfı'
title: Ccomayırıcı sınıfı
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
ms.openlocfilehash: 886692f6a55ac096e51fd6888f941d63bf089263
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146958"
---
# <a name="ccomallocator-class"></a>Ccomayırıcı sınıfı

Bu sınıf, COM bellek yordamlarını kullanarak belleği yönetmek için yöntemler sağlar.

## <a name="syntax"></a>Syntax

```
class CComAllocator
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Ccomayırıcısı:: allocate](#allocate)|Bellek ayırmak için bu statik yöntemi çağırın.|
|[Ccomayırıcısı:: Free](#free)|Ayrılmış belleği serbest bırakmak için bu statik yöntemi çağırın.|
|[Ccomayırıcı:: yeniden tahsis](#reallocate)|Belleği yeniden ayırmak için bu statik yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, [CComHeapPtr](../../atl/reference/ccomheapptr-class.md) tarafından com bellek ayırma yordamlarını sağlamak için kullanılır. Karşılık gelen Class, [CCRTAllocator](../../atl/reference/ccrtallocator-class.md), CRT yordamlarını kullanarak aynı yöntemleri sağlar.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="ccomallocatorallocate"></a><a name="allocate"></a> Ccomayırıcısı:: allocate

Bellek ayırmak için bu statik işlevi çağırın.

```
static void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>Parametreler

*nBytes*<br/>
Ayrılacak bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Ayrılan alana void bir işaretçi döndürür ya da kullanılabilir bellek yetersizse boş değer yok.

### <a name="remarks"></a>Açıklamalar

Belleği ayırır. Daha fazla ayrıntı için bkz. [CoTaskMemAlloc](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemalloc) .

## <a name="ccomallocatorfree"></a><a name="free"></a> Ccomayırıcısı:: Free

Ayrılmış belleği serbest bırakmak için bu statik işlevi çağırın.

```
static void Free(void* p) throw();
```

### <a name="parameters"></a>Parametreler

*Lama*<br/>
Ayrılan belleğe yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Ayrılan belleği serbest bırakır. Daha fazla ayrıntı için bkz. [CoTaskMemFree](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemfree) .

## <a name="ccomallocatorreallocate"></a><a name="reallocate"></a> Ccomayırıcı:: yeniden tahsis

Belleği yeniden ayırmak için bu statik işlevi çağırın.

```
static void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>Parametreler

*Lama*<br/>
Ayrılan belleğe yönelik işaretçi.

*nBytes*<br/>
Yeniden ayrılacak bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Ayrılan alana void bir işaretçi döndürür ya da bellek yetersizse NULL

### <a name="remarks"></a>Açıklamalar

Ayrılan bellek miktarını yeniden boyutlandırır. Daha fazla ayrıntı için bkz. [CoTaskMemRealloc](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemrealloc) .

## <a name="see-also"></a>Ayrıca bkz.

[CComHeapPtr sınıfı](../../atl/reference/ccomheapptr-class.md)<br/>
[CCRTAllocator sınıfı](../../atl/reference/ccrtallocator-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
