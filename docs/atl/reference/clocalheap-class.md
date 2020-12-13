---
description: 'Daha fazla bilgi edinin: CLocalHeap sınıfı'
title: CLocalHeap sınıfı
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
ms.openlocfilehash: 6cc168bc80182255017df3e3cdc970e5cfd56c7a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141524"
---
# <a name="clocalheap-class"></a>CLocalHeap sınıfı

Bu sınıf, Win32 yerel yığın işlevlerini kullanarak [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) uygular.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Syntax

```
class CLocalHeap : public IAtlMemMgr
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CLocalHeap:: ayır](#allocate)|Bellek bloğunu ayırmak için bu yöntemi çağırın.|
|[CLocalHeap:: ücretsiz](#free)|Bu bellek Yöneticisi tarafından ayrılan bir bellek bloğunu boşaltmak için bu yöntemi çağırın.|
|[CLocalHeap:: GetSize](#getsize)|Bu bellek Yöneticisi tarafından ayrılan bir bellek bloğunun ayrılan boyutunu almak için bu yöntemi çağırın.|
|[CLocalHeap:: yeniden tahsis](#reallocate)|Bu bellek Yöneticisi tarafından ayrılan belleği yeniden ayırmak için bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

`CLocalHeap` Win32 yerel yığın işlevlerini kullanarak bellek ayırma işlevlerini uygular.

> [!NOTE]
> Yerel yığın işlevleri, diğer bellek yönetim işlevlerinden daha yavaştır ve birçok özellik sağlamaz. Bu nedenle, yeni uygulamalar [yığın işlevlerini](/windows/win32/Memory/heap-functions)kullanmalıdır. Bunlar [CWin32Heap](../../atl/reference/cwin32heap-class.md) sınıfında mevcuttur.

## <a name="example"></a>Örnek

[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)örneğine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IAtlMemMgr`

`CLocalHeap`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlmem. h

## <a name="clocalheapallocate"></a><a name="allocate"></a> CLocalHeap:: ayır

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

Bu yöntem tarafından ayrılan belleği serbest bırakmak için [CLocalHeap:: Free](#free) veya [CLocalHeap::](#reallocate) ' i çağırın.

LMEM_FIXED flag parametresi ile [LocalAlloc](/windows/win32/api/winbase/nf-winbase-localalloc) kullanılarak uygulanır.

## <a name="clocalheapfree"></a><a name="free"></a> CLocalHeap:: ücretsiz

Bu bellek Yöneticisi tarafından ayrılan bir bellek bloğunu boşaltmak için bu yöntemi çağırın.

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>Parametreler

*Lama*<br/>
Bu bellek Yöneticisi tarafından daha önce ayrılan bellek işaretçisi. NULL geçerli bir değerdir ve hiçbir şey yapmaz.

### <a name="remarks"></a>Açıklamalar

[LocalFree](/windows/win32/api/winbase/nf-winbase-localfree)kullanılarak uygulanır.

## <a name="clocalheapgetsize"></a><a name="getsize"></a> CLocalHeap:: GetSize

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

[LocalSize](/windows/win32/api/winbase/nf-winbase-localsize)kullanılarak uygulanır.

## <a name="clocalheapreallocate"></a><a name="reallocate"></a> CLocalHeap:: yeniden tahsis

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

Bu yöntem tarafından ayrılan belleği serbest bırakmak için [CLocalHeap:: Free](#free) öğesini çağırın.

[LocalReAlloc](/windows/win32/api/winbase/nf-winbase-localrealloc)kullanılarak uygulanır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[CComHeap sınıfı](../../atl/reference/ccomheap-class.md)<br/>
[CWin32Heap sınıfı](../../atl/reference/cwin32heap-class.md)<br/>
[CGlobalHeap sınıfı](../../atl/reference/cglobalheap-class.md)<br/>
[CCRTHeap sınıfı](../../atl/reference/ccrtheap-class.md)<br/>
[IAtlMemMgr sınıfı](../../atl/reference/iatlmemmgr-class.md)
