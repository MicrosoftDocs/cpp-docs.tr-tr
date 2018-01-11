---
title: "CLocalHeap sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CLocalHeap
- ATLMEM/ATL::CLocalHeap
- ATLMEM/ATL::CLocalHeap::Allocate
- ATLMEM/ATL::CLocalHeap::Free
- ATLMEM/ATL::CLocalHeap::GetSize
- ATLMEM/ATL::CLocalHeap::Reallocate
dev_langs: C++
helpviewer_keywords: CLocalHeap class
ms.assetid: 1ffa87a5-5fc8-4f8d-8809-58e87e963bd2
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5307e0e6e8925bcbbfa7a03d0140c3a5a08baff9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="clocalheap-class"></a>CLocalHeap sınıfı
Bu sınıf uygulayan [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) Win32 yerel yığın işlevlerini kullanma.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CLocalHeap : public IAtlMemMgr
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CLocalHeap::Allocate](#allocate)|Bir bellek bloğu ayırmak için bu yöntemi çağırın.|  
|[CLocalHeap::Free](#free)|Bu bellek yöneticisi tarafından ayrılan bellek bloğu boşaltmak için bu yöntemi çağırın.|  
|[CLocalHeap::GetSize](#getsize)|Bu bellek yöneticisi tarafından ayrılan bellek bloğu ayrılmış boyutunu almak için bu yöntemi çağırın.|  
|[CLocalHeap::Reallocate](#reallocate)|Bu bellek yöneticisi tarafından ayrılan belleği yeniden tahsis etmek için bu yöntemi çağırın.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CLocalHeap`bellek ayırma işlevleri Win32 yerel yığın işlevler kullanılarak uygular.  
  
> [!NOTE]
>  Yerel yığın işlevleri diğer bellek yönetimi işlevleri yavaş çalışır ve gibi birçok özellik sağlamaz. Bu nedenle, yeni uygulamalar kullanmalıdır [yığın işlevleri](http://msdn.microsoft.com/library/windows/desktop/aa366711). Bunlar kullanılabilir olan [CWin32Heap](../../atl/reference/cwin32heap-class.md) sınıfı.  
  
## <a name="example"></a>Örnek  
 Örneğin bkz [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IAtlMemMgr`  
  
 `CLocalHeap`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlmem.h  
  
##  <a name="allocate"></a>CLocalHeap::Allocate  
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
 Çağrı [CLocalHeap::Free](#free) veya [CLocalHeap::Reallocate](#reallocate) bu yöntem tarafından ayrılan bellek boşaltmak için.  
  
 Kullanılarak uygulanan [LocalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366723) bir bayrak parametresi ile **LMEM_FIXED**.  
  
##  <a name="free"></a>CLocalHeap::Free  
 Bu bellek yöneticisi tarafından ayrılan bellek bloğu boşaltmak için bu yöntemi çağırın.  
  
```
virtual void Free(void* p) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `p`  
 Bu bellek yöneticisi tarafından önceden ayrılmış bellek işaretçisi. NULL geçerli bir değer ve hiçbir şey yapmaz.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanılarak uygulanan [LocalFree](http://msdn.microsoft.com/library/windows/desktop/aa366730).  
  
##  <a name="getsize"></a>CLocalHeap::GetSize  
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
 Kullanılarak uygulanan [LocalSize](http://msdn.microsoft.com/library/windows/desktop/aa366745).  
  
##  <a name="reallocate"></a>CLocalHeap::Reallocate  
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
 Çağrı [CLocalHeap::Free](#free) bu yöntem tarafından ayrılan bellek boşaltmak için.  
  
 Kullanılarak uygulanan [LocalReAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366742).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)   
 [CComHeap sınıfı](../../atl/reference/ccomheap-class.md)   
 [CWin32Heap sınıfı](../../atl/reference/cwin32heap-class.md)   
 [CGlobalHeap sınıfı](../../atl/reference/cglobalheap-class.md)   
 [CCRTHeap sınıfı](../../atl/reference/ccrtheap-class.md)   
 [IAtlMemMgr Sınıfı](../../atl/reference/iatlmemmgr-class.md)
