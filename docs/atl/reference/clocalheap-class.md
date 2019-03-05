---
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
ms.openlocfilehash: 53288bea8a50f62437eab4dd81d5d816abf78f44
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57283091"
---
# <a name="clocalheap-class"></a>CLocalHeap sınıfı

Bu sınıfın uyguladığı [Iatlmemmgr](../../atl/reference/iatlmemmgr-class.md) Win32 yerel yığın işlevlerini kullanma.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CLocalHeap : public IAtlMemMgr
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CLocalHeap::Allocate](#allocate)|Bir bellek bloğu ayırmak için bu yöntemi çağırın.|
|[CLocalHeap::Free](#free)|Bu bellek yöneticisi tarafından ayrılan bellek bloğunu serbest bırakmak için bu yöntemi çağırın.|
|[CLocalHeap::GetSize](#getsize)|Bu bellek yöneticisi tarafından ayrılan bir bellek bloğu ayrılmış boyutunu almak için bu yöntemi çağırın.|
|[CLocalHeap::Reallocate](#reallocate)|Bu bellek yöneticisi tarafından ayrılan bellek yeniden ayırmak üzere bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

`CLocalHeap` bellek ayırma işlevleri için Win32 yerel yığın işlevlerini uygular.

> [!NOTE]
>  Yerel yığın işlevlerin diğer bellek yönetimi işlevleri yavaş çalışır ve gibi birçok özelliği sağlamaz. Bu nedenle, yeni uygulamalar kullanmalıdır [yığın işlevleri](/windows/desktop/Memory/heap-functions). Bunlar, kullanılabilir [CWin32Heap](../../atl/reference/cwin32heap-class.md) sınıfı.

## <a name="example"></a>Örnek

Örneğin bakın [Iatlmemmgr](../../atl/reference/iatlmemmgr-class.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IAtlMemMgr`

`CLocalHeap`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlmem.h

##  <a name="allocate"></a>  CLocalHeap::Allocate

Bir bellek bloğu ayırmak için bu yöntemi çağırın.

```
virtual __declspec(allocator) void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>Parametreler

*nBytes*<br/>
İstenen bayt yeni bellek bloğu sayısı.

### <a name="return-value"></a>Dönüş Değeri

Yeni ayrılan bellek bloğu başlangıcı için bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

Çağrı [CLocalHeap::Free](#free) veya [CLocalHeap::Reallocate](#reallocate) bu yöntem tarafından ayrılan bellek boşaltmak için.

Kullanılarak uygulanan [LocalAlloc](/windows/desktop/api/winbase/nf-winbase-localalloc) LMEM_FIXED bayrağı parametresi ile.

##  <a name="free"></a>  CLocalHeap::Free

Bu bellek yöneticisi tarafından ayrılan bellek bloğunu serbest bırakmak için bu yöntemi çağırın.

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>Parametreler

*p*<br/>
Bu bellek yöneticisi tarafından önceden ayrılan bellek işaretçisi. NULL, geçerli bir değer ve hiçbir şey yapmaz.

### <a name="remarks"></a>Açıklamalar

Kullanılarak uygulanan [LocalFree](/windows/desktop/api/winbase/nf-winbase-localfree).

##  <a name="getsize"></a>  CLocalHeap::GetSize

Bu bellek yöneticisi tarafından ayrılan bir bellek bloğu ayrılmış boyutunu almak için bu yöntemi çağırın.

```
virtual size_t GetSize(void* p) throw();
```

### <a name="parameters"></a>Parametreler

*p*<br/>
Bu bellek yöneticisi tarafından önceden ayrılan bellek işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Ayrılan bellek blok boyutu bayt cinsinden döndürür.

### <a name="remarks"></a>Açıklamalar

Kullanılarak uygulanan [LocalSize](/windows/desktop/api/winbase/nf-winbase-localsize).

##  <a name="reallocate"></a>  CLocalHeap::Reallocate

Bu bellek yöneticisi tarafından ayrılan bellek yeniden ayırmak üzere bu yöntemi çağırın.

```
virtual __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>Parametreler

*p*<br/>
Bu bellek yöneticisi tarafından önceden ayrılan bellek işaretçisi.

*nBytes*<br/>
İstenen bayt yeni bellek bloğu sayısı.

### <a name="return-value"></a>Dönüş Değeri

Yeni ayrılan bellek bloğu başlangıcı için bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

Çağrı [CLocalHeap::Free](#free) bu yöntem tarafından ayrılan bellek boşaltmak için.

Kullanılarak uygulanan [LocalReAlloc](/windows/desktop/api/winbase/nf-winbase-localrealloc).

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)<br/>
[CComHeap Sınıfı](../../atl/reference/ccomheap-class.md)<br/>
[CWin32Heap Sınıfı](../../atl/reference/cwin32heap-class.md)<br/>
[CGlobalHeap Sınıfı](../../atl/reference/cglobalheap-class.md)<br/>
[CCRTHeap Sınıfı](../../atl/reference/ccrtheap-class.md)<br/>
[IAtlMemMgr Sınıfı](../../atl/reference/iatlmemmgr-class.md)
