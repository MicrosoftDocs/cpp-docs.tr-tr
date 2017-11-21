---
title: "CGlobalHeap sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CGlobalHeap
- ATLMEM/ATL::CGlobalHeap
- ATLMEM/ATL::CGlobalHeap::Allocate
- ATLMEM/ATL::CGlobalHeap::Free
- ATLMEM/ATL::CGlobalHeap::GetSize
- ATLMEM/ATL::CGlobalHeap::Reallocate
dev_langs: C++
helpviewer_keywords: CGlobalHeap class
ms.assetid: e348d838-3aa7-4bee-a1b3-cd000c99f834
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 693a0ce139c35b804325e9ef5dcb7beb1e4da6a1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cglobalheap-class"></a>CGlobalHeap sınıfı
Bu sınıf uygulayan [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) Win32 genel yığın işlevlerini kullanma.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CGlobalHeap : public IAtlMemMgr
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CGlobalHeap::Allocate](#allocate)|Bir bellek bloğu ayırmak için bu yöntemi çağırın.|  
|[CGlobalHeap::Free](#free)|Bu bellek yöneticisi tarafından ayrılan bellek bloğu boşaltmak için bu yöntemi çağırın.|  
|[CGlobalHeap::GetSize](#getsize)|Bu bellek yöneticisi tarafından ayrılan bellek bloğu ayrılmış boyutunu almak için bu yöntemi çağırın.|  
|[CGlobalHeap::Reallocate](#reallocate)|Bu bellek yöneticisi tarafından ayrılan belleği yeniden tahsis etmek için bu yöntemi çağırın.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CGlobalHeap`bellek ayırma işlevleri Win32 genel yığın işlevler kullanılarak uygular.  
  
> [!NOTE]
>  Genel heap işlevleri diğer bellek yönetimi işlevleri yavaş çalışır ve gibi birçok özellik sağlamaz. Bu nedenle, yeni uygulamalar kullanmalıdır [yığın işlevleri](http://msdn.microsoft.com/library/windows/desktop/aa366711). Bunlar kullanılabilir olan [CWin32Heap](../../atl/reference/cwin32heap-class.md) sınıfı. Genel işlevler hala DDE ve Pano işlevleri tarafından kullanılır.  
  
## <a name="example"></a>Örnek  
 Örneğin bkz [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IAtlMemMgr`  
  
 `CGlobalHeap`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlmem.h  
  
##  <a name="allocate"></a>CGlobalHeap::Allocate  
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
 Çağrı [CGlobalHeap::Free](#free) veya [CGlobalHeap::Reallocate](#reallocate) bu yöntem tarafından ayrılan bellek boşaltmak için.  
  
 Kullanılarak uygulanan [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574) bir bayrak parametresi ile **GMEM_FIXED**.  
  
##  <a name="free"></a>CGlobalHeap::Free  
 Bu bellek yöneticisi tarafından ayrılan bellek bloğu boşaltmak için bu yöntemi çağırın.  
  
```
virtual void Free(void* p) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `p`  
 Bu bellek yöneticisi tarafından önceden ayrılmış bellek işaretçisi. NULL geçerli bir değer ve hiçbir şey yapmaz.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanılarak uygulanan [GlobalFree](http://msdn.microsoft.com/library/windows/desktop/aa366579).  
  
##  <a name="getsize"></a>CGlobalHeap::GetSize  
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
 Kullanılarak uygulanan [GlobalSize](http://msdn.microsoft.com/library/windows/desktop/aa366593).  
  
##  <a name="reallocate"></a>CGlobalHeap::Reallocate  
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
 Çağrı [CGlobalHeap::Free](#free) bu yöntem tarafından ayrılan bellek boşaltmak için.  
  
 Kullanılarak uygulanan [GlobalReAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366590).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)   
 [CComHeap sınıfı](../../atl/reference/ccomheap-class.md)   
 [CWin32Heap sınıfı](../../atl/reference/cwin32heap-class.md)   
 [CLocalHeap sınıfı](../../atl/reference/clocalheap-class.md)   
 [CCRTHeap sınıfı](../../atl/reference/ccrtheap-class.md)   
 [IAtlMemMgr sınıfı](../../atl/reference/iatlmemmgr-class.md)
