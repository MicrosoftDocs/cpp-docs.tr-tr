---
title: CCRTHeap sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CCRTHeap
- ATLMEM/ATL::CCRTHeap
- ATLMEM/ATL::CCRTHeap::Allocate
- ATLMEM/ATL::CCRTHeap::Free
- ATLMEM/ATL::CCRTHeap::GetSize
- ATLMEM/ATL::CCRTHeap::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- CCRTHeap class
ms.assetid: 321bd6c5-1856-4ff7-8590-95044a1209f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 83655bddfb56bdd0e532b520b2389278e3fbd762
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="ccrtheap-class"></a>CCRTHeap sınıfı
Bu sınıf uygulayan [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) CRT heap işlevleri kullanarak.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CCRTHeap : public IAtlMemMgr
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CCRTHeap::Allocate](#allocate)|Bir bellek bloğu ayırmak için bu yöntemi çağırın.|  
|[CCRTHeap::Free](#free)|Bu bellek yöneticisi tarafından ayrılan bellek bloğu boşaltmak için bu yöntemi çağırın.|  
|[CCRTHeap::GetSize](#getsize)|Bu bellek yöneticisi tarafından ayrılan bellek bloğu ayrılmış boyutunu almak için bu yöntemi çağırın.|  
|[CCRTHeap::Reallocate](#reallocate)|Bu bellek yöneticisi tarafından ayrılan belleği yeniden tahsis etmek için bu yöntemi çağırın.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CCRTHeap` bellek ayırma işlevleri CRT kullanarak yığın dahil işlevlerini uygulayan [malloc](../../c-runtime-library/reference/malloc.md), [ücretsiz](../../c-runtime-library/reference/free.md), [realloc](../../c-runtime-library/reference/realloc.md), ve [_msize](../../c-runtime-library/reference/msize.md).  
  
## <a name="example"></a>Örnek  
 Örneğin bkz [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IAtlMemMgr`  
  
 `CCRTHeap`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlmem.h  
  
##  <a name="allocate"></a>  CCRTHeap::Allocate  
 Bir bellek bloğu ayırmak için bu yöntemi çağırın.  
  
```
virtual __declspec(allocator) void* Allocate(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `nBytes`  
 İstenen yeni bellek bloğu içindeki bayt sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi yeni ayrılan bellek bloğu başlangıcını döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrı [CCRTHeap::Free](#free) veya [CCRTHeap::Reallocate](#reallocate) bu yöntem tarafından ayrılan bellek boşaltmak için.  
  
 Kullanılarak uygulanan [malloc](../../c-runtime-library/reference/malloc.md).  
  
##  <a name="free"></a>  CCRTHeap::Free  
 Bu bellek yöneticisi tarafından ayrılan bellek bloğu boşaltmak için bu yöntemi çağırın.  
  
```
virtual void Free(void* p) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `p`  
 Bu bellek yöneticisi tarafından önceden ayrılmış bellek işaretçisi. NULL geçerli bir değer ve hiçbir şey yapmaz.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanılarak uygulanan [ücretsiz](../../c-runtime-library/reference/free.md).  
  
##  <a name="getsize"></a>  CCRTHeap::GetSize  
 Bu bellek yöneticisi tarafından ayrılan bellek bloğu ayrılmış boyutunu almak için bu yöntemi çağırın.  
  
```
virtual size_t GetSize(void* p) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `p`  
 Bu bellek yöneticisi tarafından önceden ayrılmış bellek işaretçisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ayrılmış bellek blok boyutunu bayt cinsinden döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanılarak uygulanan [_msize](../../c-runtime-library/reference/msize.md).  
  
##  <a name="reallocate"></a>  CCRTHeap::Reallocate  
 Bu bellek yöneticisi tarafından ayrılan belleği yeniden tahsis etmek için bu yöntemi çağırın.  
  
```
virtual __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `p`  
 Bu bellek yöneticisi tarafından önceden ayrılmış bellek işaretçisi.  
  
 `nBytes`  
 İstenen yeni bellek bloğu içindeki bayt sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi yeni ayrılan bellek bloğu başlangıcını döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrı [CCRTHeap::Free](#free) bu yöntem tarafından ayrılan bellek boşaltmak için. Kullanılarak uygulanan [realloc](../../c-runtime-library/reference/realloc.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)   
 [CComHeap sınıfı](../../atl/reference/ccomheap-class.md)   
 [CWin32Heap sınıfı](../../atl/reference/cwin32heap-class.md)   
 [CLocalHeap sınıfı](../../atl/reference/clocalheap-class.md)   
 [CGlobalHeap sınıfı](../../atl/reference/cglobalheap-class.md)   
 [IAtlMemMgr Sınıfı](../../atl/reference/iatlmemmgr-class.md)
