---
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
ms.openlocfilehash: de302c7a58bf1b15e63e7cd391621ed9558e5a70
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497592"
---
# <a name="ccomallocator-class"></a>Ccomayırıcı sınıfı

Bu sınıf, COM bellek yordamlarını kullanarak belleği yönetmek için yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

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

##  <a name="allocate"></a>Ccomayırıcısı:: allocate

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

##  <a name="free"></a>Ccomayırıcısı:: Free

Ayrılmış belleği serbest bırakmak için bu statik işlevi çağırın.

```
static void Free(void* p) throw();
```

### <a name="parameters"></a>Parametreler

*p*<br/>
Ayrılan belleğe yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Ayrılan belleği serbest bırakır. Daha fazla ayrıntı için bkz. [CoTaskMemFree](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemfree) .

##  <a name="reallocate"></a>Ccomayırıcı:: yeniden tahsis

Belleği yeniden ayırmak için bu statik işlevi çağırın.

```
static void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>Parametreler

*p*<br/>
Ayrılan belleğe yönelik işaretçi.

*nBytes*<br/>
Yeniden ayrılacak bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Ayrılan alana void bir işaretçi döndürür ya da bellek yetersizse NULL

### <a name="remarks"></a>Açıklamalar

Ayrılan bellek miktarını yeniden boyutlandırır. Daha fazla ayrıntı için bkz. [CoTaskMemRealloc](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemrealloc) .

## <a name="see-also"></a>Ayrıca bkz.

[CComHeapPtr Sınıfı](../../atl/reference/ccomheapptr-class.md)<br/>
[CCRTAllocator Sınıfı](../../atl/reference/ccrtallocator-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
