---
title: IRunnableObjectImpl sınıfı
ms.date: 11/04/2016
f1_keywords:
- IRunnableObjectImpl
- ATLCTL/ATL::IRunnableObjectImpl
- ATLCTL/ATL::IRunnableObjectImpl::GetRunningClass
- ATLCTL/ATL::IRunnableObjectImpl::IsRunning
- ATLCTL/ATL::IRunnableObjectImpl::LockRunning
- ATLCTL/ATL::IRunnableObjectImpl::Run
- ATLCTL/ATL::IRunnableObjectImpl::SetContainedObject
helpviewer_keywords:
- containers, running controls
- IRunnableObjectImpl class
- IRunnableObject, ATL implementation
- controls [ATL], running
- controls [C++], container running in ATL
ms.assetid: 305c7c3b-889e-49dd-aca1-34379c1b9931
ms.openlocfilehash: 6b1af7c21c6f5028ad6d3a228cb22650fa3cef42
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495652"
---
# <a name="irunnableobjectimpl-class"></a>IRunnableObjectImpl sınıfı

Bu sınıf, `IUnknown` [irunnableobject](/windows/win32/api/objidl/nn-objidl-irunnableobject) arabiriminin varsayılan bir uygulamasını uygular ve sunar.

> [!IMPORTANT]
>  Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class IRunnableObjectImpl
```

#### <a name="parameters"></a>Parametreler

*ŞI*<br/>
Sınıfınız, öğesinden `IRunnableObjectImpl`türetilir.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IRunnableObjectImpl:: GetRunningClass](#getrunningclass)|Çalışan denetimin CLSID 'sini döndürür. ATL uygulama, CLSID değerini GUID_NULL olarak ayarlar ve E_UNEXPECTED döndürür.|
|[IRunnableObjectImpl:: IsRunning](#isrunning)|Denetimin çalışıp çalışmadığını belirler. ATL uygulamasının doğru değeri döndürür.|
|[IRunnableObjectImpl:: LockRunning](#lockrunning)|Denetimi çalışır durumda kilitler. ATL uygulamaları S_OK döndürür.|
|[IRunnableObjectImpl:: Run](#run)|Denetimi çalıştırmaya zorlar. ATL uygulamaları S_OK döndürür.|
|[IRunnableObjectImpl:: Setkirinedobject](#setcontainedobject)|Denetimin gömülü olduğunu gösterir. ATL uygulamaları S_OK döndürür.|

## <a name="remarks"></a>Açıklamalar

[IRunnableObject](/windows/win32/api/objidl/nn-objidl-irunnableobject) arabirimi bir kapsayıcının bir denetimin çalışıp çalışmadığını belirlemesine, çalıştırmayı zorlamaya veya çalışma durumuna kilitlemesine olanak sağlar. Sınıfı `IRunnableObjectImpl` , bu arabirimin varsayılan bir uygulamasını sağlar ve hata `IUnknown` ayıklama yapılarında döküm cihazına bilgi göndererek uygular.

**Ilgili makaleler** ATL [öğreticisi](../../atl/active-template-library-atl-tutorial.md), [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IRunnableObject`

`IRunnableObjectImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlctl. h

##  <a name="getrunningclass"></a>IRunnableObjectImpl:: GetRunningClass

Çalışan denetimin CLSID 'sini döndürür.

```
HRESULT GetRunningClass(LPCLSID lpClsid);
```

### <a name="return-value"></a>Dönüş Değeri

ATL uygulama, \* *lpclsıd* 'yi GUID_NULL olarak ayarlar ve E_UNEXPECTED döndürür.

### <a name="remarks"></a>Açıklamalar

Windows SDK [IRunnableObject:: GetRunningClass](/windows/win32/api/objidl/nf-objidl-irunnableobject-getrunningclass) öğesine bakın.

##  <a name="isrunning"></a>IRunnableObjectImpl:: IsRunning

Denetimin çalışıp çalışmadığını belirler.

```
virtual BOOL IsRunning();
```

### <a name="return-value"></a>Dönüş Değeri

ATL uygulamasının doğru değeri döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz. [IRunnableObject:: IsRunning](/windows/win32/api/objidl/nf-objidl-irunnableobject-isrunning) Windows SDK.

##  <a name="lockrunning"></a>IRunnableObjectImpl:: LockRunning

Denetimi çalışır durumda kilitler.

```
HRESULT LockRunning(BOOL fLock, BOOL fLastUnlockCloses);
```

### <a name="return-value"></a>Dönüş Değeri

ATL uygulamaları S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz. [IRunnableObject:: LockRunning](/windows/win32/api/objidl/nf-objidl-irunnableobject-lockrunning) Windows SDK.

##  <a name="run"></a>IRunnableObjectImpl:: Run

Denetimi çalıştırmaya zorlar.

```
HRESULT Run(LPBINDCTX lpbc);
```

### <a name="return-value"></a>Dönüş Değeri

ATL uygulamaları S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz. [IRunnableObject:: Windows SDK Çalıştır](/windows/win32/api/objidl/nf-objidl-irunnableobject-run) .

##  <a name="setcontainedobject"></a>IRunnableObjectImpl:: Setkirinedobject

Denetimin gömülü olduğunu gösterir.

```
HRESULT SetContainedObject(BOOL fContained);
```

### <a name="return-value"></a>Dönüş Değeri

ATL uygulamaları S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Windows SDK [IRunnableObject:: Setkirinedobject](/windows/win32/api/objidl/nf-objidl-irunnableobject-setcontainedobject) bölümüne bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CComControl Sınıfı](../../atl/reference/ccomcontrol-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
