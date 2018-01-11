---
title: "CComHeap sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComHeap
- ATLCOMMEM/ATL::CComHeap
- ATLCOMMEM/ATL::CComHeap::Allocate
- ATLCOMMEM/ATL::CComHeap::Free
- ATLCOMMEM/ATL::CComHeap::GetSize
- ATLCOMMEM/ATL::CComHeap::Reallocate
dev_langs: C++
helpviewer_keywords: CComHeap class
ms.assetid: c74183ce-98ae-46fb-b186-93ea4cf0222b
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3cf86ebe45cdb0a70af6eebaaed90690e83e8db7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ccomheap-class"></a>CComHeap sınıfı
Bu sınıf uygulayan [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) COM bellek ayırma işlevlerini kullanma.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CComHeap : public IAtlMemMgr
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComHeap::Allocate](#allocate)|Bir bellek bloğu ayırmak için bu yöntemi çağırın.|  
|[CComHeap::Free](#free)|Bu bellek yöneticisi tarafından ayrılan bellek bloğu boşaltmak için bu yöntemi çağırın.|  
|[CComHeap::GetSize](#getsize)|Bu bellek yöneticisi tarafından ayrılan bellek bloğu ayrılmış boyutunu almak için bu yöntemi çağırın.|  
|[CComHeap::Reallocate](#reallocate)|Bu bellek yöneticisi tarafından ayrılan belleği yeniden tahsis etmek için bu yöntemi çağırın.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CComHeap`bellek ayırma işlevleri dahil olmak üzere COM ayırma işlevlerini kullanarak uygulayan [CoTaskMemAlloc](http://msdn.microsoft.com/library/windows/desktop/ms692727), [CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722), [IMalloc::GetSize](http://msdn.microsoft.com/library/windows/desktop/ms691226)ve [CoTaskMemRealloc](http://msdn.microsoft.com/library/windows/desktop/ms687280). Ayrılabilen maksimum belleğin eşittir **INT_MAX** (2147483647) bayt sayısı.  
  
## <a name="example"></a>Örnek  
 Örneğin bkz [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IAtlMemMgr`  
  
 `CComHeap`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** ATLComMem.h  
  
##  <a name="allocate"></a>CComHeap::Allocate  
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
 Çağrı [CComHeap::Free](#free) veya [CComHeap::Reallocate](#reallocate) bu yöntem tarafından ayrılan bellek boşaltmak için.  
  
 Kullanılarak uygulanan [CoTaskMemAlloc](http://msdn.microsoft.com/library/windows/desktop/ms692727).  
  
##  <a name="free"></a>CComHeap::Free  
 Bu bellek yöneticisi tarafından ayrılan bellek bloğu boşaltmak için bu yöntemi çağırın.  
  
```
virtual void Free(void* p) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `p`  
 Bu bellek yöneticisi tarafından önceden ayrılmış bellek işaretçisi. NULL geçerli bir değer ve hiçbir şey yapmaz.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanılarak uygulanan [CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722).  
  
##  <a name="getsize"></a>CComHeap::GetSize  
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
 Kullanılarak uygulanan [IMalloc::GetSize](http://msdn.microsoft.com/library/windows/desktop/ms691226).  
  
##  <a name="reallocate"></a>CComHeap::Reallocate  
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
 Çağrı [CComHeap::Free](#free) bu yöntem tarafından ayrılan bellek boşaltmak için.  
  
 Kullanılarak uygulanan [CoTaskMemRealloc](http://msdn.microsoft.com/library/windows/desktop/ms687280).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DynamicConsumer örnek](../../visual-cpp-samples.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)   
 [CWin32Heap sınıfı](../../atl/reference/cwin32heap-class.md)   
 [CLocalHeap sınıfı](../../atl/reference/clocalheap-class.md)   
 [CGlobalHeap sınıfı](../../atl/reference/cglobalheap-class.md)   
 [CCRTHeap sınıfı](../../atl/reference/ccrtheap-class.md)   
 [IAtlMemMgr Sınıfı](../../atl/reference/iatlmemmgr-class.md)
