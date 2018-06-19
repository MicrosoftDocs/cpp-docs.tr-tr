---
title: CComFakeCriticalSection sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a042e52439579cfb1b4145b1691f5a00128754c9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358621"
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
 `CComFakeCriticalSection` bulunan yöntemlerini yansıtan [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md). Ancak, `CComFakeCriticalSection` önemli bir bölümü; sağlamaz bu nedenle, yöntemlerinden hiçbir şey yapma.  
  
 Genellikle, kullandığınız `CComFakeCriticalSection` aracılığıyla bir `typedef` ya da ad `AutoCriticalSection` veya `CriticalSection`. Kullanırken [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) veya [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md), bunların her ikisi de `typedef` adları başvuru `CComFakeCriticalSection`. Kullanırken [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md), oldukları [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md) ve `CComCriticalSection`sırasıyla.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcore.h  
  
##  <a name="init"></a>  CComFakeCriticalSection::Init  
 Önemli bir bölümü olmadığından, hiçbir şey yapmaz.  
  
```
HRESULT Init() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK döndürür.  
  
##  <a name="lock"></a>  CComFakeCriticalSection::Lock  
 Önemli bir bölümü olmadığından, hiçbir şey yapmaz.  
  
```
HRESULT Lock() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK döndürür.  
  
##  <a name="term"></a>  CComFakeCriticalSection::Term  
 Önemli bir bölümü olmadığından, hiçbir şey yapmaz.  
  
```
HRESULT Term() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK döndürür.  
  
##  <a name="unlock"></a>  CComFakeCriticalSection::Unlock  
 Önemli bir bölümü olmadığından, hiçbir şey yapmaz.  
  
```
HRESULT Unlock() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
