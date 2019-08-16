---
title: CGlobalHeap sınıfı
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
ms.openlocfilehash: 2b5aa09357ddcc77b6b10de58545bea86eff2488
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496759"
---
# <a name="cglobalheap-class"></a>CGlobalHeap sınıfı

Bu sınıf, Win32 genel yığın işlevlerini kullanarak [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) uygular.

> [!IMPORTANT]
>  Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CGlobalHeap : public IAtlMemMgr
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CGlobalHeap:: ayır](#allocate)|Bellek bloğunu ayırmak için bu yöntemi çağırın.|
|[CGlobalHeap:: ücretsiz](#free)|Bu bellek Yöneticisi tarafından ayrılan bir bellek bloğunu boşaltmak için bu yöntemi çağırın.|
|[CGlobalHeap:: GetSize](#getsize)|Bu bellek Yöneticisi tarafından ayrılan bir bellek bloğunun ayrılan boyutunu almak için bu yöntemi çağırın.|
|[CGlobalHeap:: yeniden tahsis](#reallocate)|Bu bellek Yöneticisi tarafından ayrılan belleği yeniden ayırmak için bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

`CGlobalHeap`Win32 genel yığın işlevlerini kullanarak bellek ayırma işlevlerini uygular.

> [!NOTE]
>  Genel yığın işlevleri diğer bellek yönetimi işlevlerinden daha yavaştır ve birçok özellik sağlamaz. Bu nedenle, yeni uygulamalar [yığın işlevlerini](/windows/win32/Memory/heap-functions)kullanmalıdır. Bunlar [CWin32Heap](../../atl/reference/cwin32heap-class.md) sınıfında mevcuttur. Genel işlevler hala DDE ve Pano işlevleri tarafından kullanılmaktadır.

## <a name="example"></a>Örnek

[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)örneğine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IAtlMemMgr`

`CGlobalHeap`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlmem. h

##  <a name="allocate"></a>CGlobalHeap:: ayır

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

Bu yöntem tarafından ayrılan belleği serbest bırakmak için [CGlobalHeap:: Free](#free) veya [CGlobalHeap::](#reallocate) ' i çağırın.

GMEM_FIXED 'in Flag parametresiyle [GlobalAlloc](/windows/win32/api/winbase/nf-winbase-globalalloc) kullanılarak uygulanır.

##  <a name="free"></a>CGlobalHeap:: ücretsiz

Bu bellek Yöneticisi tarafından ayrılan bir bellek bloğunu boşaltmak için bu yöntemi çağırın.

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>Parametreler

*p*<br/>
Bu bellek Yöneticisi tarafından daha önce ayrılan bellek işaretçisi. NULL geçerli bir değerdir ve hiçbir şey yapmaz.

### <a name="remarks"></a>Açıklamalar

[GlobalFree](/windows/win32/api/winbase/nf-winbase-globalfree)kullanılarak uygulanır.

##  <a name="getsize"></a>CGlobalHeap:: GetSize

Bu bellek Yöneticisi tarafından ayrılan bir bellek bloğunun ayrılan boyutunu almak için bu yöntemi çağırın.

```
virtual size_t GetSize(void* p) throw();
```

### <a name="parameters"></a>Parametreler

*p*<br/>
Bu bellek Yöneticisi tarafından daha önce ayrılan bellek işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Ayrılan bellek bloğunun boyutunu bayt cinsinden döndürür.

### <a name="remarks"></a>Açıklamalar

[GlobalSize](/windows/win32/api/winbase/nf-winbase-globalsize)kullanılarak uygulanır.

##  <a name="reallocate"></a>CGlobalHeap:: yeniden tahsis

Bu bellek Yöneticisi tarafından ayrılan belleği yeniden ayırmak için bu yöntemi çağırın.

```
virtual __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>Parametreler

*p*<br/>
Bu bellek Yöneticisi tarafından daha önce ayrılan bellek işaretçisi.

*nBytes*<br/>
Yeni bellek bloğunda istenen bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Yeni ayrılan bellek bloğunun başlangıcına bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem tarafından ayrılan belleği serbest bırakmak için [CGlobalHeap:: Free](#free) çağırın.

[GlobalReAlloc](/windows/win32/api/winbase/nf-winbase-globalrealloc)kullanılarak uygulandı.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[CComHeap Sınıfı](../../atl/reference/ccomheap-class.md)<br/>
[CWin32Heap Sınıfı](../../atl/reference/cwin32heap-class.md)<br/>
[CLocalHeap Sınıfı](../../atl/reference/clocalheap-class.md)<br/>
[CCRTHeap Sınıfı](../../atl/reference/ccrtheap-class.md)<br/>
[IAtlMemMgr Sınıfı](../../atl/reference/iatlmemmgr-class.md)
