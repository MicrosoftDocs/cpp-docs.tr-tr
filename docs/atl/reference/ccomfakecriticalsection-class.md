---
title: "CComFakeCriticalSection sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComFakeCriticalSection
- ATLCORE/ATL::CComFakeCriticalSection
- ATLCORE/ATL::CComFakeCriticalSection::Init
- ATLCORE/ATL::CComFakeCriticalSection::Lock
- ATLCORE/ATL::CComFakeCriticalSection::Term
- ATLCORE/ATL::CComFakeCriticalSection::Unlock
dev_langs:
- C++
helpviewer_keywords:
- CComFakeCriticalSection class
ms.assetid: a4811b97-96bb-493b-ab9f-62822aeddb10
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8b9f7b3b56193100d21ef7aebaba0ab6d9ecfd5b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ccomfakecriticalsection-class"></a>CComFakeCriticalSection sınıfı
Bu sınıfın sağladığı olarak aynı yöntemlerle [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) önemli bir bölümü sağlamaz, ancak.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CComFakeCriticalSection
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComFakeCriticalSection::Init](#init)|Önemli bir bölümü olmadığından, hiçbir şey yapmaz.|  
|[CComFakeCriticalSection::Lock](#lock)|Önemli bir bölümü olmadığından, hiçbir şey yapmaz.|  
|[CComFakeCriticalSection::Term](#term)|Önemli bir bölümü olmadığından, hiçbir şey yapmaz.|  
|[CComFakeCriticalSection::Unlock](#unlock)|Önemli bir bölümü olmadığından, hiçbir şey yapmaz.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CComFakeCriticalSection`bulunan yöntemlerini yansıtan [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md). Ancak, `CComFakeCriticalSection` önemli bir bölümü; sağlamaz bu nedenle, yöntemlerinden hiçbir şey yapma.  
  
 Genellikle, kullandığınız `CComFakeCriticalSection` aracılığıyla bir `typedef` ya da ad `AutoCriticalSection` veya `CriticalSection`. Kullanırken [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) veya [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md), bunların her ikisi de `typedef` adları başvuru `CComFakeCriticalSection`. Kullanırken [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md), oldukları [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md) ve `CComCriticalSection`sırasıyla.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcore.h  
  
##  <a name="init"></a>CComFakeCriticalSection::Init  
 Önemli bir bölümü olmadığından, hiçbir şey yapmaz.  
  
```
HRESULT Init() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK döndürür.  
  
##  <a name="lock"></a>CComFakeCriticalSection::Lock  
 Önemli bir bölümü olmadığından, hiçbir şey yapmaz.  
  
```
HRESULT Lock() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK döndürür.  
  
##  <a name="term"></a>CComFakeCriticalSection::Term  
 Önemli bir bölümü olmadığından, hiçbir şey yapmaz.  
  
```
HRESULT Term() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK döndürür.  
  
##  <a name="unlock"></a>CComFakeCriticalSection::Unlock  
 Önemli bir bölümü olmadığından, hiçbir şey yapmaz.  
  
```
HRESULT Unlock() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
