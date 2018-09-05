---
title: CGlobalHeap sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CGlobalHeap
- ATLMEM/ATL::CGlobalHeap
- ATLMEM/ATL::CGlobalHeap::Allocate
- ATLMEM/ATL::CGlobalHeap::Free
- ATLMEM/ATL::CGlobalHeap::GetSize
- ATLMEM/ATL::CGlobalHeap::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- CGlobalHeap class
ms.assetid: e348d838-3aa7-4bee-a1b3-cd000c99f834
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b379cdff5f2f0b0e5bf00a6e67b9320cd5150f47
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43756170"
---
# <a name="cglobalheap-class"></a>CGlobalHeap sınıfı

Bu sınıfın uyguladığı [Iatlmemmgr](../../atl/reference/iatlmemmgr-class.md) Win32 genel yığın işlevlerini kullanma.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CGlobalHeap : public IAtlMemMgr
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CGlobalHeap::Allocate](#allocate)|Bir bellek bloğu ayırmak için bu yöntemi çağırın.|
|[CGlobalHeap::Free](#free)|Bu bellek yöneticisi tarafından ayrılan bellek bloğunu serbest bırakmak için bu yöntemi çağırın.|
|[CGlobalHeap::GetSize](#getsize)|Bu bellek yöneticisi tarafından ayrılan bir bellek bloğu ayrılmış boyutunu almak için bu yöntemi çağırın.|
|[CGlobalHeap::Reallocate](#reallocate)|Bu bellek yöneticisi tarafından ayrılan bellek yeniden ayırmak üzere bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

`CGlobalHeap` bellek ayırma işlevleri için Win32 genel yığın işlevlerini uygular.

> [!NOTE]
>  Genel yığın işlevleri diğer bellek yönetimi işlevleri yavaş çalışır ve gibi birçok özelliği sağlamaz. Bu nedenle, yeni uygulamalar kullanmalıdır [yığın işlevleri](/windows/desktop/Memory/heap-functions). Bunlar, kullanılabilir [CWin32Heap](../../atl/reference/cwin32heap-class.md) sınıfı. Genel İşlevler, yine de DDE ve Pano işlevleri tarafından kullanılır.

## <a name="example"></a>Örnek

Örneğin bakın [Iatlmemmgr](../../atl/reference/iatlmemmgr-class.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IAtlMemMgr`

`CGlobalHeap`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlmem.h

##  <a name="allocate"></a>  CGlobalHeap::Allocate

Bir bellek bloğu ayırmak için bu yöntemi çağırın.

```
virtual __declspec(allocator) void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>Parametreler

*nBytes*  
İstenen bayt yeni bellek bloğu sayısı.

### <a name="return-value"></a>Dönüş Değeri

Yeni ayrılan bellek bloğu başlangıcı için bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

Çağrı [CGlobalHeap::Free](#free) veya [CGlobalHeap::Reallocate](#reallocate) bu yöntem tarafından ayrılan bellek boşaltmak için.

Kullanılarak uygulanan [GlobalAlloc](/windows/desktop/api/winbase/nf-winbase-globalalloc) GMEM_FIXED bayrağı parametresi ile.

##  <a name="free"></a>  CGlobalHeap::Free

Bu bellek yöneticisi tarafından ayrılan bellek bloğunu serbest bırakmak için bu yöntemi çağırın.

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>Parametreler

*p*  
Bu bellek yöneticisi tarafından önceden ayrılan bellek işaretçisi. NULL, geçerli bir değer ve hiçbir şey yapmaz.

### <a name="remarks"></a>Açıklamalar

Kullanılarak uygulanan [GlobalFree](/windows/desktop/api/winbase/nf-winbase-globalfree).

##  <a name="getsize"></a>  CGlobalHeap::GetSize

Bu bellek yöneticisi tarafından ayrılan bir bellek bloğu ayrılmış boyutunu almak için bu yöntemi çağırın.

```
virtual size_t GetSize(void* p) throw();
```

### <a name="parameters"></a>Parametreler

*p*  
Bu bellek yöneticisi tarafından önceden ayrılan bellek işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Ayrılan bellek blok boyutu bayt cinsinden döndürür.

### <a name="remarks"></a>Açıklamalar

Kullanılarak uygulanan [GlobalSize](/windows/desktop/api/winbase/nf-winbase-globalsize).

##  <a name="reallocate"></a>  CGlobalHeap::Reallocate

Bu bellek yöneticisi tarafından ayrılan bellek yeniden ayırmak üzere bu yöntemi çağırın.

```
virtual __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>Parametreler

*p*  
Bu bellek yöneticisi tarafından önceden ayrılan bellek işaretçisi.

*nBytes*  
İstenen bayt yeni bellek bloğu sayısı.

### <a name="return-value"></a>Dönüş Değeri

Yeni ayrılan bellek bloğu başlangıcı için bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

Çağrı [CGlobalHeap::Free](#free) bu yöntem tarafından ayrılan bellek boşaltmak için.

Kullanılarak uygulanan [GlobalReAlloc](/windows/desktop/api/winbase/nf-winbase-globalrealloc).

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)   
[CComHeap sınıfı](../../atl/reference/ccomheap-class.md)   
[CWin32Heap sınıfı](../../atl/reference/cwin32heap-class.md)   
[CLocalHeap sınıfı](../../atl/reference/clocalheap-class.md)   
[CCRTHeap sınıfı](../../atl/reference/ccrtheap-class.md)   
[IAtlMemMgr Sınıfı](../../atl/reference/iatlmemmgr-class.md)
