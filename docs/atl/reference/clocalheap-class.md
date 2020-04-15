---
title: CLocalHeap Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CLocalHeap
- ATLMEM/ATL::CLocalHeap
- ATLMEM/ATL::CLocalHeap::Allocate
- ATLMEM/ATL::CLocalHeap::Free
- ATLMEM/ATL::CLocalHeap::GetSize
- ATLMEM/ATL::CLocalHeap::Reallocate
helpviewer_keywords:
- CLocalHeap class
ms.assetid: 1ffa87a5-5fc8-4f8d-8809-58e87e963bd2
ms.openlocfilehash: 303e3b85ad11c309f862f59d6ec610701c4ef6db
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326755"
---
# <a name="clocalheap-class"></a>CLocalHeap Sınıfı

Bu sınıf Win32 yerel yığın işlevlerini kullanarak [IAtlMemmgr](../../atl/reference/iatlmemmgr-class.md) uygular.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CLocalHeap : public IAtlMemMgr
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CLocalHeap::Ayırma](#allocate)|Bellek bloğunu ayırmak için bu yöntemi çağırın.|
|[CLocalHeap::Ücretsiz](#free)|Bu bellek yöneticisi tarafından ayrılan bellek bloğunu serbest kaldırmak için bu yöntemi arayın.|
|[CLocalHeap::GetSize](#getsize)|Bu bellek yöneticisi tarafından ayrılan bellek bloğu ayrılmış boyutunu almak için bu yöntemi arayın.|
|[CLocalHeap::Yer tahsisi](#reallocate)|Bu bellek yöneticisi tarafından ayrılan belleği yeniden tahsis etmek için bu yöntemi arayın.|

## <a name="remarks"></a>Açıklamalar

`CLocalHeap`Win32 yerel yığın işlevlerini kullanarak bellek ayırma işlevlerini uygular.

> [!NOTE]
> Yerel yığın işlevleri diğer bellek yönetimi işlevlerinden daha yavaşve birçok özellik sağlamaz. Bu nedenle, yeni uygulamalar [yığın işlevleri](/windows/win32/Memory/heap-functions)ni kullanmalıdır. Bunlar [CWin32Heap](../../atl/reference/cwin32heap-class.md) sınıfında mevcuttur.

## <a name="example"></a>Örnek

[IAtlMemmgr](../../atl/reference/iatlmemmgr-class.md)örneğine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IAtlMemMgr`

`CLocalHeap`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlmem.h

## <a name="clocalheapallocate"></a><a name="allocate"></a>CLocalHeap::Ayırma

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

[CLocalHeap'ı arayın::Ücretsiz](#free) veya [CLocalHeap::Bu](#reallocate) yöntemle ayrılan belleği serbest etmek için yeniden bulunun.

LMEM_FIXED bayrak parametresi ile [LocalAlloc](/windows/win32/api/winbase/nf-winbase-localalloc) kullanılarak uygulanır.

## <a name="clocalheapfree"></a><a name="free"></a>CLocalHeap::Ücretsiz

Bu bellek yöneticisi tarafından ayrılan bellek bloğunu serbest kaldırmak için bu yöntemi arayın.

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>Parametreler

*P*<br/>
Bu bellek yöneticisi tarafından daha önce tahsis edilen belleğe işaretçi. NULL geçerli bir değerdir ve hiçbir şey yapmaz.

### <a name="remarks"></a>Açıklamalar

[LocalFree](/windows/win32/api/winbase/nf-winbase-localfree)kullanılarak uygulanır.

## <a name="clocalheapgetsize"></a><a name="getsize"></a>CLocalHeap::GetSize

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

[LocalSize](/windows/win32/api/winbase/nf-winbase-localsize)kullanılarak uygulanır.

## <a name="clocalheapreallocate"></a><a name="reallocate"></a>CLocalHeap::Yer tahsisi

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

[CLocalHeap'ı arayın::Bu](#free) yöntemle ayrılan belleği serbest serbest etmek için ücretsiz.

[LocalReAlloc](/windows/win32/api/winbase/nf-winbase-localrealloc)kullanılarak uygulanır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)<br/>
[CComHeap Sınıfı](../../atl/reference/ccomheap-class.md)<br/>
[CWin32Heap Sınıfı](../../atl/reference/cwin32heap-class.md)<br/>
[CGlobalHeap Sınıfı](../../atl/reference/cglobalheap-class.md)<br/>
[CCRTHeap Sınıfı](../../atl/reference/ccrtheap-class.md)<br/>
[IAtlMemMgr Sınıfı](../../atl/reference/iatlmemmgr-class.md)
