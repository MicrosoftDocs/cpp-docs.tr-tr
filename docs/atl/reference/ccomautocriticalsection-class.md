---
title: "CComAutoCriticalSection sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComAutoCriticalSection
- ATLCORE/ATL::CComAutoCriticalSection
- ATLCORE/ATL::CComAutoCriticalSection::CComAutoCriticalSection
dev_langs:
- C++
helpviewer_keywords:
- CComAutoCriticalSection class
ms.assetid: 491a9d90-3398-4f90-88f5-fd2172a46b30
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d12abfceeebeb1cac89b510c14d7a9211173406e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ccomautocriticalsection-class"></a>CComAutoCriticalSection sınıfı
`CComAutoCriticalSection`Alma ve kritik bölüm nesnenin sahipliğini serbest bırakma için yöntemleri sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CComAutoCriticalSection : public CComCriticalSection
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComAutoCriticalSection::CComAutoCriticalSection](#ccomautocriticalsection)|Oluşturucu.|  
|[CComAutoCriticalSection:: ~ CComAutoCriticalSection](#dtor)|Yok Edicisi.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CComAutoCriticalSection`sınıfına benzer [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md), dışında `CComAutoCriticalSection` Oluşturucusu kritik bölüm nesnesinde otomatik olarak başlatır.  
  
 Genellikle, kullandığınız `CComAutoCriticalSection` aracılığıyla `typedef` adı [AutoCriticalSection](ccommultithreadmodel-class.md#autocriticalsection). Bu ad başvuran `CComAutoCriticalSection` zaman [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) kullanılıyor.  

  
 `Init` Ve `Term` yöntemleri [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) Bu sınıf kullanırken kullanılabilir değil.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)  
  
 `CComAutoCriticalSection`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcore.h  
  
##  <a name="ccomautocriticalsection"></a>CComAutoCriticalSection::CComAutoCriticalSection  
 Oluşturucu.  
  
```
CComAutoCriticalSection();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Win32 işlev çağrılarını [InitializeCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms683472), kritik bölüm nesnesini başlatır.  
  
##  <a name="dtor"></a>CComAutoCriticalSection:: ~ CComAutoCriticalSection  
 Yok Edicisi.  
  
```
~CComAutoCriticalSection() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yıkıcı çağrıları [DeleteCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms682552), kritik bölüm nesnesi tarafından kullanılan tüm sistem kaynakları serbest bırakır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CComFakeCriticalSection sınıfı](../../atl/reference/ccomfakecriticalsection-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)   
 [CComCriticalSection Sınıfı](../../atl/reference/ccomcriticalsection-class.md)
