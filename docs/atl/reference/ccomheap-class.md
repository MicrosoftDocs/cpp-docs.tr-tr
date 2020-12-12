---
description: 'Daha fazla bilgi edinin: CComHeap sınıfı'
title: CComHeap sınıfı
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
ms.openlocfilehash: 2ced98194bea8e186cee17504ca9e3abf7c212c3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152041"
---
# <a name="ccomheap-class"></a>CComHeap sınıfı

Bu sınıf, COM bellek ayırma işlevlerini kullanarak [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) uygular.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Syntax

```
class CComHeap : public IAtlMemMgr
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComHeap:: allocate](#allocate)|Bellek bloğunu ayırmak için bu yöntemi çağırın.|
|[CComHeap:: ücretsiz](#free)|Bu bellek Yöneticisi tarafından ayrılan bir bellek bloğunu boşaltmak için bu yöntemi çağırın.|
|[CComHeap:: GetSize](#getsize)|Bu bellek Yöneticisi tarafından ayrılan bir bellek bloğunun ayrılan boyutunu almak için bu yöntemi çağırın.|
|[CComHeap:: yeniden tahsis](#reallocate)|Bu bellek Yöneticisi tarafından ayrılan belleği yeniden ayırmak için bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

`CComHeap`[CoTaskMemAlloc](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemalloc), [CoTaskMemFree](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemfree), [ımayırma:: GetSize](/windows/win32/api/objidlbase/nf-objidlbase-imalloc-getsize)ve [CoTaskMemRealloc](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemrealloc)dahil olmak üzere com ayırma işlevlerini kullanarak bellek ayırma işlevlerini uygular. Ayrılabilen maksimum bellek miktarı INT_MAX (2147483647) bayta eşittir.

## <a name="example"></a>Örnek

[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)örneğine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IAtlMemMgr`

`CComHeap`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** ATLComMem. h

## <a name="ccomheapallocate"></a><a name="allocate"></a> CComHeap:: allocate

Bellek bloğunu ayırmak için bu yöntemi çağırın.

```
virtual __declspec(allocator) void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>Parametreler

*nBytes*<br/>
Yeni bellek bloğunda istenen bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Yeni ayrılan bellek bloğunun başlangıcına bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem tarafından ayrılan belleği serbest bırakmak için [CComHeap:: Free](#free) veya [CComHeap::](#reallocate) ' i çağırın.

[CoTaskMemAlloc](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemalloc)kullanılarak uygulanır.

## <a name="ccomheapfree"></a><a name="free"></a> CComHeap:: ücretsiz

Bu bellek Yöneticisi tarafından ayrılan bir bellek bloğunu boşaltmak için bu yöntemi çağırın.

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>Parametreler

*Lama*<br/>
Bu bellek Yöneticisi tarafından daha önce ayrılan bellek işaretçisi. NULL geçerli bir değerdir ve hiçbir şey yapmaz.

### <a name="remarks"></a>Açıklamalar

[CoTaskMemFree](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemfree)kullanılarak uygulanır.

## <a name="ccomheapgetsize"></a><a name="getsize"></a> CComHeap:: GetSize

Bu bellek Yöneticisi tarafından ayrılan bir bellek bloğunun ayrılan boyutunu almak için bu yöntemi çağırın.

```
virtual size_t GetSize(void* p) throw();
```

### <a name="parameters"></a>Parametreler

*Lama*<br/>
Bu bellek Yöneticisi tarafından daha önce ayrılan bellek işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Ayrılan bellek bloğunun boyutunu bayt cinsinden döndürür.

### <a name="remarks"></a>Açıklamalar

[Imayırma:: GetSize](/windows/win32/api/objidlbase/nf-objidlbase-imalloc-getsize)kullanılarak uygulanır.

## <a name="ccomheapreallocate"></a><a name="reallocate"></a> CComHeap:: yeniden tahsis

Bu bellek Yöneticisi tarafından ayrılan belleği yeniden ayırmak için bu yöntemi çağırın.

```
virtual __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>Parametreler

*Lama*<br/>
Bu bellek Yöneticisi tarafından daha önce ayrılan bellek işaretçisi.

*nBytes*<br/>
Yeni bellek bloğunda istenen bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Yeni ayrılan bellek bloğunun başlangıcına bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem tarafından ayrılan belleği serbest bırakmak için [CComHeap:: Free](#free) çağırın.

[CoTaskMemRealloc](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemrealloc)kullanılarak uygulandı.

## <a name="see-also"></a>Ayrıca bkz.

[DynamicConsumer örneği](../../overview/visual-cpp-samples.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[CWin32Heap sınıfı](../../atl/reference/cwin32heap-class.md)<br/>
[CLocalHeap sınıfı](../../atl/reference/clocalheap-class.md)<br/>
[CGlobalHeap sınıfı](../../atl/reference/cglobalheap-class.md)<br/>
[CCRTHeap sınıfı](../../atl/reference/ccrtheap-class.md)<br/>
[IAtlMemMgr sınıfı](../../atl/reference/iatlmemmgr-class.md)
