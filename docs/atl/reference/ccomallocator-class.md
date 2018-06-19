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
ms.openlocfilehash: 3606df325bfd41dabf99bb790ff154b383ab987f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358283"
---
# <a name="ccomallocator-class"></a>CComAllocator sınıfı
Bu sınıf COM bellek yordamları kullanarak bellek yönetme için yöntemleri sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CComAllocator
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComAllocator::Allocate](#allocate)|Bellek ayırma için statik bu yöntemi çağırın.|  
|[CComAllocator::Free](#free)|Ayrılmış Bellek boşaltmak için statik bu yöntemi çağırın.|  
|[CComAllocator::Reallocate](#reallocate)|Belleği yeniden tahsis için statik bu yöntemi çağırın.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf tarafından kullanılan [CComHeapPtr](../../atl/reference/ccomheapptr-class.md) COM bellek ayırma yordamları sağlamak için. Karşılık gelen sınıf [CCRTAllocator](../../atl/reference/ccrtallocator-class.md), CRT yordamları kullanarak aynı yöntemleri sağlar.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  
  
##  <a name="allocate"></a>  CComAllocator::Allocate  
 Bellek ayırmak için bu statik işlevini çağırın.  
  
```
static void* Allocate(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `nBytes`  
 Ayrılacak bayt sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kullanılabilir bellek yetersiz ise bir void işaretçi ayrılan alan veya NULL döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bellek ayırır. Bkz: [CoTaskMemAlloc](http://msdn.microsoft.com/library/windows/desktop/ms692727) daha fazla ayrıntı için.  
  
##  <a name="free"></a>  CComAllocator::Free  
 Ayrılmış Bellek boşaltmak için bu statik işlevini çağırın.  
  
```
static void Free(void* p) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `p`  
 Ayrılmış bellek işaretçisi.  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrılmış bellek boşaltır. Bkz: [CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722) daha fazla ayrıntı için.  
  
##  <a name="reallocate"></a>  CComAllocator::Reallocate  
 Bellek yeniden ayırmak üzere bu statik işlevini çağırın.  
  
```
static void* Reallocate(void* p, size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `p`  
 Ayrılmış bellek işaretçisi.  
  
 `nBytes`  
 Yeniden ayırmak üzere bayt sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bellek yetersiz ise bir void işaretçi ayrılan alan veya NULL döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrılmış bellek miktarı göre yeniden boyutlandırır. Bkz: [CoTaskMemRealloc](http://msdn.microsoft.com/library/windows/desktop/ms687280) daha fazla ayrıntı için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CComHeapPtr sınıfı](../../atl/reference/ccomheapptr-class.md)   
 [CCRTAllocator sınıfı](../../atl/reference/ccrtallocator-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
