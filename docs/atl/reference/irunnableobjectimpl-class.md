---
title: IRunnableObjectImpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IRunnableObjectImpl
- ATLCTL/ATL::IRunnableObjectImpl
- ATLCTL/ATL::IRunnableObjectImpl::GetRunningClass
- ATLCTL/ATL::IRunnableObjectImpl::IsRunning
- ATLCTL/ATL::IRunnableObjectImpl::LockRunning
- ATLCTL/ATL::IRunnableObjectImpl::Run
- ATLCTL/ATL::IRunnableObjectImpl::SetContainedObject
dev_langs:
- C++
helpviewer_keywords:
- containers, running controls
- IRunnableObjectImpl class
- IRunnableObject, ATL implementation
- controls [ATL], running
- controls [C++], container running in ATL
ms.assetid: 305c7c3b-889e-49dd-aca1-34379c1b9931
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a08fec0fd38e30729c9131def1831e5e5d8f633e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="irunnableobjectimpl-class"></a>IRunnableObjectImpl sınıfı
Bu sınıf uygulayan **IUnknown** ve bir varsayılan uygulamayı sağlar [IRunnableObject](http://msdn.microsoft.com/library/windows/desktop/ms692783) arabirimi.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class T>  
class IRunnableObjectImpl
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sınıfınız, türetilen `IRunnableObjectImpl`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IRunnableObjectImpl::GetRunningClass](#getrunningclass)|Çalışan Denetimi'nin CLSID değerini döndürür. ATL uygulamasını CLSID ayarlar `GUID_NULL` ve döndürür **E_UNEXPECTED**.|  
|[IRunnableObjectImpl::IsRunning](#isrunning)|Denetim çalışıp çalışmadığını belirler. ATL uygulamasını döndürür **doğru**.|  
|[IRunnableObjectImpl::LockRunning](#lockrunning)|Denetim çalışır duruma geçirmek kilitler. ATL uygulamasını döndürür `S_OK`.|  
|[IRunnableObjectImpl::Run](#run)|Çalıştırmak için Denetim zorlar. ATL uygulamasını döndürür `S_OK`.|  
|[IRunnableObjectImpl::SetContainedObject](#setcontainedobject)|Denetim katıştırılır gösterir. ATL uygulamasını döndürür `S_OK`.|  
  
## <a name="remarks"></a>Açıklamalar  
 [IRunnableObject](http://msdn.microsoft.com/library/windows/desktop/ms692783) arabirimi denetim çalışıp çalışmadığını belirlemek için çalıştırmak veya çalışan bir duruma kilitlemek için zorlamak için bir kapsayıcı sağlar. Sınıf `IRunnableObjectImpl` bu arabirimin varsayılan uygulamasını sağlar ve uygulayan **IUnknown** aygıt hata ayıklama dökümü bilgileri göndererek oluşturur.  
  
 **İlgili makaleler** [ATL öğretici](../../atl/active-template-library-atl-tutorial.md), [bir ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IRunnableObject`  
  
 `IRunnableObjectImpl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlctl.h  
  
##  <a name="getrunningclass"></a>  IRunnableObjectImpl::GetRunningClass  
 Çalışan Denetimi'nin CLSID değerini döndürür.  
  
```
HRESULT GetRunningClass(LPCLSID lpClsid);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 ATL uygulama kümeleri \* *lpClsid* için `GUID_NULL` ve döndürür **E_UNEXPECTED**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IRunnableObject::GetRunningClass](http://msdn.microsoft.com/library/windows/desktop/ms693734) Windows SDK.  
  
##  <a name="isrunning"></a>  IRunnableObjectImpl::IsRunning  
 Denetim çalışıp çalışmadığını belirler.  
  
```
virtual BOOL IsRunning();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 ATL uygulamasını döndürür **doğru**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IRunnableObject::IsRunning](http://msdn.microsoft.com/library/windows/desktop/ms678496) Windows SDK.  
  
##  <a name="lockrunning"></a>  IRunnableObjectImpl::LockRunning  
 Denetim çalışır duruma geçirmek kilitler.  
  
```
HRESULT LockRunning(BOOL fLock, BOOL fLastUnlockCloses);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 ATL uygulamasını döndürür `S_OK`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IRunnableObject::LockRunning](http://msdn.microsoft.com/library/windows/desktop/ms693361) Windows SDK.  
  
##  <a name="run"></a>  IRunnableObjectImpl::Run  
 Çalıştırmak için Denetim zorlar.  
  
```
HRESULT Run(LPBINDCTX lpbc);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 ATL uygulamasını döndürür `S_OK`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IRunnableObject::Run](http://msdn.microsoft.com/library/windows/desktop/ms694517) Windows SDK.  
  
##  <a name="setcontainedobject"></a>  IRunnableObjectImpl::SetContainedObject  
 Denetim katıştırılır gösterir.  
  
```
HRESULT SetContainedObject(BOOL fContained);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 ATL uygulamasını döndürür `S_OK`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IRunnableObject::SetContainedObject](http://msdn.microsoft.com/library/windows/desktop/ms693710) Windows SDK.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CComControl sınıfı](../../atl/reference/ccomcontrol-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
