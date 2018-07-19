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
ms.openlocfilehash: 68c99d1ef7b28a9325d59db2144be11fa63cc99f
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37883053"
---
# <a name="ccrtheap-class"></a>CCRTHeap sınıfı
Bu sınıfın uyguladığı [Iatlmemmgr](../../atl/reference/iatlmemmgr-class.md) CRT yığın işlevlerinin kullanarak.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CCRTHeap : public IAtlMemMgr
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CCRTHeap::Allocate](#allocate)|Bir bellek bloğu ayırmak için bu yöntemi çağırın.|  
|[CCRTHeap::Free](#free)|Bu bellek yöneticisi tarafından ayrılan bellek bloğunu serbest bırakmak için bu yöntemi çağırın.|  
|[CCRTHeap::GetSize](#getsize)|Bu bellek yöneticisi tarafından ayrılan bir bellek bloğu ayrılmış boyutunu almak için bu yöntemi çağırın.|  
|[CCRTHeap::Reallocate](#reallocate)|Bu bellek yöneticisi tarafından ayrılan bellek yeniden ayırmak üzere bu yöntemi çağırın.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CCRTHeap` CRT kullanarak ayırma işlevleri, İşlevler dahil olmak üzere, yığın bellek uygulayan [malloc](../../c-runtime-library/reference/malloc.md), [ücretsiz](../../c-runtime-library/reference/free.md), [realloc](../../c-runtime-library/reference/realloc.md), ve [_msize](../../c-runtime-library/reference/msize.md).  
  
## <a name="example"></a>Örnek  
 Örneğin bakın [Iatlmemmgr](../../atl/reference/iatlmemmgr-class.md).  
  
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
 *nBytes*  
 İstenen bayt yeni bellek bloğu sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni ayrılan bellek bloğu başlangıcı için bir işaretçi döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrı [CCRTHeap::Free](#free) veya [CCRTHeap::Reallocate](#reallocate) bu yöntem tarafından ayrılan bellek boşaltmak için.  
  
 Kullanılarak uygulanan [malloc](../../c-runtime-library/reference/malloc.md).  
  
##  <a name="free"></a>  CCRTHeap::Free  
 Bu bellek yöneticisi tarafından ayrılan bellek bloğunu serbest bırakmak için bu yöntemi çağırın.  
  
```
virtual void Free(void* p) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *p*  
 Bu bellek yöneticisi tarafından önceden ayrılan bellek işaretçisi. NULL, geçerli bir değer ve hiçbir şey yapmaz.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanılarak uygulanan [ücretsiz](../../c-runtime-library/reference/free.md).  
  
##  <a name="getsize"></a>  CCRTHeap::GetSize  
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
 Kullanılarak uygulanan [_msize](../../c-runtime-library/reference/msize.md).  
  
##  <a name="reallocate"></a>  CCRTHeap::Reallocate  
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
 Çağrı [CCRTHeap::Free](#free) bu yöntem tarafından ayrılan bellek boşaltmak için. Kullanılarak uygulanan [realloc](../../c-runtime-library/reference/realloc.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)   
 [CComHeap sınıfı](../../atl/reference/ccomheap-class.md)   
 [CWin32Heap sınıfı](../../atl/reference/cwin32heap-class.md)   
 [CLocalHeap sınıfı](../../atl/reference/clocalheap-class.md)   
 [CGlobalHeap sınıfı](../../atl/reference/cglobalheap-class.md)   
 [IAtlMemMgr Sınıfı](../../atl/reference/iatlmemmgr-class.md)
