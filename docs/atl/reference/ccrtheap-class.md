---
title: CCRTHeap sınıfı
ms.date: 11/04/2016
f1_keywords:
- CCRTHeap
- ATLMEM/ATL::CCRTHeap
- ATLMEM/ATL::CCRTHeap::Allocate
- ATLMEM/ATL::CCRTHeap::Free
- ATLMEM/ATL::CCRTHeap::GetSize
- ATLMEM/ATL::CCRTHeap::Reallocate
helpviewer_keywords:
- CCRTHeap class
ms.assetid: 321bd6c5-1856-4ff7-8590-95044a1209f7
ms.openlocfilehash: 3c5030b9cfbfd636a783d27bcc8f9469f8348acb
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57276279"
---
# <a name="ccrtheap-class"></a>CCRTHeap sınıfı

Bu sınıfın uyguladığı [Iatlmemmgr](../../atl/reference/iatlmemmgr-class.md) CRT yığın işlevlerinin kullanarak.

## <a name="syntax"></a>Sözdizimi

```
class CCRTHeap : public IAtlMemMgr
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CCRTHeap::Allocate](#allocate)|Bir bellek bloğu ayırmak için bu yöntemi çağırın.|
|[CCRTHeap::Free](#free)|Bu bellek yöneticisi tarafından ayrılan bellek bloğunu serbest bırakmak için bu yöntemi çağırın.|
|[CCRTHeap::GetSize](#getsize)|Bu bellek yöneticisi tarafından ayrılan bir bellek bloğu ayrılmış boyutunu almak için bu yöntemi çağırın.|
|[CCRTHeap::Reallocate](#reallocate)|Bu bellek yöneticisi tarafından ayrılan bellek yeniden ayırmak üzere bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

`CCRTHeap` CRT kullanarak ayırma işlevleri, İşlevler dahil olmak üzere, yığın bellek uygulayan [malloc](../../c-runtime-library/reference/malloc.md), [ücretsiz](../../c-runtime-library/reference/free.md), [realloc](../../c-runtime-library/reference/realloc.md), ve [_msize](../../c-runtime-library/reference/msize.md).

## <a name="example"></a>Örnek

Örneğin bakın [Iatlmemmgr](../../atl/reference/iatlmemmgr-class.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IAtlMemMgr`

`CCRTHeap`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlmem.h

##  <a name="allocate"></a>  CCRTHeap::Allocate

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

Çağrı [CCRTHeap::Free](#free) veya [CCRTHeap::Reallocate](#reallocate) bu yöntem tarafından ayrılan bellek boşaltmak için.

Kullanılarak uygulanan [malloc](../../c-runtime-library/reference/malloc.md).

##  <a name="free"></a>  CCRTHeap::Free

Bu bellek yöneticisi tarafından ayrılan bellek bloğunu serbest bırakmak için bu yöntemi çağırın.

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>Parametreler

*p*<br/>
Bu bellek yöneticisi tarafından önceden ayrılan bellek işaretçisi. NULL, geçerli bir değer ve hiçbir şey yapmaz.

### <a name="remarks"></a>Açıklamalar

Kullanılarak uygulanan [ücretsiz](../../c-runtime-library/reference/free.md).

##  <a name="getsize"></a>  CCRTHeap::GetSize

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

Kullanılarak uygulanan [_msize](../../c-runtime-library/reference/msize.md).

##  <a name="reallocate"></a>  CCRTHeap::Reallocate

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

Çağrı [CCRTHeap::Free](#free) bu yöntem tarafından ayrılan bellek boşaltmak için. Kullanılarak uygulanan [realloc](../../c-runtime-library/reference/realloc.md).

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)<br/>
[CComHeap Sınıfı](../../atl/reference/ccomheap-class.md)<br/>
[CWin32Heap Sınıfı](../../atl/reference/cwin32heap-class.md)<br/>
[CLocalHeap Sınıfı](../../atl/reference/clocalheap-class.md)<br/>
[CGlobalHeap Sınıfı](../../atl/reference/cglobalheap-class.md)<br/>
[IAtlMemMgr Sınıfı](../../atl/reference/iatlmemmgr-class.md)
