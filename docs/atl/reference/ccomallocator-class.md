---
title: CComAllocator sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComAllocator
- ATLBASE/ATL::CComAllocator
- ATLBASE/ATL::CComAllocator::Allocate
- ATLBASE/ATL::CComAllocator::Free
- ATLBASE/ATL::CComAllocator::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- CComAllocator class
ms.assetid: 0cd706fd-0c7b-42d3-9054-febe2966fc8e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f867d3a7ca81d190ee363c7539e56a62004eb377
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46088949"
---
# <a name="ccomallocator-class"></a>CComAllocator sınıfı

Bu sınıf, COM bellek yordamları kullanarak bellek yönetmek için yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CComAllocator
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComAllocator::Allocate](#allocate)|Bellek ayırma için statik bu yöntemi çağırın.|
|[CComAllocator::Free](#free)|Ayrılmış belleği boşaltmak için statik bu yöntemi çağırın.|
|[CComAllocator::Reallocate](#reallocate)|Bellek yeniden ayırmak üzere statik bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf tarafından kullanılan [CComHeapPtr](../../atl/reference/ccomheapptr-class.md) COM bellek ayırma yordamlarını sağlamak için. Karşılık gelen sınıf [CCRTAllocator](../../atl/reference/ccrtallocator-class.md), CRT yordamları kullanarak aynı yöntemleri sağlar.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlbase.h

##  <a name="allocate"></a>  CComAllocator::Allocate

Bellek ayırma için statik bu işlevi çağırın.

```
static void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>Parametreler

*nBytes*<br/>
Ayrılacak bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Kullanılabilir bellek yetersiz ise bir void işaretçisine ayrılan alanı veya NULL döndürür.

### <a name="remarks"></a>Açıklamalar

Bellek ayırır. Bkz: [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) daha fazla ayrıntı için.

##  <a name="free"></a>  CComAllocator::Free

Ayrılmış belleği boşaltmak için statik bu işlevi çağırın.

```
static void Free(void* p) throw();
```

### <a name="parameters"></a>Parametreler

*p*<br/>
Ayrılan bellek işaretçisi.

### <a name="remarks"></a>Açıklamalar

Ayrılan belleği serbest bırakır. Bkz: [CoTaskMemFree](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemfree) daha fazla ayrıntı için.

##  <a name="reallocate"></a>  CComAllocator::Reallocate

Bellek yeniden ayırmak üzere statik bu işlevi çağırın.

```
static void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>Parametreler

*p*<br/>
Ayrılan bellek işaretçisi.

*nBytes*<br/>
Ayrılacak bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Yetersiz bellek varsa void bir işaretçi ayrılan alanı veya NULL döndürür.

### <a name="remarks"></a>Açıklamalar

Ayrılan bellek miktarını yeniden boyutlandırır. Bkz: [CoTaskMemRealloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemrealloc) daha fazla ayrıntı için.

## <a name="see-also"></a>Ayrıca Bkz.

[CComHeapPtr Sınıfı](../../atl/reference/ccomheapptr-class.md)<br/>
[CCRTAllocator Sınıfı](../../atl/reference/ccrtallocator-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
