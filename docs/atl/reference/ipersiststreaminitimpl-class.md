---
description: 'Daha fazla bilgi edinin: ıpersiststreaminimpl sınıfı'
title: Ipersiststreaminimpl sınıfı
ms.date: 11/04/2016
f1_keywords:
- IPersistStreamInitImpl
- ATLCOM/ATL::IPersistStreamInitImpl
- ATLCOM/ATL::IPersistStreamInitImpl::GetClassID
- ATLCOM/ATL::IPersistStreamInitImpl::GetSizeMax
- ATLCOM/ATL::IPersistStreamInitImpl::InitNew
- ATLCOM/ATL::IPersistStreamInitImpl::IsDirty
- ATLCOM/ATL::IPersistStreamInitImpl::Load
- ATLCOM/ATL::IPersistStreamInitImpl::Save
helpviewer_keywords:
- IPersistStreamInit ATL implementation
- IPersistStreamInitImpl class
- streams, ATL
ms.assetid: ef217c3c-020f-4cf8-871e-ef68e57865b8
ms.openlocfilehash: f60483435be750c7031f2e7bf7f3f18cba36a023
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158159"
---
# <a name="ipersiststreaminitimpl-class"></a>Ipersiststreaminimpl sınıfı

Bu sınıf `IUnknown` , [ıpersiststreaminıt](/windows/win32/api/ocidl/nn-ocidl-ipersiststreaminit) arabiriminin varsayılan bir uygulamasını uygular ve sunar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class ATL_NO_VTABLE IPersistStreamInitImpl
   : public IPersistStreamInit
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız, öğesinden türetilir `IPersistStreamInitImpl` .

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Ipersiststreaminimpl:: GetClassID](#getclassid)|Nesnenin CLSID 'sini alır.|
|[Ipersiststreaminimpl:: GetSizeMax](#getsizemax)|Nesnenin verilerini kaydetmek için gereken akışın boyutunu alır. ATL uygulama E_NOTIMPL döndürür.|
|[Ipersiststreaminimpl:: InitNew](#initnew)|Yeni oluşturulan bir nesneyi başlatır.|
|[Ipersiststreaminimpl:: IsDirty](#isdirty)|Nesnenin verilerinin son kaydedilmesinden bu yana değişip değişmediğini denetler.|
|[Ipersiststreaminimpl:: Load](#load)|Nesnenin özelliklerini belirtilen akıştan yükler.|
|[Ipersiststreaminimpl:: Save](#save)|Nesnenin özelliklerini belirtilen akışa kaydeder.|

## <a name="remarks"></a>Açıklamalar

[Ipersiststreaminıt](/windows/win32/api/ocidl/nn-ocidl-ipersiststreaminit) arabirimi, bir istemcinin, nesnenizin, kalıcı verilerini tek bir akışa yükleyip kaydetmeyeceğini ister. Sınıfı, `IPersistStreamInitImpl` Bu arabirimin varsayılan bir uygulamasını sağlar ve `IUnknown` hata ayıklama yapılarında döküm cihazına bilgi göndererek uygular.

**Ilgili makaleler** [ATL öğreticisi](../../atl/active-template-library-atl-tutorial.md), [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IPersistStreamInit`

`IPersistStreamInitImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

## <a name="ipersiststreaminitimplgetclassid"></a><a name="getclassid"></a> Ipersiststreaminimpl:: GetClassID

Nesnenin CLSID 'sini alır.

```
STDMETHOD(GetClassID)(CLSID* pClassID);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK bkz. [IPersist:: GetClassID](/windows/win32/api/objidl/nf-objidl-ipersist-getclassid) .

## <a name="ipersiststreaminitimplgetsizemax"></a><a name="getsizemax"></a> Ipersiststreaminimpl:: GetSizeMax

Nesnenin verilerini kaydetmek için gereken akışın boyutunu alır.

```
STDMETHOD(GetSizeMax)(ULARGE_INTEGER FAR* pcbSize);
```

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Windows SDK [ıpersiststreaminit:: GetSizeMax](/windows/win32/api/ocidl/nf-ocidl-ipersiststreaminit-getsizemax) öğesine bakın.

## <a name="ipersiststreaminitimplinitnew"></a><a name="initnew"></a> Ipersiststreaminimpl:: InitNew

Yeni oluşturulan bir nesneyi başlatır.

```
STDMETHOD(InitNew)();
```

### <a name="remarks"></a>Açıklamalar

Windows SDK [ıpersiststreaminit:: InitNew](/windows/win32/api/ocidl/nf-ocidl-ipersiststreaminit-initnew) öğesine bakın.

## <a name="ipersiststreaminitimplisdirty"></a><a name="isdirty"></a> Ipersiststreaminimpl:: IsDirty

Nesnenin verilerinin son kaydedilmesinden bu yana değişip değişmediğini denetler.

```
STDMETHOD(IsDirty)();
```

### <a name="remarks"></a>Açıklamalar

Windows SDK [ıpersiststreaminit:: IsDirty](/windows/win32/api/ocidl/nf-ocidl-ipersiststreaminit-isdirty) öğesine bakın.

## <a name="ipersiststreaminitimplload"></a><a name="load"></a> Ipersiststreaminimpl:: Load

Nesnenin özelliklerini belirtilen akıştan yükler.

```
STDMETHOD(Load)(LPSTREAM pStm);
```

### <a name="remarks"></a>Açıklamalar

ATL bu bilgileri almak için nesnenin özellik eşlemesini kullanır.

Windows SDK [ıpersiststreaminıt:: Load](/windows/win32/api/ocidl/nf-ocidl-ipersiststreaminit-load) öğesine bakın.

## <a name="ipersiststreaminitimplsave"></a><a name="save"></a> Ipersiststreaminimpl:: Save

Nesnenin özelliklerini belirtilen akışa kaydeder.

```
STDMETHOD(Save)(LPSTREAM pStm, BOOL fClearDirty);
```

### <a name="remarks"></a>Açıklamalar

ATL bu bilgileri depolamak için nesnenin özellik eşlemesini kullanır.

Windows SDK [ıpersiststreaminıt:: Save](/windows/win32/api/ocidl/nf-ocidl-ipersiststreaminit-save) öğesine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Storages ve akışlar](/windows/win32/Stg/storages-and-streams)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
