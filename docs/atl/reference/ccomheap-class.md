---
title: CComHeap Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComHeap
- ATLCOMMEM/ATL::CComHeap
- ATLCOMMEM/ATL::CComHeap::Allocate
- ATLCOMMEM/ATL::CComHeap::Free
- ATLCOMMEM/ATL::CComHeap::GetSize
- ATLCOMMEM/ATL::CComHeap::Reallocate
helpviewer_keywords:
- CComHeap class
ms.assetid: c74183ce-98ae-46fb-b186-93ea4cf0222b
ms.openlocfilehash: a38d1147e718870c03af84ec1487e226805b956e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327829"
---
# <a name="ccomheap-class"></a>CComHeap Sınıfı

Bu sınıf COM bellek ayırma işlevlerini kullanarak [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) uygular.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CComHeap : public IAtlMemMgr
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CComHeap::Ayırma](#allocate)|Bellek bloğunu ayırmak için bu yöntemi çağırın.|
|[CComHeap::Ücretsiz](#free)|Bu bellek yöneticisi tarafından ayrılan bellek bloğunu serbest kaldırmak için bu yöntemi arayın.|
|[CComHeap::GetSize](#getsize)|Bu bellek yöneticisi tarafından ayrılan bellek bloğu ayrılmış boyutunu almak için bu yöntemi arayın.|
|[CComHeap::Yer tahsisi](#reallocate)|Bu bellek yöneticisi tarafından ayrılan belleği yeniden tahsis etmek için bu yöntemi arayın.|

## <a name="remarks"></a>Açıklamalar

`CComHeap`[CoTaskMemAlloc,](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemalloc) [CoTaskMemFree,](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemfree) [IMalloc::GetSize](/windows/win32/api/objidlbase/nf-objidlbase-imalloc-getsize)ve [CoTaskMemRealloc](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemrealloc)dahil olmak üzere COM ayırma işlevlerini kullanarak bellek ayırma işlevlerini uygular. Ayrılabilen maksimum bellek miktarı INT_MAX (2147483647) baytlara eşittir.

## <a name="example"></a>Örnek

[IAtlMemmgr](../../atl/reference/iatlmemmgr-class.md)örneğine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IAtlMemMgr`

`CComHeap`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** ATLComMem.h

## <a name="ccomheapallocate"></a><a name="allocate"></a>CComHeap::Ayırma

Bellek bloğunu ayırmak için bu yöntemi çağırın.

```
virtual __declspec(allocator) void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>Parametreler

*nBayt*<br/>
Yeni bellek bloğunda istenen bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Yeni ayrılan bellek bloğunun başlangıcına bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

[CComHeap'ı arayın::Ücretsiz](#free) veya [CComHeap::Bu](#reallocate) yöntemle ayrılan belleği serbest etmek için yeniden bulunun.

[CoTaskMemAlloc](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemalloc)kullanılarak uygulanır.

## <a name="ccomheapfree"></a><a name="free"></a>CComHeap::Ücretsiz

Bu bellek yöneticisi tarafından ayrılan bellek bloğunu serbest kaldırmak için bu yöntemi arayın.

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>Parametreler

*P*<br/>
Bu bellek yöneticisi tarafından daha önce tahsis edilen belleğe işaretçi. NULL geçerli bir değerdir ve hiçbir şey yapmaz.

### <a name="remarks"></a>Açıklamalar

[CoTaskMemFree](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemfree)kullanılarak uygulanır.

## <a name="ccomheapgetsize"></a><a name="getsize"></a>CComHeap::GetSize

Bu bellek yöneticisi tarafından ayrılan bellek bloğu ayrılmış boyutunu almak için bu yöntemi arayın.

```
virtual size_t GetSize(void* p) throw();
```

### <a name="parameters"></a>Parametreler

*P*<br/>
Bu bellek yöneticisi tarafından daha önce tahsis edilen belleğe işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Baytlar halinde ayrılan bellek bloğunun boyutunu döndürür.

### <a name="remarks"></a>Açıklamalar

[IMalloc kullanılarak uygulanan::GetSize](/windows/win32/api/objidlbase/nf-objidlbase-imalloc-getsize).

## <a name="ccomheapreallocate"></a><a name="reallocate"></a>CComHeap::Yer tahsisi

Bu bellek yöneticisi tarafından ayrılan belleği yeniden tahsis etmek için bu yöntemi arayın.

```
virtual __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>Parametreler

*P*<br/>
Bu bellek yöneticisi tarafından daha önce tahsis edilen belleğe işaretçi.

*nBayt*<br/>
Yeni bellek bloğunda istenen bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Yeni ayrılan bellek bloğunun başlangıcına bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

[CComHeap'ı arayın::Bu](#free) yöntemle ayrılan belleği serbest serbest etmek için ücretsiz.

[CoTaskMemRealloc](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemrealloc)kullanılarak uygulanır.

## <a name="see-also"></a>Ayrıca bkz.

[DinamikTüketici Örneği](../../overview/visual-cpp-samples.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)<br/>
[CWin32Heap Sınıfı](../../atl/reference/cwin32heap-class.md)<br/>
[CLocalHeap Sınıfı](../../atl/reference/clocalheap-class.md)<br/>
[CGlobalHeap Sınıfı](../../atl/reference/cglobalheap-class.md)<br/>
[CCRTHeap Sınıfı](../../atl/reference/ccrtheap-class.md)<br/>
[IAtlMemMgr Sınıfı](../../atl/reference/iatlmemmgr-class.md)
