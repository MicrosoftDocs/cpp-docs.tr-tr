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
ms.openlocfilehash: 9dbaa4631e50b14131418b902dd008e74060dbf6
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37881938"
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
 *nBytes*  
 Ayrılacak bayt sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kullanılabilir bellek yetersiz ise bir void işaretçisine ayrılan alanı veya NULL döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bellek ayırır. Bkz: [CoTaskMemAlloc](http://msdn.microsoft.com/library/windows/desktop/ms692727) daha fazla ayrıntı için.  
  
##  <a name="free"></a>  CComAllocator::Free  
 Ayrılmış belleği boşaltmak için statik bu işlevi çağırın.  
  
```
static void Free(void* p) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *p*  
 Ayrılan bellek işaretçisi.  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrılan belleği serbest bırakır. Bkz: [CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722) daha fazla ayrıntı için.  
  
##  <a name="reallocate"></a>  CComAllocator::Reallocate  
 Bellek yeniden ayırmak üzere statik bu işlevi çağırın.  
  
```
static void* Reallocate(void* p, size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *p*  
 Ayrılan bellek işaretçisi.  
  
 *nBytes*  
 Ayrılacak bayt sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yetersiz bellek varsa void bir işaretçi ayrılan alanı veya NULL döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrılan bellek miktarını yeniden boyutlandırır. Bkz: [CoTaskMemRealloc](http://msdn.microsoft.com/library/windows/desktop/ms687280) daha fazla ayrıntı için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CComHeapPtr sınıfı](../../atl/reference/ccomheapptr-class.md)   
 [CCRTAllocator sınıfı](../../atl/reference/ccrtallocator-class.md)   
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)
