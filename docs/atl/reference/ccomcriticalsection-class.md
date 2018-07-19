---
title: CComCriticalSection sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComCriticalSection
- ATLCORE/ATL::CComCriticalSection
- ATLCORE/ATL::CComCriticalSection::CComCriticalSection
- ATLCORE/ATL::CComCriticalSection::Init
- ATLCORE/ATL::CComCriticalSection::Lock
- ATLCORE/ATL::CComCriticalSection::Term
- ATLCORE/ATL::CComCriticalSection::Unlock
- ATLCORE/ATL::CComCriticalSection::m_sec
dev_langs:
- C++
helpviewer_keywords:
- CComCriticalSection class
ms.assetid: 44e1edd2-90be-4bfe-9739-58e8b419e7d1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5926f92ae636a13c1e5241792790151ee48ceddc
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37884876"
---
# <a name="ccomcriticalsection-class"></a>CComCriticalSection sınıfı
Bu sınıf, alma ve kritik bölüm nesnenin sahipliğini serbest için yöntemler sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CComCriticalSection
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComCriticalSection::CComCriticalSection](#ccomcriticalsection)|Oluşturucu.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComCriticalSection::Init](#init)|Oluşturur ve kritik bölüm nesnesi başlatır.|  
|[CComCriticalSection::Lock](#lock)|Kritik bölüm nesne sahipliğini alır.|  
|[CComCriticalSection::Term](#term)|Kritik bölüm nesne tarafından kullanılan sistem kaynaklarını serbest bırakır.|  
|[CComCriticalSection::Unlock](#unlock)|Kritik bölüm nesnenin sahipliğini serbest bırakır.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComCriticalSection::m_sec](#m_sec)|Bir CRITICAL_SECTION nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CComCriticalSection` sınıfına benzer [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md), siz açıkça başlatmak ve kritik bölüm yayın.  
  
 Genellikle, kullandığınız `CComCriticalSection` aracılığıyla **typedef** adı [CriticalSection](ccommultithreadmodel-class.md#criticalsection). Bu ada başvuran `CComCriticalSection` olduğunda [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) kullanılıyor.  

  
 Bkz: [CComCritSecLock sınıfı](../../atl/reference/ccomcritseclock-class.md) arama bu sınıf kullanmak daha güvenli bir şekilde `Lock` ve `Unlock` doğrudan.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcore.h  
  
##  <a name="ccomcriticalsection"></a>  CComCriticalSection::CComCriticalSection  
 Oluşturucu.  
  
```
CComCriticalSection() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Kümeleri [m_sec](#m_sec) veri üyesi null.  
  
##  <a name="init"></a>  CComCriticalSection::Init  
 Win32 işlevini çağırır [InitializeCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms683472), yer alan kritik bölüm nesnesi başlatır [m_sec](#m_sec) veri üyesi.  
  
```
HRESULT Init() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı, E_OUTOFMEMORY veya hata durumunda E_FAIL başarılıysa S_OK döndürür.  
  
##  <a name="lock"></a>  CComCriticalSection::Lock  
 Win32 işlevini çağırır [EnterCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms682608), iş parçacığı kritik bölüm nesnenin içerdiği sahipliğini alabilir kadar hangi bekler [m_sec](#m_sec) veri üyesi.  
  
```
HRESULT Lock() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı, E_OUTOFMEMORY veya hata durumunda E_FAIL başarılıysa S_OK döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Kritik bölüm nesnesi ilk çağrısı ile başlatılmalıdır [Init](#init) yöntemi. Korumalı kod yürütme sona erdiğinde, iş parçacığı çağırmalıdır [kilidini](#unlock) kritik bölüm sahipliğini serbest bırakmak için.  
  
##  <a name="m_sec"></a>  CComCriticalSection::m_sec  
 Tüm tarafından kullanılan kritik bölüm nesnesi içeren `CComCriticalSection` yöntemleri.  
  
```
CRITICAL_SECTION m_sec;
```  
  
##  <a name="term"></a>  CComCriticalSection::Term  
 Win32 işlevini çağırır [DeleteCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms682552), yer alan kritik bölüm nesnesi tarafından kullanılan tüm kaynakları serbest bırakır [m_sec](#m_sec) veri üyesi.  
  
```
HRESULT Term() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir kez `Term` çağrılıp çağrılmadığını, kritik bölüm için eşitlemeyi artık kullanılabilir.  
  
##  <a name="unlock"></a>  CComCriticalSection::Unlock  
 Win32 işlevini çağırır [LeaveCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms684169), yer alan kritik bölüm nesnenin sahipliğini serbest [m_sec](#m_sec) veri üyesi.  
  
```
HRESULT Unlock() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk sahipliğini almak için iş parçacığı çağırmalıdır [kilit](#lock) yöntemi. Her çağrı `Lock` karşılık gelen bir çağrı gerektirir `Unlock` kritik bölüm sahipliğini serbest bırakmak için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CComFakeCriticalSection sınıfı](../../atl/reference/ccomfakecriticalsection-class.md)   
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)   
 [CComCritSecLock Sınıfı](../../atl/reference/ccomcritseclock-class.md)
