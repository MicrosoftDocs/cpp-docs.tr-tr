---
title: Irunnableobjectımpl sınıfı | Microsoft Docs
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
ms.openlocfilehash: 2a98456d3d7d0d2e4600267a81151c44e38993c5
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37885594"
---
# <a name="irunnableobjectimpl-class"></a>Irunnableobjectımpl sınıfı
Bu sınıfın uyguladığı `IUnknown` ve varsayılan bir uygulama sağlar [IRunnableObject](http://msdn.microsoft.com/library/windows/desktop/ms692783) arabirimi.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class T>  
class IRunnableObjectImpl
```  
  
#### <a name="parameters"></a>Parametreler  
 *T*  
 Sınıfınız, türetilen `IRunnableObjectImpl`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IRunnableObjectImpl::GetRunningClass](#getrunningclass)|Çalışan denetimi CLSID değeri döndürür. ATL uygulamasını CLSID GUID_NULL için ayarlar ve E_UNEXPECTED döndürür.|  
|[IRunnableObjectImpl::IsRunning](#isrunning)|Denetim çalışıp çalışmadığını belirtir. ATL uygulamasını TRUE döndürür.|  
|[IRunnableObjectImpl::LockRunning](#lockrunning)|Denetim çalışır duruma geçirmek kilitler. ATL uygulamasını S_OK döndürür.|  
|[IRunnableObjectImpl::Run](#run)|Çalıştırılacak denetim zorlar. ATL uygulamasını S_OK döndürür.|  
|[IRunnableObjectImpl::SetContainedObject](#setcontainedobject)|Denetimin ekli olduğunu gösterir. ATL uygulamasını S_OK döndürür.|  
  
## <a name="remarks"></a>Açıklamalar  
 [IRunnableObject](http://msdn.microsoft.com/library/windows/desktop/ms692783) arabirimi denetim çalışıp çalışmadığını belirlemek için çalıştırmak veya çalışır duruma geçirmek kilitlemek için zorlamak için bir kapsayıcı sağlar. Sınıf `IRunnableObjectImpl` bu arabirimin bir varsayılan uygulamasını sağlar ve uygulayan `IUnknown` dökümünü almak için bilgi göndererek hata ayıklama cihazı oluşturur.  
  
 **İle ilgili makaleler** [ATL öğretici](../../atl/active-template-library-atl-tutorial.md), [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IRunnableObject`  
  
 `IRunnableObjectImpl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlctl.h  
  
##  <a name="getrunningclass"></a>  IRunnableObjectImpl::GetRunningClass  
 Çalışan denetimi CLSID değeri döndürür.  
  
```
HRESULT GetRunningClass(LPCLSID lpClsid);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 ATL uygulamasını kümeleri \* *lpClsid* GUID_NULL ve E_UNEXPECTED döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IRunnableObject::GetRunningClass](http://msdn.microsoft.com/library/windows/desktop/ms693734) Windows SDK içinde.  
  
##  <a name="isrunning"></a>  IRunnableObjectImpl::IsRunning  
 Denetim çalışıp çalışmadığını belirtir.  
  
```
virtual BOOL IsRunning();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 ATL uygulamasını TRUE döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IRunnableObject::IsRunning](http://msdn.microsoft.com/library/windows/desktop/ms678496) Windows SDK içinde.  
  
##  <a name="lockrunning"></a>  IRunnableObjectImpl::LockRunning  
 Denetim çalışır duruma geçirmek kilitler.  
  
```
HRESULT LockRunning(BOOL fLock, BOOL fLastUnlockCloses);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 ATL uygulamasını S_OK döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IRunnableObject::LockRunning](http://msdn.microsoft.com/library/windows/desktop/ms693361) Windows SDK içinde.  
  
##  <a name="run"></a>  IRunnableObjectImpl::Run  
 Çalıştırılacak denetim zorlar.  
  
```
HRESULT Run(LPBINDCTX lpbc);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 ATL uygulamasını S_OK döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IRunnableObject::Run](http://msdn.microsoft.com/library/windows/desktop/ms694517) Windows SDK içinde.  
  
##  <a name="setcontainedobject"></a>  IRunnableObjectImpl::SetContainedObject  
 Denetimin ekli olduğunu gösterir.  
  
```
HRESULT SetContainedObject(BOOL fContained);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 ATL uygulamasını S_OK döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IRunnableObject::SetContainedObject](http://msdn.microsoft.com/library/windows/desktop/ms693710) Windows SDK içinde.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CComControl sınıfı](../../atl/reference/ccomcontrol-class.md)   
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)
