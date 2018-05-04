---
title: CComAutoCriticalSection sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ae0c3cd1d00ce83a4e952d60a978663bfa76f814
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="ccomautocriticalsection-class"></a>CComAutoCriticalSection sınıfı
`CComAutoCriticalSection` Alma ve kritik bölüm nesnenin sahipliğini serbest bırakma için yöntemleri sağlar.  
  
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
 `CComAutoCriticalSection` sınıfına benzer [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md), dışında `CComAutoCriticalSection` Oluşturucusu kritik bölüm nesnesinde otomatik olarak başlatır.  
  
 Genellikle, kullandığınız `CComAutoCriticalSection` aracılığıyla `typedef` adı [AutoCriticalSection](ccommultithreadmodel-class.md#autocriticalsection). Bu ad başvuran `CComAutoCriticalSection` zaman [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) kullanılıyor.  

  
 `Init` Ve `Term` yöntemleri [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) Bu sınıf kullanırken kullanılabilir değil.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)  
  
 `CComAutoCriticalSection`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcore.h  
  
##  <a name="ccomautocriticalsection"></a>  CComAutoCriticalSection::CComAutoCriticalSection  
 Oluşturucu.  
  
```
CComAutoCriticalSection();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Win32 işlev çağrılarını [InitializeCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms683472), kritik bölüm nesnesini başlatır.  
  
##  <a name="dtor"></a>  CComAutoCriticalSection:: ~ CComAutoCriticalSection  
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
