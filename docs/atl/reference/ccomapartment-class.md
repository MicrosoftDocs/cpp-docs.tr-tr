---
title: CComApartment sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComApartment
- ATLBASE/ATL::CComApartment
- ATLBASE/ATL::CComApartment::CComApartment
- ATLBASE/ATL::CComApartment::Apartment
- ATLBASE/ATL::CComApartment::GetLockCount
- ATLBASE/ATL::CComApartment::Lock
- ATLBASE/ATL::CComApartment::Unlock
- ATLBASE/ATL::CComApartment::m_dwThreadID
- ATLBASE/ATL::CComApartment::m_hThread
- ATLBASE/ATL::CComApartment::m_nLockCnt
dev_langs:
- C++
helpviewer_keywords:
- apartments in ATL EXE modules
- CComApartment class
ms.assetid: dbc177d7-7ee4-45f2-b563-d578a467ca93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 88e08d50cec36366df2423d31082b97d41b5061f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32362167"
---
# <a name="ccomapartment-class"></a>CComApartment sınıfı
Bu sınıf, bir iş parçacığı havuza EXE modülünde bir daire yönetmek için destek sağlar.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CComApartment
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComApartment::CComApartment](#ccomapartment)|Oluşturucu.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComApartment::Apartment](#apartment)|İş parçacığının başlangıç adresi işaretler.|  
|[CComApartment::GetLockCount](#getlockcount)|İş parçacığının geçerli kilit sayımını döndürür.|  
|[CComApartment::Lock](#lock)|İş parçacığının kilit sayısını artırır.|  
|[CComApartment::Unlock](#unlock)|Azaltır iş parçacığının kilit sayısı.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComApartment::m_dwThreadID](#m_dwthreadid)|İş parçacığının tanımlayıcısı içeriyor.|  
|[CComApartment::m_hThread](#m_hthread)|İş parçacığının tanıtıcı içerir.|  
|[CComApartment::m_nLockCnt](#m_nlockcnt)|İş parçacığının geçerli kilit sayısı içerir.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CComApartment` tarafından kullanılan [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md) bir iş parçacığı havuza EXE modülü bir grupta yönetmek için. `CComApartment` bir iş parçacığında yöntemleri artırma ve azaltma kilit sayısı sağlar.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  
  
##  <a name="apartment"></a>  CComApartment::Apartment  
 İş parçacığının başlangıç adresi işaretler.  
  
```
DWORD Apartment();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Sırasında otomatik olarak ayarlamak [CComAutoThreadModule::Init](../../atl/reference/ccomautothreadmodule-class.md#init).  
  
##  <a name="ccomapartment"></a>  CComApartment::CComApartment  
 Oluşturucu.  
  
```
CComApartment();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Başlatır `CComApartment` veri üyeleri [m_nLockCnt](#m_nlockcnt) ve [m_hThread](#m_hthread).  
  
##  <a name="getlockcount"></a>  CComApartment::GetLockCount  
 İş parçacığının geçerli kilit sayımını döndürür.  
  
```
LONG GetLockCount();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İş parçacığı üzerinde kilit sayısı.  
  
##  <a name="lock"></a>  CComApartment::Lock  
 İş parçacığının kilit sayısını artırır.  
  
```
LONG Lock();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tanılama için kullanışlı veya test bir değer.  
  
### <a name="remarks"></a>Açıklamalar  
 Tarafından çağrılır [CComAutoThreadModule::Lock](../../atl/reference/ccomautothreadmodule-class.md#lock).  
  
 İş parçacığı üzerinde kilit sayısı İstatistiksel amaçlar için kullanılır.  
  
##  <a name="m_dwthreadid"></a>  CComApartment::m_dwThreadID  
 İş parçacığının tanımlayıcısı içeriyor.  
  
```
DWORD m_dwThreadID;
```  
  
##  <a name="m_hthread"></a>  CComApartment::m_hThread  
 İş parçacığının tanıtıcı içerir.  
  
```
HANDLE m_hThread;
```  
  
##  <a name="m_nlockcnt"></a>  CComApartment::m_nLockCnt  
 İş parçacığının geçerli kilit sayısı içerir.  
  
```
LONG m_nLockCnt;
```  
  
##  <a name="unlock"></a>  CComApartment::Unlock  
 Azaltır iş parçacığının kilit sayısı.  
  
```
LONG Unlock();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tanılama için kullanışlı veya test bir değer.  
  
### <a name="remarks"></a>Açıklamalar  
 Tarafından çağrılır [CComAutoThreadModule::Unlock](../../atl/reference/ccomautothreadmodule-class.md#lock).  
  
 İş parçacığı üzerinde kilit sayısı İstatistiksel amaçlar için kullanılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
