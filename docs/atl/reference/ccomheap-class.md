---
title: CComHeap sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComHeap
- ATLCOMMEM/ATL::CComHeap
- ATLCOMMEM/ATL::CComHeap::Allocate
- ATLCOMMEM/ATL::CComHeap::Free
- ATLCOMMEM/ATL::CComHeap::GetSize
- ATLCOMMEM/ATL::CComHeap::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- CComHeap class
ms.assetid: c74183ce-98ae-46fb-b186-93ea4cf0222b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cf09696f6a13c11fbb37fa6e89ccb9b1241cadd0
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43751549"
---
# <a name="ccomheap-class"></a>CComHeap sınıfı

Bu sınıfın uyguladığı [Iatlmemmgr](../../atl/reference/iatlmemmgr-class.md) COM bellek ayırma işlevlerini kullanma.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CComHeap : public IAtlMemMgr
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComHeap::Allocate](#allocate)|Bir bellek bloğu ayırmak için bu yöntemi çağırın.|
|[CComHeap::Free](#free)|Bu bellek yöneticisi tarafından ayrılan bellek bloğunu serbest bırakmak için bu yöntemi çağırın.|
|[CComHeap::GetSize](#getsize)|Bu bellek yöneticisi tarafından ayrılan bir bellek bloğu ayrılmış boyutunu almak için bu yöntemi çağırın.|
|[CComHeap::Reallocate](#reallocate)|Bu bellek yöneticisi tarafından ayrılan bellek yeniden ayırmak üzere bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

`CComHeap` bellek ayırma işlevleri dahil olmak üzere COM ayırma işlevlerini kullanarak uygulayan [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc), [CoTaskMemFree](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemfree), [IMalloc::GetSize](/windows/desktop/api/objidlbase/nf-objidlbase-imalloc-getsize)ve [CoTaskMemRealloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemrealloc). INT_MAX (2147483647) bayt için ayrılan maksimum belleğin eşittir.

## <a name="example"></a>Örnek

Örneğin bakın [Iatlmemmgr](../../atl/reference/iatlmemmgr-class.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IAtlMemMgr`

`CComHeap`

## <a name="requirements"></a>Gereksinimler

**Başlık:** ATLComMem.h

##  <a name="allocate"></a>  CComHeap::Allocate

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

Çağrı [CComHeap::Free](#free) veya [CComHeap::Reallocate](#reallocate) bu yöntem tarafından ayrılan bellek boşaltmak için.

Kullanılarak uygulanan [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc).

##  <a name="free"></a>  CComHeap::Free

Bu bellek yöneticisi tarafından ayrılan bellek bloğunu serbest bırakmak için bu yöntemi çağırın.

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>Parametreler

*p*  
Bu bellek yöneticisi tarafından önceden ayrılan bellek işaretçisi. NULL, geçerli bir değer ve hiçbir şey yapmaz.

### <a name="remarks"></a>Açıklamalar

Kullanılarak uygulanan [CoTaskMemFree](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemfree).

##  <a name="getsize"></a>  CComHeap::GetSize

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

Kullanılarak uygulanan [IMalloc::GetSize](/windows/desktop/api/objidlbase/nf-objidlbase-imalloc-getsize).

##  <a name="reallocate"></a>  CComHeap::Reallocate

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

Çağrı [CComHeap::Free](#free) bu yöntem tarafından ayrılan bellek boşaltmak için.

Kullanılarak uygulanan [CoTaskMemRealloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemrealloc).

## <a name="see-also"></a>Ayrıca Bkz.

[DynamicConsumer örnek](../../visual-cpp-samples.md)   
[Sınıfına genel bakış](../../atl/atl-class-overview.md)   
[CWin32Heap sınıfı](../../atl/reference/cwin32heap-class.md)   
[CLocalHeap sınıfı](../../atl/reference/clocalheap-class.md)   
[CGlobalHeap sınıfı](../../atl/reference/cglobalheap-class.md)   
[CCRTHeap sınıfı](../../atl/reference/ccrtheap-class.md)   
[IAtlMemMgr Sınıfı](../../atl/reference/iatlmemmgr-class.md)
