---
title: IRunnableObjectImpl Sınıfı
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
ms.openlocfilehash: 2843c0c25a5c104ffbdff72255ac5d85cf53b1ee
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329453"
---
# <a name="irunnableobjectimpl-class"></a>IRunnableObjectImpl Sınıfı

Bu `IUnknown` [sınıf, IRunnableObject](/windows/win32/api/objidl/nn-objidl-irunnableobject) arabiriminin varsayılan uygulamasını uygular ve sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class IRunnableObjectImpl
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınızdan `IRunnableObjectImpl`türetilmiştir.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[IRunnableObjectImpl::GetRunningClass](#getrunningclass)|Çalışan denetimin CLSID'sini verir. ATL uygulaması CLSID'yi GUID_NULL ayarlar ve E_UNEXPECTED döndürür.|
|[IRunnableObjectImpl::IsRunning](#isrunning)|Denetimin çalışır durumda olup olmadığını belirler. ATL uygulaması TRUE döndürür.|
|[IRunnableObjectImpl::LockRunning](#lockrunning)|Denetimi çalışan duruma kilitler. ATL uygulaması S_OK döndürür.|
|[IRunnableObjectImpl::Çalıştır](#run)|Kontrolü çalıştırmaya zorlar. ATL uygulaması S_OK döndürür.|
|[IRunnableObjectImpl::SetContainedObject](#setcontainedobject)|Denetimin gömülü olduğunu gösterir. ATL uygulaması S_OK döndürür.|

## <a name="remarks"></a>Açıklamalar

[IRunnableObject](/windows/win32/api/objidl/nn-objidl-irunnableobject) arabirimi, bir denetimin çalışır durumda olup olmadığını belirlemek, çalıştırmak için zorlamak veya çalışan duruma kilitlemek için bir kapsayıcı sağlar. Sınıf `IRunnableObjectImpl` bu arabirimin varsayılan bir `IUnknown` uygulamasını sağlar ve hata ayıklama oluştururda dökümü aygıtına bilgi göndererek uygular.

**İlgili Makaleler** [ATL Tutorial](../../atl/active-template-library-atl-tutorial.md), [ATL Projesi Oluşturma](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IRunnableObject`

`IRunnableObjectImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlctl.h

## <a name="irunnableobjectimplgetrunningclass"></a><a name="getrunningclass"></a>IRunnableObjectImpl::GetRunningClass

Çalışan denetimin CLSID'sini verir.

```
HRESULT GetRunningClass(LPCLSID lpClsid);
```

### <a name="return-value"></a>Dönüş Değeri

ATL uygulaması \* *lpClsid'i* GUID_NULL ayarlar ve E_UNEXPECTED döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz. [IRunnableObject::Windows](/windows/win32/api/objidl/nf-objidl-irunnableobject-getrunningclass) SDK'da GetRunningClass.

## <a name="irunnableobjectimplisrunning"></a><a name="isrunning"></a>IRunnableObjectImpl::IsRunning

Denetimin çalışır durumda olup olmadığını belirler.

```
virtual BOOL IsRunning();
```

### <a name="return-value"></a>Dönüş Değeri

ATL uygulaması TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz. [IRunnableObject::Windows](/windows/win32/api/objidl/nf-objidl-irunnableobject-isrunning) SDK'da Çalışıyor.

## <a name="irunnableobjectimpllockrunning"></a><a name="lockrunning"></a>IRunnableObjectImpl::LockRunning

Denetimi çalışan duruma kilitler.

```
HRESULT LockRunning(BOOL fLock, BOOL fLastUnlockCloses);
```

### <a name="return-value"></a>Dönüş Değeri

ATL uygulaması S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz. [IRunnableObject::Windows](/windows/win32/api/objidl/nf-objidl-irunnableobject-lockrunning) SDK'da Kilitleme.

## <a name="irunnableobjectimplrun"></a><a name="run"></a>IRunnableObjectImpl::Çalıştır

Kontrolü çalıştırmaya zorlar.

```
HRESULT Run(LPBINDCTX lpbc);
```

### <a name="return-value"></a>Dönüş Değeri

ATL uygulaması S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz. [IRunnableObject::Windows](/windows/win32/api/objidl/nf-objidl-irunnableobject-run) SDK'da çalıştırın.

## <a name="irunnableobjectimplsetcontainedobject"></a><a name="setcontainedobject"></a>IRunnableObjectImpl::SetContainedObject

Denetimin gömülü olduğunu gösterir.

```
HRESULT SetContainedObject(BOOL fContained);
```

### <a name="return-value"></a>Dönüş Değeri

ATL uygulaması S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz. [IRunnableObject::Windows](/windows/win32/api/objidl/nf-objidl-irunnableobject-setcontainedobject) SDK'daki SetContainedObject.

## <a name="see-also"></a>Ayrıca bkz.

[CComControl Sınıfı](../../atl/reference/ccomcontrol-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
