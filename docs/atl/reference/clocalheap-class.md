---
title: CLocalHeap sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CLocalHeap
- ATLMEM/ATL::CLocalHeap
- ATLMEM/ATL::CLocalHeap::Allocate
- ATLMEM/ATL::CLocalHeap::Free
- ATLMEM/ATL::CLocalHeap::GetSize
- ATLMEM/ATL::CLocalHeap::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- CLocalHeap class
ms.assetid: 1ffa87a5-5fc8-4f8d-8809-58e87e963bd2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 54ded1ccb86a7580cf8f004c1f61a82c876eccbe
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43760912"
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

*nBytes*  
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

*p*  
Bu bellek yöneticisi tarafından önceden ayrılan bellek işaretçisi. NULL, geçerli bir değer ve hiçbir şey yapmaz.

### <a name="remarks"></a>Açıklamalar

Kullanılarak uygulanan [LocalFree](/windows/desktop/api/winbase/nf-winbase-localfree).

##  <a name="getsize"></a>  CLocalHeap::GetSize

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

Kullanılarak uygulanan [LocalSize](/windows/desktop/api/winbase/nf-winbase-localsize).

##  <a name="reallocate"></a>  CLocalHeap::Reallocate

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

Çağrı [CLocalHeap::Free](#free) bu yöntem tarafından ayrılan bellek boşaltmak için.

Kullanılarak uygulanan [LocalReAlloc](/windows/desktop/api/winbase/nf-winbase-localrealloc).

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)   
[CComHeap sınıfı](../../atl/reference/ccomheap-class.md)   
[CWin32Heap sınıfı](../../atl/reference/cwin32heap-class.md)   
[CGlobalHeap sınıfı](../../atl/reference/cglobalheap-class.md)   
[CCRTHeap sınıfı](../../atl/reference/ccrtheap-class.md)   
[IAtlMemMgr Sınıfı](../../atl/reference/iatlmemmgr-class.md)
