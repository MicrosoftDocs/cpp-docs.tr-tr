---
title: "CComCriticalSection sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
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
dev_langs: C++
helpviewer_keywords: CComCriticalSection class
ms.assetid: 44e1edd2-90be-4bfe-9739-58e8b419e7d1
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 827ba99a141799af42fab65c36df1f22d212260a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ccomcriticalsection-class"></a>CComCriticalSection sınıfı
Bu sınıf, alma ve kritik bölüm nesnenin sahipliğini serbest bırakma için yöntemleri sağlar.  
  
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
|[CComCriticalSection::Init](#init)|Oluşturur ve kritik bölüm nesnesini başlatır.|  
|[CComCriticalSection::Lock](#lock)|Kritik bölüm nesnenin sahipliğini alır.|  
|[CComCriticalSection::Term](#term)|Kritik bölüm nesnesi tarafından kullanılan sistem kaynaklarını serbest bırakır.|  
|[CComCriticalSection::Unlock](#unlock)|Kritik bölüm nesnenin sahipliğini serbest bırakır.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComCriticalSection::m_sec](#m_sec)|A **CRITICAL_SECTION** nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CComCriticalSection`sınıfına benzer [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md), siz açıkça başlatmak ve kritik bölüm yayın dışında.  
  
 Genellikle, kullandığınız `CComCriticalSection` aracılığıyla `typedef` adı [CriticalSection](ccommultithreadmodel-class.md#criticalsection). Bu ad başvuran `CComCriticalSection` zaman [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) kullanılıyor.  

  
 Bkz: [CComCritSecLock sınıfı](../../atl/reference/ccomcritseclock-class.md) arama daha bu sınıfını kullanmak daha güvenli bir yol `Lock` ve `Unlock` doğrudan.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcore.h  
  
##  <a name="ccomcriticalsection"></a>CComCriticalSection::CComCriticalSection  
 Oluşturucu.  
  
```
CComCriticalSection() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayarlar [m_sec](#m_sec) veri üyesi null **.**  
  
##  <a name="init"></a>CComCriticalSection::Init  
 Win32 işlev çağrılarını [InitializeCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms683472), içinde yer alan kritik bölüm nesnesini başlatır [m_sec](#m_sec) veri üyesi.  
  
```
HRESULT Init() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK` başarılı, **E_OUTOFMEMORY** veya **E_FAIL** hatasında.  
  
##  <a name="lock"></a>CComCriticalSection::Lock  
 Win32 işlev çağrılarını [EnterCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms682608), iş parçacığı içinde yer alan kritik bölüm nesnenin sahipliğini alabilir kadar hangi bekler [m_sec](#m_sec) veri üyesi.  
  
```
HRESULT Lock() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK` başarılı, **E_OUTOFMEMORY** veya **E_FAIL** hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 Kritik bölüm nesnesi çağrısıyla önce başlatılmalıdır [Init](#init) yöntemi. Korumalı kod yürütme tamamlandığında, iş parçacığı çağırmalısınız [Unlock](#unlock) kritik bölüm sahipliğini serbest bırakmak için.  
  
##  <a name="m_sec"></a>CComCriticalSection::m_sec  
 Tüm tarafından kullanılan bir kritik bölüm nesnesi içeren `CComCriticalSection` yöntemleri.  
  
```
CRITICAL_SECTION m_sec;
```  
  
##  <a name="term"></a>CComCriticalSection::Term  
 Win32 işlev çağrılarını [DeleteCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms682552), içerdiği kritik bölüm nesnesi tarafından kullanılan tüm kaynakları serbest bırakır [m_sec](#m_sec) veri üyesi.  
  
```
HRESULT Term() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir kez `Term` çağrılıp çağrılmadığını, kritik bölümü artık eşitleme için kullanılabilir.  
  
##  <a name="unlock"></a>CComCriticalSection::Unlock  
 Win32 işlev çağrılarını [LeaveCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms684169), içerdiği kritik bölüm nesnenin sahipliğini serbest [m_sec](#m_sec) veri üyesi.  
  
```
HRESULT Unlock() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK`.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk sahipliğini almak için iş parçacığı çağırmalısınız [kilit](#lock) yöntemi. Her çağrı `Lock` karşılık gelen çağrıyı gerektirir `Unlock` kritik bölüm sahipliğini serbest bırakmak için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CComFakeCriticalSection sınıfı](../../atl/reference/ccomfakecriticalsection-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)   
 [CComCritSecLock Sınıfı](../../atl/reference/ccomcritseclock-class.md)
