---
description: 'Daha fazla bilgi edinin: CCRTHeap sınıfı'
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
ms.openlocfilehash: c256139f37a4b0caa0a60f1a87fd71b6a3a8de3b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142018"
---
# <a name="ccrtheap-class"></a>CCRTHeap sınıfı

Bu sınıf, CRT yığın işlevlerini kullanarak [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) uygular.

## <a name="syntax"></a>Syntax

```
class CCRTHeap : public IAtlMemMgr
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CCRTHeap:: allocate](#allocate)|Bellek bloğunu ayırmak için bu yöntemi çağırın.|
|[CCRTHeap:: Free](#free)|Bu bellek Yöneticisi tarafından ayrılan bir bellek bloğunu boşaltmak için bu yöntemi çağırın.|
|[CCRTHeap:: GetSize](#getsize)|Bu bellek Yöneticisi tarafından ayrılan bir bellek bloğunun ayrılan boyutunu almak için bu yöntemi çağırın.|
|[CCRTHeap:: yeniden tahsis](#reallocate)|Bu bellek Yöneticisi tarafından ayrılan belleği yeniden ayırmak için bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

`CCRTHeap`[malloc](../../c-runtime-library/reference/malloc.md), [ücretsiz](../../c-runtime-library/reference/free.md), [REALLOC](../../c-runtime-library/reference/realloc.md)ve [_msize](../../c-runtime-library/reference/msize.md)dahil CRT yığın işlevlerini kullanarak bellek ayırma işlevlerini uygular.

## <a name="example"></a>Örnek

[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)örneğine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IAtlMemMgr`

`CCRTHeap`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlmem. h

## <a name="ccrtheapallocate"></a><a name="allocate"></a> CCRTHeap:: allocate

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

Bu yöntem tarafından ayrılan belleği boşaltmak için [CCRTHeap:: Free](#free) veya [CCRTHeap::](#reallocate) olarak yeniden tahsis edin.

[Malloc](../../c-runtime-library/reference/malloc.md)kullanılarak uygulanır.

## <a name="ccrtheapfree"></a><a name="free"></a> CCRTHeap:: Free

Bu bellek Yöneticisi tarafından ayrılan bir bellek bloğunu boşaltmak için bu yöntemi çağırın.

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>Parametreler

*Lama*<br/>
Bu bellek Yöneticisi tarafından daha önce ayrılan bellek işaretçisi. NULL geçerli bir değerdir ve hiçbir şey yapmaz.

### <a name="remarks"></a>Açıklamalar

[Ücretsiz](../../c-runtime-library/reference/free.md)kullanılarak uygulanır.

## <a name="ccrtheapgetsize"></a><a name="getsize"></a> CCRTHeap:: GetSize

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

[_Msize](../../c-runtime-library/reference/msize.md)kullanılarak uygulanır.

## <a name="ccrtheapreallocate"></a><a name="reallocate"></a> CCRTHeap:: yeniden tahsis

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

Bu yöntem tarafından ayrılan belleği serbest bırakmak için [CCRTHeap:: Free](#free) öğesini çağırın. [Realloc](../../c-runtime-library/reference/realloc.md)kullanılarak uygulanır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[CComHeap sınıfı](../../atl/reference/ccomheap-class.md)<br/>
[CWin32Heap sınıfı](../../atl/reference/cwin32heap-class.md)<br/>
[CLocalHeap sınıfı](../../atl/reference/clocalheap-class.md)<br/>
[CGlobalHeap sınıfı](../../atl/reference/cglobalheap-class.md)<br/>
[IAtlMemMgr sınıfı](../../atl/reference/iatlmemmgr-class.md)
