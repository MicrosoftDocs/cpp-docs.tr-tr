---
title: CGlobalHeap Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CGlobalHeap
- ATLMEM/ATL::CGlobalHeap
- ATLMEM/ATL::CGlobalHeap::Allocate
- ATLMEM/ATL::CGlobalHeap::Free
- ATLMEM/ATL::CGlobalHeap::GetSize
- ATLMEM/ATL::CGlobalHeap::Reallocate
helpviewer_keywords:
- CGlobalHeap class
ms.assetid: e348d838-3aa7-4bee-a1b3-cd000c99f834
ms.openlocfilehash: d596fd51c1bf33f606c1f14c9e8dbd2f1926c7f8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326937"
---
# <a name="cglobalheap-class"></a>CGlobalHeap Sınıfı

Bu sınıf Win32 küresel yığın işlevlerini kullanarak [IAtlMemgr](../../atl/reference/iatlmemmgr-class.md) uygular.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CGlobalHeap : public IAtlMemMgr
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CGlobalHeap::Ayırma](#allocate)|Bellek bloğunu ayırmak için bu yöntemi çağırın.|
|[CGlobalHeap::Ücretsiz](#free)|Bu bellek yöneticisi tarafından ayrılan bellek bloğunu serbest kaldırmak için bu yöntemi arayın.|
|[CGlobalHeap::GetSize](#getsize)|Bu bellek yöneticisi tarafından ayrılan bellek bloğu ayrılmış boyutunu almak için bu yöntemi arayın.|
|[CGlobalHeap::Tahsis](#reallocate)|Bu bellek yöneticisi tarafından ayrılan belleği yeniden tahsis etmek için bu yöntemi arayın.|

## <a name="remarks"></a>Açıklamalar

`CGlobalHeap`Win32 genel yığın işlevlerini kullanarak bellek ayırma işlevlerini uygular.

> [!NOTE]
> Genel yığın işlevleri diğer bellek yönetimi işlevlerinden daha yavaşve birçok özellik sağlamaz. Bu nedenle, yeni uygulamalar [yığın işlevleri](/windows/win32/Memory/heap-functions)ni kullanmalıdır. Bunlar [CWin32Heap](../../atl/reference/cwin32heap-class.md) sınıfında mevcuttur. Genel işlevler hala DDE ve pano işlevleri tarafından kullanılır.

## <a name="example"></a>Örnek

[IAtlMemmgr](../../atl/reference/iatlmemmgr-class.md)örneğine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IAtlMemMgr`

`CGlobalHeap`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlmem.h

## <a name="cglobalheapallocate"></a><a name="allocate"></a>CGlobalHeap::Ayırma

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

[CGlobalHeap'ı Arayın::Ücretsiz](#free) veya [CGlobalHeap::Bu](#reallocate) yöntemle ayrılan belleği serbest etmek için yeniden bulunun.

GMEM_FIXED bayrak parametresi ile [GlobalAlloc](/windows/win32/api/winbase/nf-winbase-globalalloc) kullanılarak uygulanır.

## <a name="cglobalheapfree"></a><a name="free"></a>CGlobalHeap::Ücretsiz

Bu bellek yöneticisi tarafından ayrılan bellek bloğunu serbest kaldırmak için bu yöntemi arayın.

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>Parametreler

*P*<br/>
Bu bellek yöneticisi tarafından daha önce tahsis edilen belleğe işaretçi. NULL geçerli bir değerdir ve hiçbir şey yapmaz.

### <a name="remarks"></a>Açıklamalar

[GlobalFree](/windows/win32/api/winbase/nf-winbase-globalfree)kullanılarak uygulanmaktadır.

## <a name="cglobalheapgetsize"></a><a name="getsize"></a>CGlobalHeap::GetSize

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

[GlobalSize](/windows/win32/api/winbase/nf-winbase-globalsize)kullanılarak uygulanır.

## <a name="cglobalheapreallocate"></a><a name="reallocate"></a>CGlobalHeap::Tahsis

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

[CGlobalHeap'ı arayın::Bu](#free) yöntemle ayrılan belleği serbest serbest kılmış için ücretsiz.

[GlobalReAlloc](/windows/win32/api/winbase/nf-winbase-globalrealloc)kullanılarak uygulanmaktadır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)<br/>
[CComHeap Sınıfı](../../atl/reference/ccomheap-class.md)<br/>
[CWin32Heap Sınıfı](../../atl/reference/cwin32heap-class.md)<br/>
[CLocalHeap Sınıfı](../../atl/reference/clocalheap-class.md)<br/>
[CCRTHeap Sınıfı](../../atl/reference/ccrtheap-class.md)<br/>
[IAtlMemMgr Sınıfı](../../atl/reference/iatlmemmgr-class.md)
