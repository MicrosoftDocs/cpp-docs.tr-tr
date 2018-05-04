---
title: CComCritSecLock sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComCritSecLock
- ATLBASE/ATL::CComCritSecLock
- ATLBASE/ATL::CComCritSecLock::CComCritSecLock
- ATLBASE/ATL::CComCritSecLock::Lock
- ATLBASE/ATL::CComCritSecLock::Unlock
dev_langs:
- C++
helpviewer_keywords:
- CComCritSecLock class
ms.assetid: 223152a1-86c3-4ef9-89a7-f455fe791b0e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 98b6eb7a8e6df16134573b55a7c9666befe4e4a1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="ccomcritseclock-class"></a>CComCritSecLock sınıfı
Bu sınıf kilitleme ve kritik bölüm nesnenin kilidini açma yöntemlerini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class TLock> class CComCritSecLock
```  
  
#### <a name="parameters"></a>Parametreler  
 *TLock*  
 Kilitli ve kilidi nesnesi.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComCritSecLock::CComCritSecLock](#ctor)|Oluşturucu.|  
|[CComCritSecLock:: ~ CComCritSecLock](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComCritSecLock::Lock](#lock)|Kritik bölüm nesneyi kilitlemek için bu yöntemi çağırın.|  
|[CComCritSecLock::Unlock](#unlock)|Kritik bölüm nesne kilidini açmak için bu yöntemi çağırın.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf kilitlemek ve daha güvenli bir şekilde ile nesnelerin kilidini açmak için kullanmak [CComCriticalSection sınıfı](../../atl/reference/ccomcriticalsection-class.md) veya [CComAutoCriticalSection sınıfı](../../atl/reference/ccomautocriticalsection-class.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  
  
##  <a name="ctor"></a>  CComCritSecLock::CComCritSecLock  
 Oluşturucu.  
  
```
CComCritSecLock(TLock& cs, bool bInitialLock = true);
```  
  
### <a name="parameters"></a>Parametreler  
 *cs*  
 Kritik bölüm nesnesi.  
  
 `bInitialLock`  
 İlk kilit durumu: **true** kilitli anlamına gelir.  
  
### <a name="remarks"></a>Açıklamalar  
 Kritik bölüm nesnesini başlatır.  
  
##  <a name="dtor"></a>  CComCritSecLock:: ~ CComCritSecLock  
 Yok Edicisi.  
  
```
~CComCritSecLock() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Kritik bölüm nesne kilidini açar.  
  
##  <a name="lock"></a>  CComCritSecLock::Lock  
 Kritik bölüm nesneyi kilitlemek için bu yöntemi çağırın.  
  
```
HRESULT Lock() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Nesne başarıyla kilitlenmişse S_OK ya da HRESULT hata hatası döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Nesne zaten kilitliyse ASSERT hata hata ayıklama derlemelerinde ortaya çıkar.  
  
##  <a name="unlock"></a>  CComCritSecLock::Unlock  
 Kritik bölüm nesne kilidini açmak için bu yöntemi çağırın.  
  
```
void Unlock() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Nesne zaten kilidi açılmış, bir ASSERT hata hata ayıklama derlemelerinde ortaya çıkar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CComCriticalSection sınıfı](../../atl/reference/ccomcriticalsection-class.md)   
 [CComAutoCriticalSection Sınıfı](../../atl/reference/ccomautocriticalsection-class.md)
