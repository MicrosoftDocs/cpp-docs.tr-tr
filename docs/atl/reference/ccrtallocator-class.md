---
title: CCRTAllocator sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CCRTAllocator
- ATLCORE/ATL::CCRTAllocator
- ATLCORE/ATL::CCRTAllocator::Allocate
- ATLCORE/ATL::CCRTAllocator::Free
- ATLCORE/ATL::CCRTAllocator::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- CCRTAllocator class
ms.assetid: 3e1b8cb0-859a-41ab-8e93-6f0b5ceca49d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2f92ae3f4041b143a8cc4d58b1060c7d5b9a7bb4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="ccrtallocator-class"></a>CCRTAllocator sınıfı
Bu sınıf CRT bellek yordamları kullanarak bellek yönetme için yöntemleri sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class ATL::CCRTAllocator
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CCRTAllocator::Allocate](#allocate)|(Statik) Bellek ayırma için bu yöntemi çağırın.|  
|[CCRTAllocator::Free](#free)|(Statik) Belleği boşaltmak için bu yöntemi çağırın.|  
|[CCRTAllocator::Reallocate](#reallocate)|(Statik) Belleği yeniden tahsis için bu yöntemi çağırın.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf tarafından kullanılan [CHeapPtr](../../atl/reference/cheapptr-class.md) CRT bellek ayırma yordamları sağlamak için. Karşılık gelen sınıf [CComAllocator](../../atl/reference/ccomallocator-class.md), COM yordamları kullanarak aynı yöntemleri sağlar.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcore.h  
  
##  <a name="allocate"></a>  CCRTAllocator::Allocate  
 Bellek ayırmak için bu statik işlevini çağırın.  
  
```
static __declspec(allocator) void* Allocate(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `nBytes`  
 Ayrılacak bayt sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kullanılabilir bellek yetersiz ise bir void işaretçi ayrılan alan veya NULL döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bellek ayırır. Bkz: [malloc](../../c-runtime-library/reference/malloc.md) daha fazla ayrıntı için.  
  
##  <a name="free"></a>  CCRTAllocator::Free  
 Belleği boşaltmak için bu statik işlevini çağırın.  
  
```
static void Free(void* p) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `p`  
 Ayrılmış bellek işaretçisi.  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrılmış bellek boşaltır. Bkz: [ücretsiz](../../c-runtime-library/reference/free.md) daha fazla ayrıntı için.  
  
##  <a name="reallocate"></a>  CCRTAllocator::Reallocate  
 Bellek yeniden ayırmak üzere bu statik işlevini çağırın.  
  
```
static __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `p`  
 Ayrılmış bellek işaretçisi.  
  
 `nBytes`  
 Yeniden ayırmak üzere bayt sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bellek yetersiz ise bir void işaretçi ayrılan alan veya NULL döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrılmış bellek miktarı göre yeniden boyutlandırır. Bkz: [realloc](../../c-runtime-library/reference/realloc.md) daha fazla ayrıntı için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CHeapPtr sınıfı](../../atl/reference/cheapptr-class.md)   
 [CComAllocator sınıfı](../../atl/reference/ccomallocator-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
