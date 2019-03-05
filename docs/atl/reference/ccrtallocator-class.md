---
title: CCRTAllocator sınıfı
ms.date: 11/04/2016
f1_keywords:
- CCRTAllocator
- ATLCORE/ATL::CCRTAllocator
- ATLCORE/ATL::CCRTAllocator::Allocate
- ATLCORE/ATL::CCRTAllocator::Free
- ATLCORE/ATL::CCRTAllocator::Reallocate
helpviewer_keywords:
- CCRTAllocator class
ms.assetid: 3e1b8cb0-859a-41ab-8e93-6f0b5ceca49d
ms.openlocfilehash: c08d594e1c0f4d532f46961e266bf6ced98c51b2
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57287368"
---
# <a name="ccrtallocator-class"></a>CCRTAllocator sınıfı

Bu sınıf, CRT bellek yordamları kullanarak bellek yönetmek için yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
class ATL::CCRTAllocator
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CCRTAllocator::Allocate](#allocate)|(Statik) Bellek ayırmak için bu yöntemi çağırın.|
|[CCRTAllocator::Free](#free)|(Statik) Belleği boşaltmak için bu yöntemi çağırın.|
|[CCRTAllocator::Reallocate](#reallocate)|(Statik) Bellek yeniden ayırmak üzere bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf tarafından kullanılan [CHeapPtr](../../atl/reference/cheapptr-class.md) CRT bellek ayırma yordamlarını sağlamak için. Karşılık gelen sınıf [CComAllocator](../../atl/reference/ccomallocator-class.md), COM yordamları kullanarak aynı yöntemleri sağlar.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcore.h

##  <a name="allocate"></a>  CCRTAllocator::Allocate

Bellek ayırma için statik bu işlevi çağırın.

```
static __declspec(allocator) void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>Parametreler

*nBytes*<br/>
Ayrılacak bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Kullanılabilir bellek yetersiz ise bir void işaretçisine ayrılan alanı veya NULL döndürür.

### <a name="remarks"></a>Açıklamalar

Bellek ayırır. Bkz: [malloc](../../c-runtime-library/reference/malloc.md) daha fazla ayrıntı için.

##  <a name="free"></a>  CCRTAllocator::Free

Belleği boşaltmak için statik bu işlevi çağırın.

```
static void Free(void* p) throw();
```

### <a name="parameters"></a>Parametreler

*p*<br/>
Ayrılan bellek işaretçisi.

### <a name="remarks"></a>Açıklamalar

Ayrılan belleği serbest bırakır. Bkz: [ücretsiz](../../c-runtime-library/reference/free.md) daha fazla ayrıntı için.

##  <a name="reallocate"></a>  CCRTAllocator::Reallocate

Bellek yeniden ayırmak üzere statik bu işlevi çağırın.

```
static __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>Parametreler

*p*<br/>
Ayrılan bellek işaretçisi.

*nBytes*<br/>
Ayrılacak bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Yetersiz bellek varsa, ayrılmış alanı veya NULL void bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

Ayrılan bellek miktarını yeniden boyutlandırır. Bkz: [realloc](../../c-runtime-library/reference/realloc.md) daha fazla ayrıntı için.

## <a name="see-also"></a>Ayrıca bkz.

[CHeapPtr Sınıfı](../../atl/reference/cheapptr-class.md)<br/>
[CComAllocator Sınıfı](../../atl/reference/ccomallocator-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
