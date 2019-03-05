---
title: CComAllocator sınıfı
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
ms.openlocfilehash: 9f1c005262d25b1ff5e900377c229afe1573e6d3
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57296078"
---
# <a name="ccomallocator-class"></a>CComAllocator sınıfı

Bu sınıf, COM bellek yordamları kullanarak bellek yönetmek için yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CComAllocator
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComAllocator::Allocate](#allocate)|Bellek ayırma için statik bu yöntemi çağırın.|
|[CComAllocator::Free](#free)|Ayrılmış belleği boşaltmak için statik bu yöntemi çağırın.|
|[CComAllocator::Reallocate](#reallocate)|Bellek yeniden ayırmak üzere statik bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf tarafından kullanılan [CComHeapPtr](../../atl/reference/ccomheapptr-class.md) COM bellek ayırma yordamlarını sağlamak için. Karşılık gelen sınıf [CCRTAllocator](../../atl/reference/ccrtallocator-class.md), CRT yordamları kullanarak aynı yöntemleri sağlar.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlbase.h

##  <a name="allocate"></a>  CComAllocator::Allocate

Bellek ayırma için statik bu işlevi çağırın.

```
static void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>Parametreler

*nBytes*<br/>
Ayrılacak bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Kullanılabilir bellek yetersiz ise bir void işaretçisine ayrılan alanı veya NULL döndürür.

### <a name="remarks"></a>Açıklamalar

Bellek ayırır. Bkz: [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) daha fazla ayrıntı için.

##  <a name="free"></a>  CComAllocator::Free

Ayrılmış belleği boşaltmak için statik bu işlevi çağırın.

```
static void Free(void* p) throw();
```

### <a name="parameters"></a>Parametreler

*p*<br/>
Ayrılan bellek işaretçisi.

### <a name="remarks"></a>Açıklamalar

Ayrılan belleği serbest bırakır. Bkz: [CoTaskMemFree](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemfree) daha fazla ayrıntı için.

##  <a name="reallocate"></a>  CComAllocator::Reallocate

Bellek yeniden ayırmak üzere statik bu işlevi çağırın.

```
static void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>Parametreler

*p*<br/>
Ayrılan bellek işaretçisi.

*nBytes*<br/>
Ayrılacak bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Yetersiz bellek varsa void bir işaretçi ayrılan alanı veya NULL döndürür.

### <a name="remarks"></a>Açıklamalar

Ayrılan bellek miktarını yeniden boyutlandırır. Bkz: [CoTaskMemRealloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemrealloc) daha fazla ayrıntı için.

## <a name="see-also"></a>Ayrıca bkz.

[CComHeapPtr Sınıfı](../../atl/reference/ccomheapptr-class.md)<br/>
[CCRTAllocator Sınıfı](../../atl/reference/ccrtallocator-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
