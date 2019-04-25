---
title: Irunnableobjectımpl sınıfı
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
ms.openlocfilehash: 44b1e0ae1b72a40b45abe0650eb69a279b5a84d1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62200345"
---
# <a name="irunnableobjectimpl-class"></a>Irunnableobjectımpl sınıfı

Bu sınıfın uyguladığı `IUnknown` ve varsayılan bir uygulama sağlar [IRunnableObject](/windows/desktop/api/objidl/nn-objidl-irunnableobject) arabirimi.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class IRunnableObjectImpl
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
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

[IRunnableObject](/windows/desktop/api/objidl/nn-objidl-irunnableobject) arabirimi denetim çalışıp çalışmadığını belirlemek için çalıştırmak veya çalışır duruma geçirmek kilitlemek için zorlamak için bir kapsayıcı sağlar. Sınıf `IRunnableObjectImpl` bu arabirimin bir varsayılan uygulamasını sağlar ve uygulayan `IUnknown` dökümünü almak için bilgi göndererek hata ayıklama cihazı oluşturur.

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

Bkz: [IRunnableObject::GetRunningClass](/windows/desktop/api/objidl/nf-objidl-irunnableobject-getrunningclass) Windows SDK içinde.

##  <a name="isrunning"></a>  IRunnableObjectImpl::IsRunning

Denetim çalışıp çalışmadığını belirtir.

```
virtual BOOL IsRunning();
```

### <a name="return-value"></a>Dönüş Değeri

ATL uygulamasını TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz: [IRunnableObject::IsRunning](/windows/desktop/api/objidl/nf-objidl-irunnableobject-isrunning) Windows SDK içinde.

##  <a name="lockrunning"></a>  IRunnableObjectImpl::LockRunning

Denetim çalışır duruma geçirmek kilitler.

```
HRESULT LockRunning(BOOL fLock, BOOL fLastUnlockCloses);
```

### <a name="return-value"></a>Dönüş Değeri

ATL uygulamasını S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz: [IRunnableObject::LockRunning](/windows/desktop/api/objidl/nf-objidl-irunnableobject-lockrunning) Windows SDK içinde.

##  <a name="run"></a>  IRunnableObjectImpl::Run

Çalıştırılacak denetim zorlar.

```
HRESULT Run(LPBINDCTX lpbc);
```

### <a name="return-value"></a>Dönüş Değeri

ATL uygulamasını S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz: [IRunnableObject::Run](/windows/desktop/api/objidl/nf-objidl-irunnableobject-run) Windows SDK içinde.

##  <a name="setcontainedobject"></a>  IRunnableObjectImpl::SetContainedObject

Denetimin ekli olduğunu gösterir.

```
HRESULT SetContainedObject(BOOL fContained);
```

### <a name="return-value"></a>Dönüş Değeri

ATL uygulamasını S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz: [IRunnableObject::SetContainedObject](/windows/desktop/api/objidl/nf-objidl-irunnableobject-setcontainedobject) Windows SDK içinde.

## <a name="see-also"></a>Ayrıca bkz.

[CComControl Sınıfı](../../atl/reference/ccomcontrol-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
