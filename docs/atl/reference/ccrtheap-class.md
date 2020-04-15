---
title: CCRTHeap Sınıfı
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
ms.openlocfilehash: caf5508079332689c2fff42f130951375dc35512
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327155"
---
# <a name="ccrtheap-class"></a>CCRTHeap Sınıfı

Bu sınıf CRT yığın işlevlerini kullanarak [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) uygular.

## <a name="syntax"></a>Sözdizimi

```
class CCRTHeap : public IAtlMemMgr
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CCRTHeap::Ayırma](#allocate)|Bellek bloğunu ayırmak için bu yöntemi çağırın.|
|[CCRTHeap::Ücretsiz](#free)|Bu bellek yöneticisi tarafından ayrılan bellek bloğunu serbest kaldırmak için bu yöntemi arayın.|
|[CCRTHeap::GetSize](#getsize)|Bu bellek yöneticisi tarafından ayrılan bellek bloğu ayrılmış boyutunu almak için bu yöntemi arayın.|
|[CCRTHeap::Yeniden tahsis](#reallocate)|Bu bellek yöneticisi tarafından ayrılan belleği yeniden tahsis etmek için bu yöntemi arayın.|

## <a name="remarks"></a>Açıklamalar

`CCRTHeap`[malloc,](../../c-runtime-library/reference/malloc.md) [ücretsiz,](../../c-runtime-library/reference/free.md) [realloc](../../c-runtime-library/reference/realloc.md)ve [_msize](../../c-runtime-library/reference/msize.md)dahil olmak üzere CRT yığın işlevlerini kullanarak bellek ayırma işlevleri uygular.

## <a name="example"></a>Örnek

[IAtlMemmgr](../../atl/reference/iatlmemmgr-class.md)örneğine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IAtlMemMgr`

`CCRTHeap`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlmem.h

## <a name="ccrtheapallocate"></a><a name="allocate"></a>CCRTHeap::Ayırma

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

[CCRTHeap'ı arayın::Ücretsiz](#free) veya [CCRTHeap::Bu](#reallocate) yöntemle ayrılan belleği serbest etmek için yeniden bulunun.

[Malloc](../../c-runtime-library/reference/malloc.md)kullanılarak uygulanır.

## <a name="ccrtheapfree"></a><a name="free"></a>CCRTHeap::Ücretsiz

Bu bellek yöneticisi tarafından ayrılan bellek bloğunu serbest kaldırmak için bu yöntemi arayın.

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>Parametreler

*P*<br/>
Bu bellek yöneticisi tarafından daha önce tahsis edilen belleğe işaretçi. NULL geçerli bir değerdir ve hiçbir şey yapmaz.

### <a name="remarks"></a>Açıklamalar

[Ücretsiz](../../c-runtime-library/reference/free.md)kullanılarak uygulanır.

## <a name="ccrtheapgetsize"></a><a name="getsize"></a>CCRTHeap::GetSize

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

[_msize](../../c-runtime-library/reference/msize.md)kullanılarak uygulanır.

## <a name="ccrtheapreallocate"></a><a name="reallocate"></a>CCRTHeap::Yeniden tahsis

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

[CCRTHeap'ı arayın::Bu](#free) yöntemle ayrılan belleği serbest çesitlemek için ücretsiz. [Realloc](../../c-runtime-library/reference/realloc.md)kullanılarak uygulanır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)<br/>
[CComHeap Sınıfı](../../atl/reference/ccomheap-class.md)<br/>
[CWin32Heap Sınıfı](../../atl/reference/cwin32heap-class.md)<br/>
[CLocalHeap Sınıfı](../../atl/reference/clocalheap-class.md)<br/>
[CGlobalHeap Sınıfı](../../atl/reference/cglobalheap-class.md)<br/>
[IAtlMemMgr Sınıfı](../../atl/reference/iatlmemmgr-class.md)
